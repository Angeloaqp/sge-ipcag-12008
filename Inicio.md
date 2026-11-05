---
title: "Início — Vault de Engenharia e Arquitetura (SGE IPCAG N.º 12008 / BGO)"
aliases:
  - "Inicio"
  - "Home"
  - "Dashboard"
created: 2026-10-31
updated: 2026-11-02
status: ativo
tags:
  - dashboard
  - moc
  - sge
  - ipcag-12008
---

# Painel Central do Vault — Engenharia de Software & SGE

> [!abstract] Bem-vindo à Base de Conhecimento Oficial (Obsidian Vault)
> Este cofre está organizado segundo a metodologia **PARA adaptada para Engenharia de Software**, garantindo rastreabilidade total entre requisitos legais angolanos (**MED / AGT / APD / GEPE**), modelagem de domínio (**DDD**), fluxos operacionais, histórias de utilizador (**BDD**), documentos oficiais e modelagem de dados (**PostgreSQL + Offline-First**).

---

## 1. Acesso Rápido ao Projeto Principal

> [!important] Projeto Ativo: **[[00 - MOC SGE IPCAG 12008 BGO|SGE — IPCAG N.º 12008 / BGO ("Nossa Senhora do Rosário")]]**
> Sistema de Gestão Escolar para o Ensino Secundário Técnico-Profissional (10ª à 13ª Classe) — Bairro Modular do Panguila, Município do Dande, Província do Bengo, Angola.
> - **Índice Mestre (MOC):** [[00 - MOC SGE IPCAG 12008 BGO]]
> - **Mapa Visual Interativo (Canvas):** [[Arquitetura SGE IPCAG 12008 BGO.canvas]]
> - **Base de Dados de Notas (Obsidian Base):** [[Painel Documentacao SGE.base]]

### Documentos Core da Especificação (`v1.2` Auditada)
1. **[[01 - Dominio e Regras|DOC-01 — Domínio (DDD), Estrutura Orgânica (RBAC), Máquinas de Estado e Regras de Negócio]]**
2. **[[02 - Fluxos de Trabalho|DOC-02 — Mapeamento de Fluxos de Trabalho Ponta a Ponta (Swimlanes e Exceções)]]**
3. **[[03 - User Stories|DOC-03 — User Story Mapping, Épicos e Critérios de Aceitação (BDD)]]**
4. **[[04 - Telas e Documentos|DOC-04 — Arquitetura da Informação (4 Workspaces) e 12 Documentos Oficiais (MED/AGT/GEPE)]]**
5. **[[05 - Modelagem de Dados|DOC-05 — Modelagem Conceptual e Organização Lógica da Base de Dados (ERD e RLS)]]**

> [!todo] Fase atual: Definição completa antes do código
> Siga o **[[00.1 - Plano de Engenharia de Requisitos|PLN-00 — Plano de Engenharia de Requisitos]]**: lacunas, mapa de capacidades do SGE, fases de validação e decisões pendentes.

---

## 2. 🎨 Quadros Visuais de Arquitetura no Figma (FigJam)

> [!tip] 🚀 Acesso Rápido aos Diagramas Oficiais da Equipa (`angeloaqp1997's team`)
> Toda a especificação está desenhada e sincronizada no Figma em alta resolução:
> - 🌐 **Quadro Geral Unificado (Todas as Secções):** [Abrir Ficheiro Geral no FigJam](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - 🏛️ **DOC-01 (Domínio, RBAC e Máquinas de Estado):** [Abrir Quadro DOC-01](https://www.figma.com/board/l8fbIkk7SlJXCc3poCnExT)
> - 🔄 **DOC-02 (Fluxos de Trabalho / Swimlanes):** [Abrir Quadro DOC-02](https://www.figma.com/board/klMnPKkxorDv9NEfvvpSRq)
> - 📋 **DOC-03 (User Story Mapping e Critérios BDD):** [Abrir Quadro DOC-03](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd)
> - 📑 **DOC-04 (Arquitetura da Informação e Documentos MED/AGT):** [Abrir Quadro DOC-04](https://www.figma.com/board/ceE1mzcDmB2bT9RUAZxOcN)
> - 🗄️ **DOC-05 (Modelagem Lógica ERD, Offline-First e RLS):** [Abrir Quadro DOC-05](https://www.figma.com/board/lGrzPwEBaxgExyewDXnEAt)
> - 📑 **Catálogo Completo com Metadados e Instruções:** [[Quadros de Arquitetura no Figma|Ver Índice Completo de Links do Figma]]

---

## 3. Vista Dinâmica da Documentação (`Obsidian Base`)

![[Painel Documentacao SGE.base]]

---

## 4. Navegação por Estrutura de Pastas do Vault

| Pasta | Propósito | Notas e Índices Principais |
| :--- | :--- | :--- |
| **`00 - Inbox/`** | Material recebido por triar, rascunhos rápidos e novos despachos | [[00 - Guia de Triagem Inbox]] |
| **`01 - Projetos/`** | Projetos com escopo, entregáveis e ciclo de vida definidos | [[00 - MOC SGE IPCAG 12008 BGO]]<br>[[Arquitetura SGE IPCAG 12008 BGO.canvas]]<br>[[Painel Documentacao SGE.base]] |
| **`02 - Areas/`** | Domínios de responsabilidade contínua (Arquitetura e Gestão Escolar) | [[Arquitetura de Software e DDD]]<br>[[Governacao Escolar Ensino Tecnico MED]] |
| **`03 - Recursos/`** | Legislação angolana, normas técnicas e catálogos de ativos no Figma | [[Quadro Legal MED AGT e APD Angola]]<br>[[Quadros de Arquitetura no Figma]] |
| **`04 - Modelos/`** | Templates padronizados para criação rápida de novas notas | [[Modelo de Documento de Arquitetura]]<br>[[Modelo de User Story BDD]] |
| **`99 - Arquivo/`** | Cópias de segurança (`Backup Original Pre-Obsidian`) e ficheiros inativos | Ficheiros preservados por segurança (nunca apagados) |

---

## 5. Próximas Ações Recomendadas

> [!todo] Completar — Próximos Marcos de Engenharia
> - [x] Concluir e auditar a especificação funcional e lógica (`DOC-01` a `DOC-05` — `v1.1`).
> - [x] Estruturar os 5 quadros exclusivos de arquitetura no FigJam (`DOC-01` a `DOC-05`).
> - [x] Organizar o Vault no Obsidian com YAML Frontmatter, `[[wikilinks]]`, `.base` e `.canvas`.
> - [ ] Concluir a fase de definição ([[00.1 - Plano de Engenharia de Requisitos]] — ver o estado no topo do plano e as notas novas no [[00 - MOC SGE IPCAG 12008 BGO|MOC §2.1]]) e aprovar a especificação `v2.0`.
> - [ ] Iniciar a geração dos scripts físicos SQL (`DDL PostgreSQL`, Triggers de Imutabilidade e Políticas `RLS`) a partir de [[05 - Modelagem de Dados]].
> - [ ] Prototipar a API Backend e o motor de sincronização *Offline-First* (`IndexedDB` $\leftrightarrow$ `PostgreSQL`).
