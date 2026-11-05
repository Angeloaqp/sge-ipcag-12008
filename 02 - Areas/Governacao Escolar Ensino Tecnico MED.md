---
title: "Governação Escolar e Ensino Secundário Técnico-Profissional (MED Angola)"
aliases:
  - "Governacao Escolar Ensino Tecnico MED"
  - "Gestão Escolar MED"
created: 2026-10-31
updated: 2026-11-02
status: ativo
tags:
  - area
  - governacao-escolar
  - med-angola
  - ensino-tecnico
  - sge
---

# Área: Governação Escolar e Ensino Secundário Técnico-Profissional (MED Angola)

> [!abstract] Ligações no Vault
> - **Painel Central:** [[Inicio]] | **Projeto Principal:** [[00 - MOC SGE IPCAG 12008 BGO]]
> - **Documentos de Especificação:** [[01 - Dominio e Regras]] | [[02 - Fluxos de Trabalho]] | [[03 - User Stories]] | [[04 - Telas e Documentos]]
> - **Enquadramento Legal:** [[Quadro Legal MED AGT e APD Angola]]
> - **Quadros de Arquitetura no Figma:** [[Quadros de Arquitetura no Figma|Catálogo FigJam]] | [Quadro Geral Unificado](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) | [Quadro DOC-01 (RBAC/Domínio)](https://www.figma.com/board/l8fbIkk7SlJXCc3poCnExT)

---

## 1. Estrutura Orgânica de Direção e Chefia (DP n.º 93/21)

O modelo de governação do **IPCAG N.º 12008 / BGO** implementa rigorosamente os **12 cargos oficiais** previstos no **Decreto Presidencial n.º 93/21**:

| Nível Hierárquico | Código RBAC | Cargo Oficial (DP n.º 93/21) | Responsabilidade Nuclear no SGE |
| :--- | :---: | :--- | :--- |
| **Direção Executiva** | `DIR_GERAL` | Director Geral | Homologação final de Pautas, Atas de PAP, Diplomas, Bolsas e Despachos de Exceção. |
| **Direção Executiva** | `SUB_PED` | Subdirector Pedagógico | Supervisão académica, Matrizes Curriculares, Conselhos de Notas e Despachos de Reabertura. |
| **Direção Executiva** | `SUB_ADM` | Subdirector Administrativo | Supervisão financeira, Homologação de Fecho de Caixa, Notas de Estorno AGT e Património. |
| **Chefia de Secretaria** | `CHEFE_SEC_PED` | Chefe da Secretaria Pedagógica | Validação de matrículas, transcrições externas, `Livro/Folha/Termo` e mapas estatísticos GEPE. |
| **Operação Pedagógica** | `OP_PED` | Operador da Secretaria Pedagógica | Atendimento, inscrição no exame de admissão, matrículas e emissão de declarações/boletins. |
| **Chefia Administrativa**| `CHEFE_SEC_GER` | Chefe da Secretaria Geral | Gestão documental geral, processos individuais de funcionários e assiduidade laboral (RH). |
| **Operação Tesouraria** | `OP_TES` | Operador de Tesouraria / Caixa | Validação de Borderôs bancários, emissão de recibos AGT e fecho de caixa por turno. |
| **Coordenação Média** | `COORD_CURSO` | Coordenador de Curso Técnico | Supervisão técnica do curso (10ª–13ª), Estágio Curricular Supervisionado e Bancas de PAP. |
| **Coordenação Média** | `COORD_DISC` | Coordenador de Disciplina | Gestão da dosificação programática trimestral e matrizes de provas (`NPT`). |
| **Coordenação Média** | `COORD_TURNO` | Coordenador de Turno | Controlo disciplinar e de assiduidade docente nos turnos da Manhã e da Tarde (12 salas). |
| **Gestão de Turma** | `DIR_TURMA` | Director de Turma | Único perfil docente autorizado a justificar faltas dos alunos da sua turma (`RN-03`). |
| **Docência** | `PROF` | Professor | Lançamento de sumários, faltas diárias e notas (`MAC`, `NPP`, `NPT`) nas suas turmas ativas. |

---

## 2. Ciclo de Vida Académico do Ensino Técnico-Profissional (10ª à 13ª Classe)

1. **Admissão à 10ª Classe (DE n.º 361/26):** Inscrição de candidatos, atribuição de **Código de Anonimato**, correção cega das provas, descodificação pública e apuramento por cota das 12 salas (ver [[02 - Fluxos de Trabalho#Fluxo 01 Configuração do Ano Letivo e Concurso de Admissão à 10ª Classe (DE n.º 361/26)|Fluxo 01]]).
2. **Regime Curricular em 3 Trimestres (10ª, 11ª e 12ª Classes):** Avaliação contínua (`MAC`), prova do professor (`NPP`) e prova trimestral (`NPT`), com congelamento do `N.º de Ordem na Turma` após o fecho do I Trimestre (`RN-05`).
3. **Transição com Deficiências (Cadeiras em Atraso):** Controlo de disciplinas não aprovadas em classes anteriores e inscrição em **Exame Extraordinário** (`RN-02`).
4. **Regime Especial da 13ª Classe (DP n.º 167/23):** Realização do **Estágio Curricular Supervisionado** e defesa da **Prova de Aptidão Profissional (PAP)** perante júri homologado, culminando no cálculo da `MFC` e emissão do Diploma e Certificado com registo em `Livro, Folha e Termo`.
