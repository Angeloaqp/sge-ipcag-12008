---
title: "Catálogo Completo de Quadros de Arquitetura no Figma (FigJam)"
aliases:
  - "Quadros de Arquitetura no Figma"
  - "Figma SGE"
  - "FigJam SGE"
  - "Todos os Links do Figma"
  - "Figma Links"
  - "Links FigJam"
created: 2026-10-31
updated: 2026-11-02
status: ativo
version: "1.2"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - recurso
  - figma
  - figjam
  - diagramas
  - arquitetura
  - catalogo-links
  - sge
---

# Catálogo Central de Quadros de Arquitetura no Figma (FigJam)

> [!abstract] Navegação no Vault
> - **Painel Principal:** [[Inicio|Início do Vault]] | **Índice do Projeto:** [[00 - MOC SGE IPCAG 12008 BGO|MOC — SGE IPCAG N.º 12008 / BGO]]
> - **Canvas do Sistema:** [[Arquitetura SGE IPCAG 12008 BGO.canvas|Mapa Visual Interativo (.canvas)]]
> - **Base de Dados Dinâmica:** [[Painel Documentacao SGE.base|Painel da Documentação (.base)]]

---

## 1. Acesso Rápido aos Ambientes Visuais no Figma

Toda a arquitetura do **Sistema de Gestão Escolar (SGE)** do **IPCAG N.º 12008 / BGO** está modelada visualmente na equipa oficial do Figma:
- **Equipa Figma:** `angeloaqp1997's team` (`team::1261050830171286420`)
- **Ficheiro Geral Unificado (Todas as Secções):** [Abrir Ficheiro Geral no FigJam (OneLIwLlc2kuM1koaIeXG0)](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
- **Estrutura por Páginas Dedicadas:** 5 Quadros Individuais criados para isolar cada fase da engenharia de software (`DOC-01` a `DOC-05`).

> [!tip] 🚀 Links Diretos de Um Clique
> - 🌐 **Quadro Mestre Unificado (Todas as Secções 01 a 05.6):** [Aceder ao Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - 🏛️ **DOC-01 (Domínio, RBAC e Máquinas de Estado):** [Aceder ao Quadro DOC-01](https://www.figma.com/board/l8fbIkk7SlJXCc3poCnExT)
> - 🔄 **DOC-02 (Fluxos de Trabalho / Swimlanes):** [Aceder ao Quadro DOC-02](https://www.figma.com/board/klMnPKkxorDv9NEfvvpSRq)
> - 📋 **DOC-03 (User Story Mapping e Critérios BDD):** [Aceder ao Quadro DOC-03](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd)
> - 📑 **DOC-04 (Arquitetura da Informação e Documentos MED/AGT):** [Aceder ao Quadro DOC-04](https://www.figma.com/board/ceE1mzcDmB2bT9RUAZxOcN)
> - 🗄️ **DOC-05 (Modelagem Lógica ERD, Offline-First e RLS):** [Aceder ao Quadro DOC-05](https://www.figma.com/board/lGrzPwEBaxgExyewDXnEAt)

---

## 2. Matriz Geral de Rastreabilidade e Links Oficiais

| Código | Documento no Vault | Escopo Visual no FigJam | Quadro Dedicado (Página Individual) | Secção no Ficheiro Geral Unificado | Estado |
| :---: | :--- | :--- | :---: | :---: | :---: |
| **`DOC-01`** | [[01 - Dominio e Regras\|01 - Domínio e Regras]] | Mapa dos 6 Contextos DDD, 12 Perfis RBAC (DP n.º 93/21), 7 Máquinas de Estado e Regras `RN-01` a `RN-10.1` | [Abrir DOC-01](https://www.figma.com/board/l8fbIkk7SlJXCc3poCnExT) | [Secção 01 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |
| **`DOC-02`** | [[02 - Fluxos de Trabalho\|02 - Fluxos de Trabalho]] | 8 Diagramas Swimlanes ponta a ponta (Admissão, Matrícula, Rotina Docente Offline-First, Conselho de Notas, Deficiências, 13ª Classe, Tesouraria e Documentos) | [Abrir DOC-02](https://www.figma.com/board/klMnPKkxorDv9NEfvvpSRq) | [Secção 02 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |
| **`DOC-03`** | [[03 - User Stories\|03 - User Stories]] | User Story Mapping dos 7 Épicos (`EP-GOV` a `EP-DOC-AUD`), as 32 User Stories e matriz de rastreabilidade BDD | [Abrir DOC-03](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd) | [Secção 03 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |
| **`DOC-04`** | [[04 - Telas e Documentos\|04 - Telas e Documentos]] | Árvore dos 4 Workspaces + Portal QR Code e Anatomia Estrutural dos 12 Documentos Oficiais Impressos (`DOF-01` a `DOF-12`) | [Abrir DOC-04](https://www.figma.com/board/ceE1mzcDmB2bT9RUAZxOcN) | [Secção 04 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |
| **`DOC-05`** | [[05 - Modelagem de Dados\|05 - Modelagem de Dados]] | Arquitetura *Offline-First* (IndexedDB + PostgreSQL), Diagrama ERD das 44 Tabelas nos 6 Domínios e Árvore de Isolamento RLS | [Abrir DOC-05](https://www.figma.com/board/lGrzPwEBaxgExyewDXnEAt) | [Secção 05 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |
| **`AUD-01`** | [[01 - Dominio e Regras#RN-10 Auditoria Imutável (APD - Lei n.º 22/11), Livro/Folha/Termo, QR Code e Resiliência Offline-First\|Refinamentos de Auditoria]] | Mapa das 5 Ações Corretivas da Auditoria de Consistência (`[INC-01]` a `[INC-07]`), FSM de 3 Níveis e Casos de Borda | Integrado nos Quadros `DOC-01` a `05` | [Secção 05.5 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.1` |
| **`ADM-01`** | [[01 - Dominio e Regras#RN-01 Fórmulas Oficiais de Avaliação e Regra Estrita de Arredondamento MED (10ª à 12ª Classe)\|Regra de Admissão e Vagas]] | Fluxo completo de Admissão à 10ª Classe (`RN-01.2`): `quadros_vagas_admissao`, $MFA \ge 10$, Apuramento nos 3 Estados e Repescagem de 2ª Opção | Integrado em `DOC-01`, `02`, `05` | [Secção 05.6 no Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | `✅ v1.2` |

---

## 3. Especificação Detalhada de Cada Quadro Visual

### Quadro 01: Domínio, RBAC e Máquinas de Estado (`DOC-01`)
> [!example] 🏛️ Identificação do Quadro
> - **Link Direto:** [Abrir Quadro DOC-01 no FigJam](https://www.figma.com/board/l8fbIkk7SlJXCc3poCnExT)
> - **Ficheiro Geral:** [Secção 01 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Nota no Vault:** [[01 - Dominio e Regras]]
> - **Conteúdo Visual:**
>   1. **Mapa de Contextos Delimitados (DDD):** 6 bounded contexts com relações e contratos de integração.
>   2. **Hierarquia Orgânica dos 12 Cargos RBAC:** Segregação de poderes do Decreto Presidencial n.º 93/21.
>   3. **7 Máquinas de Estado Finitas (FSM):** Hierarquia de 3 níveis de notas, Candidatura, Matrícula Anual, Disciplinas/Deficiências, 13ª Classe (PAP/Estágio), Propinas e Borderô Anti-Fraude.
>   4. **10 Regras de Negócio Invioláveis:** Painéis visuais para `RN-01` até `RN-10`.

---

### Quadro 02: Fluxos de Trabalho Operacionais (Swimlanes — `DOC-02`)
> [!example] 🔄 Identificação do Quadro
> - **Link Direto:** [Abrir Quadro DOC-02 no FigJam](https://www.figma.com/board/klMnPKkxorDv9NEfvvpSRq)
> - **Ficheiro Geral:** [Secção 02 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Nota no Vault:** [[02 - Fluxos de Trabalho]]
> - **Conteúdo Visual:**
>   - **Raias Operacionais (Swimlanes):** Direção Executiva (`DIR_GERAL`, `SUB_PED`, `SUB_ADM`), Secretaria Pedagógica (`CHEFE_SEC_PED`, `OP_PED`), Tesouraria (`OP_TES`), Coordenações (`COORD_CURSO`, `COORD_DISC`, `COORD_TURNO`), Docência (`PROF`, `DIR_TURMA`).
>   - **8 Fluxos Mapeados:** (1) Admissão 10ª, (2) Matrícula e Bolsas, (3) Rotina Docente Offline-First, (4) Conselho de Notas, (5) Cadeiras em Atraso, (6) 13ª Classe Estágio/PAP, (7) Tesouraria Anti-Fraude, (8) Balcão de Documentos.

---

### Quadro 03: User Story Mapping e Critérios BDD (`DOC-03`)
> [!example] 📋 Identificação do Quadro
> - **Link Direto:** [Abrir Quadro DOC-03 no FigJam](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd)
> - **Ficheiro Geral:** [Secção 03 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Nota no Vault:** [[03 - User Stories]]
> - **Conteúdo Visual:**
>   - **7 Épicos Mapeados:** `EP-GOV`, `EP-ADM`, `EP-MAT`, `EP-PED`, `EP-DEF-13`, `EP-TES`, `EP-DOC-AUD`.
>   - **32 Cartões de User Stories:** Disposição vertical por prioridade com rastreabilidade explícita para critérios Gherkin BDD (Dado / Quando / Então).

---

### Quadro 04: Arquitetura da Informação e Documentos MED/AGT (`DOC-04`)
> [!example] 📑 Identificação do Quadro
> - **Link Direto:** [Abrir Quadro DOC-04 no FigJam](https://www.figma.com/board/ceE1mzcDmB2bT9RUAZxOcN)
> - **Ficheiro Geral:** [Secção 04 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Nota no Vault:** [[04 - Telas e Documentos]]
> - **Conteúdo Visual:**
>   - **Árvore Estrutural de Módulos (Sem UI):** 4 Workspaces Operacionais + Portal Público de Validação QR Code.
>   - **Anatomia dos 12 Documentos Oficiais Impressos:** Padrão de Cabeçalho Institucional da República de Angola, corpo tabular e Rodapé Criptográfico HMAC-SHA256 (`DOF-01` a `DOF-12`).

> [!warning] Quadros por atualizar
> No quadro dedicado do DOC-04 e na Secção 04 do Ficheiro Geral, os nós dos documentos oficiais ainda usam o prefixo antigo `DOC-` com o mesmo número e subparte. Até os quadros serem atualizados, leia-se `DOF-` nesses nós (convenção em [[04 - Telas e Documentos]]).

---

### Quadro 05: Modelagem Conceitual e Lógica de Dados (ERD — `DOC-05`)
> [!example] 🗄️ Identificação do Quadro
> - **Link Direto:** [Abrir Quadro DOC-05 no FigJam](https://www.figma.com/board/lGrzPwEBaxgExyewDXnEAt)
> - **Ficheiro Geral:** [Secção 05 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Nota no Vault:** [[05 - Modelagem de Dados]]
> - **Conteúdo Visual:**
>   - **Arquitetura de Sincronização Offline-First:** Fluxo `IndexedDB` $\leftrightarrow$ Fila de Idempotência $\leftrightarrow$ PostgreSQL Central.
>   - **Diagrama Entidade-Relacionamento (ERD):** 44 Tabelas agrupadas nos 6 grandes domínios com integridade referencial.
>   - **Árvore de Políticas de Segurança RLS:** Isolamento por linha garantindo que docentes e operadores só acedem aos seus dados autorizados.

---

### Secção 05.6: Admissão 10ª Classe, Quadro de Vagas e Repescagem (`ADM-01`)
> [!example] 🎯 Identificação do Quadro
> - **Ficheiro Geral:** [05.6 - Admissão 10ª Classe no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)
> - **Notas no Vault:** [[01 - Dominio e Regras#RN-01 Fórmulas Oficiais de Avaliação e Regra Estrita de Arredondamento MED (10ª à 12ª Classe)|Regra RN-01.2]] | [[02 - Fluxos de Trabalho#Fluxo 01 Configuração do Ano Letivo e Concurso de Admissão à 10ª Classe (DE n.º 361/26)|Fluxo 01]] | [[05 - Modelagem de Dados#3.1 Grupo 1 — Governação, Calendário e Estrutura Académica|Tabela quadros_vagas_admissao]]
> - **Conteúdo Visual:**
>   1. Parametrização em `quadros_vagas_admissao` (`total_vagas`, `nota_minima_admissao = 10`, `nota_minima_por_prova = 0`, faixas etárias DP n.º 167/23).
>   2. Inscrição com 1ª e 2ª opção, emissão de taxa, alocação nas 12 salas e correção cega por Código de Anonimato.
>   3. Cálculo de $MFA$ e bifurcação nos 3 resultados oficiais (`ADMITIDO`, `NÃO ADMITIDO - FORA DAS VAGAS / EXCEDENTE`, `NÃO ADMITIDO - NOTA INFERIOR AO MÍNIMO`).
>   4. Loop de repescagem de 2ª opção para turmas com vagas sobrantes e redução homologada de limiar por despacho conjunto da Direção Executiva.

---

## 4. Instruções de Colaboração e Configurações Técnicas

1. **Permissões de Acesso:** Todos os quadros estão registados sob o plano de equipa **`angeloaqp1997's team` (`team::1261050830171286420`)**. Para permissões de edição ou comentários, solicite acesso ao administrador da equipa.
2. **Navegação Eficiente no FigJam:**
   - Utilize a barra de secções à esquerda para saltar diretamente entre os tópicos numerados.
   - Os conectores usam código de cores consistente com os domínios do sistema: **Azul** (Governação), **Verde** (Pedagógico/Aprovado), **Amarelo/Laranja** (Avisos/Exames), **Vermelho** (Retenções/Veto/Bloqueio Financeiro), **Roxo** (Tesouraria/Recibos AGT).
3. **Sincronização Bidirecional:** Qualquer alteração efetuada nos ficheiros Markdown locais é refletida nestes quadros utilizando o MCP oficial `figma_figma`.
