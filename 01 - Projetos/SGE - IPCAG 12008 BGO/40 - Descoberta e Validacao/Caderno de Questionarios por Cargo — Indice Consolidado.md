---
title: "Caderno de Questionários por Cargo — Índice Consolidado (Fase C — Parametrização e Descoberta)"
aliases:
  - "Índice Consolidado de Questionários por Cargo"
  - "DSC-00-INDEX"
  - "Caderno de Questionários da Escola"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-00-INDEX"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - indice-consolidado
  - parametrizacao
---

# Caderno de Questionários por Cargo: Índice Consolidado

**Finalidade:** Apresentar a estrutura modular completa de questionários por cargo destinados à recolha de parâmetros operacionais, regras de rotina e decisões regulamentares junto do IPCAG N.º 12008 / BGO e entidades tutelares, operacionalizando a `DEC-009` (Pontos de Controlo PC-E1 a PC-E4) sem bloquear o congelamento da especificação v2.0.

**Enquadramento Arquitetural:**
A especificação funcional e arquitetural do SGE IPCAG 12008 / BGO (v2.0) possui **0 questões estruturais em aberto** (`DEC-001` a `DEC-026`). O sistema é plenamente desacoplado e governado por tabelas de configuração (`parametros_instituicao`, `cursos`, `disciplinas`, `matriz_curricular`, `salas_fisicas`, `turnos`, etc.).

As **195 questões de parametrização e levantamento de campo** triadas em `IDX-12 §4` foram integralmente distribuídas por 7 cadernos modulares, adaptados ao perfil de cada interlocutor da instituição escolar.

---

## 1. Mapa Consolidado dos Questionários por Cargo

| Doc ID | Título do Questionário | Destinatários Principais | Papéis RBAC / Entidades | Total Perguntas | Pontos de Controlo |
| :--- | :--- | :--- | :--- | :---: | :---: |
| [[Questionario por Cargo — Secretaria Pedagogica\|DSC-04-SEC-PED]] | Questionário: Secretaria Pedagógica | Chefe de Secretaria Pedagógica e Oficiais Pedagógicos | `CHEFE_SEC_PED`, `OP_PED` | 47 | PC-E1 / PC-E2 |
| [[Questionario por Cargo — Subdirecao Pedagogica\|DSC-05-SUB-PED]] | Questionário: Subdireção Pedagógica | Subdiretor Pedagógico | `SUB_PED` | 43 | PC-E1 / PC-E2 |
| [[Questionario por Cargo — Subdirecao Administrativa e Tesouraria\|DSC-06-SUB-ADM]] | Questionário: Subdireção Administrativa e Tesouraria | Subdiretor Administrativo, Operadores de Tesouraria e Contabilista | `SUB_ADM`, `OP_TES`, Contabilista | 31 | PC-E1 |
| [[Questionario por Cargo — Secretaria Geral e Administracao Tecnica\|DSC-07-SEC-GER]] | Questionário: Secretaria Geral e Administração Técnica | Chefe da Secretaria Geral e Administrador Técnico Local | `CHEFE_SEC_GER`, `ADMIN_TEC` | 19 | PC-E1 / PC-E2 |
| [[Questionario por Cargo — Direcao Geral e Comissao de Gestao\|DSC-08-DIR-GERAL]] | Questionário: Direção Geral e Comissão de Gestão | Diretor Geral, Membros da Comissão de Gestão e Direção | `DIR_GERAL`, Direção, Comissão de Gestão | 45 | PC-E1 a PC-E3 |
| [[Questionario por Cargo — Coordenadores de Turno e de Curso\|DSC-09-COORD]] | Questionário: Coordenadores de Turno e de Curso | Coordenadores de Turno (Manhã/Tarde) e Coordenadores de Curso Técnico | `COORD_TURNO`, `COORD_CURSO` | 10 | PC-E1 / PC-E4 |
| [[Questionario Institucional — Direcao Provincial da Educacao e INADE\|DSC-10-DPE-INADE]] | Questionário de Articulação Institucional | Gabinete Provincial da Educação do Bengo e INADE / MED | Entidades Tutelares Externas | 4 | PC-E4 |
| **Total Global** | **7 Cadernos de Validação** | **Toda a Estrutura da Escola e Tutela** | **Todos os Papéis Operacionais** | **199** | **E1–E5** |

