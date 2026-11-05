---
title: "Quadro Legal e Normativo — MED, AGT, APD e GEPE (Angola)"
aliases:
  - "Quadro Legal MED AGT e APD Angola"
  - "Legislação Angolana SGE"
created: 2026-10-31
updated: 2026-11-02
status: concluido
tags:
  - recurso
  - legislacao
  - med-angola
  - agt
  - apd
  - gepe
  - sge
---

# Recurso: Quadro Legal e Normativo — MED, AGT, APD e GEPE (Angola)

> [!abstract] Ligações no Vault
> - **Painel Central:** [[Inicio]] | **Projeto Principal:** [[00 - MOC SGE IPCAG 12008 BGO]]
> - **Aplicação Direta nas Especificações:** [[01 - Dominio e Regras]] | [[02 - Fluxos de Trabalho]] | [[04 - Telas e Documentos]] | [[05 - Modelagem de Dados]]
> - **Diagramas no Figma:** [[Quadros de Arquitetura no Figma|Catálogo de Quadros FigJam]] | [Quadro Geral Unificado](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0)

---

## 1. Catálogo de Diplomas Legais que Regem o SGE IPCAG N.º 12008 / BGO

| Diploma Legal | Entidade Emissora | Âmbito e Impacto Direto na Arquitetura do SGE | Regras de Negócio Vinculadas |
| :--- | :---: | :--- | :--- |
| **Lei n.º 32/20, de 12 de Agosto** *(altera a Lei n.º 17/16)* | Assembleia Nacional / MED | **Lei de Bases do Sistema de Educação e Ensino:** Define a estrutura do II Ciclo do Ensino Secundário Técnico-Profissional (10ª à 13ª Classe) e a escala nacional de avaliação de `0` a `20` valores. | `RN-01`, `RN-06` |
| **Decreto Presidencial n.º 167/23** | Presidência da República / MED | **Regime Jurídico do Subsistema de Ensino Secundário Técnico-Profissional (ESTP):** Regula as componentes curriculares (Socio-Cultural, Científica e Técnica/Tecnológica/Prática), as disciplinas nucleares, o Estágio Curricular, a Prova de Aptidão Profissional (PAP) e a Média Final de Curso (`MFC`). | `RN-01`, `RN-04`, `RN-06` |
| **Decreto Presidencial n.º 93/21** | Presidência da República / MED | **Regulamento sobre os Cargos de Direção e Chefia:** Define as competências estritas da Direção Executiva (`DIR_GERAL`, `SUB_PED`, `SUB_ADM`), Chefias de Secretaria (`CHEFE_SEC_PED`, `CHEFE_SEC_GER`), Coordenações (`COORD_CURSO`, `COORD_DISC`, `COORD_TURNO`) e Direção de Turma (`DIR_TURMA`). | `RN-02`, `RN-03`, `RN-04`, `RN-08` |
| **Decreto Executivo n.º 361/26** e **DE n.º 136/24** | Ministério da Educação (MED) | **Normas de Exames de Admissão à 10ª Classe e Calendário Escolar Nacional:** Exige correção cega por **Código de Anonimato** nos exames de seleção, janelas temporais dos 3 trimestres e regras de assiduidade e recurso. | `RN-01`, `RN-03`, `RN-04`, `RN-05` |
| **Decreto Presidencial n.º 292/18 (RJFDE)** | Presidência da República / AGT | **Regime Jurídico das Faturas e Documentos Equivalentes:** Proíbe a eliminação (`DELETE`) ou edição retroativa de recibos emitidos; obriga à numeração sequencial cronológica por série anual e ao uso exclusivo de **Nota de Estorno (`NE`)** para anulações. | `RN-09`, `RN-09.1`, `RN-09.2` |
| **Lei n.º 22/11, de 17 de Junho** | Assembleia Nacional / APD | **Lei da Proteção de Dados Pessoais:** Exige controlo estrito de acesso por função (RBAC + RLS), segregação de dados financeiros e pedagógicos e trilha de auditoria imutável (`audit_logs`) sobre dados sensíveis de estudantes e famílias. | `RN-08`, `RN-10` |
| **Normas Estatísticas do GEPE / MED** | GEPE / MED | **Mapas Estatísticos Oficiais:** Padroniza o reporte demográfico e de aproveitamento por Curso, Classe, Turma, Turno (Manhã/Tarde), Género (`M`/`F`/`MF`) e Faixa Etária (`DOF-12`). | `RN-05`, `RN-10` |

