---
title: "Modelo de User Story (BDD)"
aliases:
  - "Template User Story BDD"
created: 2026-10-31
updated: 2026-10-31
status: rascunho
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - modelo
  - template
  - user-stories
  - bdd
  - sge
---

# `US-XXX-00`: [Título Conciso da Funcionalidade]

> [!abstract] Rastreabilidade da User Story
> - **Projeto:** [[00 - MOC SGE IPCAG 12008 BGO]] | **Catálogo Geral:** [[03 - User Stories]]
> - **Épico:** `EP-XXX` | **Fluxo Relacionado:** [[02 - Fluxos de Trabalho]] | **Regras:** [[01 - Dominio e Regras]]
> - **Quadro no Figma:** [Quadro DOC-03 (User Story Mapping)](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd) | [[Quadros de Arquitetura no Figma|Catálogo de Links]]

---

## 1. Declaração da História de Utilizador

- **História:** *Como* **`[Cargo RBAC — DP n.º 93/21]`**, *quero* **`[ação ou funcionalidade desejada]`**, *para* **`[benefício de negócio ou conformidade legal MED/AGT/APD]`**.
- **Pré-condições:**
  - Utilizador autenticado com o perfil `[RBAC]`.
  - `[Estado necessário da máquina de estados]`.

---

## 2. Critérios de Aceitação (BDD — Gherkin)

### Cenário 1 (Sucesso — Caminho Feliz)
- **Dado** que `[contexto inicial válido]`,
- **Quando** o utilizador `[executa a ação principal]`,
- **Então** o sistema `[resultado esperado e mudança de estado]`.

### Cenário 2 (Bloqueio / Regra de Negócio)
- **Dado** que `[condição que viola uma regra RN-01..RN-10]`,
- **Quando** o utilizador tenta `[ação inválida]`,
- **Então** o sistema rejeita a operação com `[código de erro e mensagem clara]` e regista o evento em `audit_logs` se aplicável.

---

## 3. Pós-condições e Impacto nos Dados

> [!todo] Completar
> Liste as tabelas de [[05 - Modelagem de Dados]] e os documentos de [[04 - Telas e Documentos]] impactados por esta história.
