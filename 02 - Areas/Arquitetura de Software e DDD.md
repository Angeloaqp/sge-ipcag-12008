---
title: "Arquitetura de Software, DDD, Offline-First e Segurança RLS"
aliases:
  - "Arquitetura de Software e DDD"
  - "Padrões Arquiteturais SGE"
created: 2026-10-31
updated: 2026-11-02
status: ativo
tags:
  - area
  - arquitetura
  - ddd
  - offline-first
  - rls
  - postgresql
  - sge
---

# Área: Arquitetura de Software, DDD, Offline-First e Segurança RLS

> [!abstract] Ligações no Vault
> - **Painel Central:** [[Inicio]] | **Projeto Principal:** [[00 - MOC SGE IPCAG 12008 BGO]]
> - **Especificações Relacionadas:** [[01 - Dominio e Regras]] | [[04 - Telas e Documentos]] | [[05 - Modelagem de Dados]]
> - **Quadros de Arquitetura no Figma:** [[Quadros de Arquitetura no Figma|Catálogo de Links FigJam]] | [Quadro Geral Unificado](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | [Quadro DOC-05 (ERD/RLS)](https://www.figma.com/board/lGrzPwEBaxgExyewDXnEAt)

---

## 1. Decomposição em Contextos Delimitados (*Domain-Driven Design*)

A arquitetura de domínio aplicada ao **[[00 - MOC SGE IPCAG 12008 BGO|SGE — IPCAG N.º 12008 / BGO]]** separa o sistema em **6 Contextos Delimitados (*Bounded Contexts*)**, alinhados com a segregação orgânica do **Decreto Presidencial n.º 93/21**:

1. **Contexto 01 — Governação & Direção Executiva:** Configuração do Ano Letivo, Matrizes Curriculares, Homologação de Pautas, Despachos de Reabertura e Auditoria Global (`DIR_GERAL`, `SUB_PED`, `SUB_ADM`).
2. **Contexto 02 — Admissão & Secretaria Pedagógica:** Concurso de Admissão à 10ª Classe com **Código de Anonimato**, Matrículas, Chamada Congelada, Transcrição de Histórico Externo e Emissão Documental com `Livro/Folha/Termo` (`CHEFE_SEC_PED`, `OP_PED`).
3. **Contexto 03 — Coordenação & Vida Pedagógica:** Dosificação Trimestral, Mini-Pautas *Offline-First*, Sumários, Faltas Diárias, Justificação exclusiva pelo Director de Turma e Conselho de Notas (`COORD_CURSO`, `COORD_DISC`, `DIR_TURMA`, `PROF`).
4. **Contexto 04 — 13ª Classe (Estágio & PAP) e Cadeiras em Atraso:** Gestão de Deficiências (Exame Extraordinário), Estágio Curricular Supervisionado, Banca de Defesa de PAP e cálculo da `MFC` (`COORD_CURSO`, `SUB_PED`, `DIR_GERAL`).
5. **Contexto 05 — Tesouraria Anti-Fraude, Fiscalidade AGT & RH:** Controlo de Borderô por Saldo (`N:N`), Motor de Bolsas, Conta Corrente de Propinas, Recibos Imutáveis, Notas de Estorno (`NE`), Fecho de Caixa por Turno e Assiduidade Laboral (`SUB_ADM`, `CHEFE_SEC_GER`, `OP_TES`, `COORD_TURNO`).
6. **Contexto 06 — Auditoria Imutável & Verificação Criptográfica:** Trilha *append-only* (`audit_logs` — Lei n.º 22/11 APD) e Portal Público de Verificação via **QR Code (`HMAC-SHA256`)**.

---

## 2. Estratégia de Resiliência *Offline-First* (Panguila / Bengo)

Para garantir operação contínua perante falhas de energia elétrica ou cortes de internet:
- **Camada Docente (Navegador / PWA):** Armazenamento local em `IndexedDB` cifrado + fila de sincronização (`sync_queue`) com `idempotency_key` (UUID v4) e resolução de conflitos via `optimistic locking` (`version`).
- **Camada de Balcão (Secretaria & Tesouraria):** Operação em servidor local na rede LAN do instituto com base de dados **PostgreSQL** e replicação assíncrona segura para a nuvem.
- **Trava de Segurança Crítica no Servidor:** A validação temporal do trimestre (`ABERTO_EM_CURSO` vs. `FECHADO_HOMOLOGADO`) é sempre verificada pelo relógio do servidor central (Máquina de Estado `3.1` do DOC-01 e `RN-10`), impedindo manipulação do relógio local do dispositivo.

---

## 3. Segurança em Profundidade (RBAC + PostgreSQL RLS + Imutabilidade)

- **Isolamento por Linha (*Row-Level Security*):** Especificado em detalhe em [[05 - Modelagem de Dados]], garantindo que um professor (`PROF`) só lê e escreve nas linhas de `avaliacoes_trimestrais` onde possui alocação ativa em `alocacoes_docentes`.
- **Fronteira de Privacidade Interdepartamental (`RN-08`):** A Secretaria Pedagógica consome apenas a função booleana `fn_semaforo_financeiro_aluno(aluno_id)` (`VERDE` / `VERMELHO`), sem acesso às tabelas financeiras.
- **Proibição de `DELETE` Contabilístico e de Auditoria (`RN-09` e `RN-10`):** Tabelas `recibos`, `notas_estorno` e `audit_logs` protegidas por triggers nativas contra `DELETE` e `UPDATE` indevidos.