---

## 2. Rastreabilidade Legal por Documento Oficial Impresso ([[04 - Telas e Documentos]])

> [!note] Numeração dos documentos oficiais
> Os códigos `DOF-01` a `DOF-12` (e as subpartes `A`/`B`/`C`) são os da Parte 2 de [[04 - Telas e Documentos]], que é a fonte autoritativa. `DOC-xx` designa apenas as notas da especificação. As bases legais vêm do catálogo do §1 e ainda têm de ser confirmadas no Diário da República (lacuna L3 do [[00.1 - Plano de Engenharia de Requisitos]]). A coluna de regras indica as `RN` que o DOC-04 aplica a cada documento (na Parte 2 ou no módulo que o emite).

| Código | Documento oficial impresso | Base legal | Regras de negócio |
| :---: | :--- | :--- | :--- |
| **`DOF-01`** | Ficha de Inscrição no Teste de Admissão (10ª Classe) + Talão com Código de Anonimato | Decreto Executivo n.º 361/26 | `RN-01.2`, `RN-08` |
| **`DOF-02`** | Pauta Oficial de Resultados do Exame de Admissão (`Admitidos` e `Não Admitidos`) | Decreto Executivo n.º 361/26 | `RN-01.2` |
| **`DOF-03`** | Ficha e Comprovativo Oficial de Matrícula / Confirmação Anual | Lei n.º 32/20 e DP n.º 167/23 | `RN-02`, `RN-05`, `RN-07`, `RN-08` |
| **`DOF-04`** | Mini-Pauta Oficial do MED por Disciplina (10ª à 12ª Classe) | DP n.º 167/23 e DP n.º 93/21 | `RN-01`, `RN-03`, `RN-04`, `RN-05` |
| **`DOF-05`** | Pauta Geral da Turma (Mapa do Conselho de Notas e Exames de Recurso) | DP n.º 167/23 e DP n.º 93/21 | `RN-01`, `RN-02` |
| **`DOF-06`** | Boletim Individual de Notas e Faltas (Trimestral e Anual) | Lei n.º 32/20 e DP n.º 167/23 | `RN-08` |
| **`DOF-07`** | Pauta e Termo Oficial de Exame Extraordinário (Eliminação de Cadeiras em Atraso) | **Por identificar** (ver questões em aberto) | `RN-02`, `RN-10` |
| **`DOF-08`** | `DOF-08A` Carta de Apresentação de Estágio Curricular · `DOF-08B` Ata Oficial de Defesa Pública da PAP (13ª Classe) | DP n.º 167/23 | `RN-06`, `RN-10` |
| **`DOF-09`** | `DOF-09A` Declaração de Matrícula / Frequência (Simples) · `DOF-09B` Declaração Com Notas Discriminadas · `DOF-09C` Guia Oficial de Transferência Externa de Saída | DP n.º 167/23 | `RN-05`, `RN-08`, `RN-10` |
| **`DOF-10`** | Certificado de Habilitações e Diploma de Técnico Médio (10ª à 13ª Classe) | DP n.º 167/23 | `RN-06`, `RN-08`, `RN-10` (`Livro, Folha e Termo`) |
| **`DOF-11`** | `DOF-11A` Recibo Oficial Sequencial em Kwanzas (`AOA`) · `DOF-11B` Nota de Estorno (Padrão AGT) · `DOF-11C` Mapa Diário de Fecho de Caixa por Turno | DP n.º 292/18 (RJFDE — AGT) | `RN-09`, `RN-09.1`, `RN-09.2` |
| **`DOF-12`** | Mapa Estatístico Oficial do GEPE / MED (Demografia e Aproveitamento Escolar) | Normas Estatísticas do GEPE / MED | `RN-05`, `RN-10` |

> [!question] Questões em aberto
> - **`DOF-07`:** nenhum diploma do §1 regula explicitamente o Exame Extraordinário de cadeiras em atraso. Falta identificar a base legal.
> - **Edital do concurso de admissão:** a versão anterior deste §2 citava um "Edital", mas o DOC-04 não especifica nenhum edital como documento oficial próprio. Falta confirmar se a `DOF-02` cumpre essa função ou se é preciso especificar um documento novo.