*(Nota: O total de 199 inclui as 195 perguntas de `IDX-12 §4` mais os 4 pontos de articulação institucional externa do Ticket #26 / Ticket #40; os blocos de recolha documental marcados `[HITL / DEC-nnn]` (ex.: alvará/acordo em `DSC-08`, contabilista e certidão fiscal em `DSC-06`, contacto APD em `DSC-07`) não entram nesta contagem.)*

---

## 2. Correspondência com o Índice de Questões em Aberto (`IDX-12 §4`)

- **§4.1 `CHEFE_SEC_PED` (47 perguntas):** Integradas integralmente em [[Questionario por Cargo — Secretaria Pedagogica|DSC-04-SEC-PED]].
- **§4.2 `SUB_PED` (43 perguntas):** Integradas integralmente em [[Questionario por Cargo — Subdirecao Pedagogica|DSC-05-SUB-PED]].
- **§4.3 `SUB_ADM` (29 perguntas) + §4.10 `contabilista` (2 perguntas):** Integradas integralmente em [[Questionario por Cargo — Subdirecao Administrativa e Tesouraria|DSC-06-SUB-ADM]].
- **§4.5 `CHEFE_SEC_GER` (18 perguntas) + §4.12 `equipa técnica` (1 pergunta):** Integradas integralmente em [[Questionario por Cargo — Secretaria Geral e Administracao Tecnica|DSC-07-SEC-GER]].
- **§4.4 `DIR_GERAL` (22 perguntas) + §4.6 `Direção` (12 perguntas) + §4.7 `Comissão de Gestão` (11 perguntas):** Integradas integralmente em [[Questionario por Cargo — Direcao Geral e Comissao de Gestao|DSC-08-DIR-GERAL]].
- **§4.8 `COORD_TURNO` (5 perguntas) + §4.9 `COORD_CURSO` (4 perguntas) + §4.11 `Por atribuir` (1 pergunta - `Q-C13-07`):** Integradas integralmente em [[Questionario por Cargo — Coordenadores de Turno e de Curso|DSC-09-COORD]].
- **Ticket #26 / Ticket #40 (4 perguntas de tutela externa):** Integradas formalmente em [[Questionario Institucional — Direcao Provincial da Educacao e INADE|DSC-10-DPE-INADE]].

---

## 3. Protocolo de Aplicação em Campo e Ingestão de Respostas

1. **Aplicação Diferenciada por Cargo:**
   - Cada responsável recebe apenas o caderno correspondente à sua área de competência, evitando sobrecarga e garantindo respostas de quem domina a rotina efetiva.
2. **Calendarização por Pontos de Controlo (`DEC-009`):**
   - **PC-E1 (Arranque e Matrículas):** Cadernos `DSC-04`, `DSC-06`, `DSC-07` e blocos de governança de `DSC-08`.
   - **PC-E2 (Horários e Avaliação Periódica):** Cadernos `DSC-05` e `DSC-09`.
   - **PC-E3 (Disciplina e Ocorrências):** Bloco disciplinar de `DSC-08` e `DSC-09`.
   - **PC-E4 (Estágios, PAP e Certificação Final):** Caderno `DSC-10` e bloco de conclusão de `DSC-09`.
3. **Ingestão Zero-Code:**
   - As respostas obtidas são vertidas diretamente para scripts de seed ou para o ecrã de administração de parâmetros institucionais, sem exigir novas sprints de engenharia de software nem alterações à arquitetura de base de dados congelada na v2.0.
