---
title: "ATA-HOM-01 — Homologação das Decisões da Especificação v2.0"
aliases:
  - "ATA-HOM-01"
  - "Ata de Homologacao v2.0"
created: 2026-11-09
updated: 2026-11-09
status: rascunho
version: "0.1"
doc_id: "ATA-HOM-01"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tipo_sessao: "homologação de decisões"
data_sessao: "AAAA-MM-DD"
tags:
  - sge
  - ipcag-12008
  - homologacao
  - validacao
---

# `ATA-HOM-01` — Homologação das Decisões da Especificação v2.0

> [!abstract] Para que serve este documento
> É o documento a apresentar à **Comissão de Gestão do IPCAG** para homologar as **26 decisões** (`DEC-001` a `DEC-026`) tomadas durante a definição do Sistema de Gestão Escolar (SGE). Com a ata assinada, a especificação fica **congelada na versão 2.0** e pode começar a construção (Fase 5 da [[00.3 - Proposta de Organizacao Documental|ORG-00]]).
> - **Fonte das decisões:** [[12 - Registo de Decisoes e Questoes em Aberto|REG-12]] §1–§2, com o contexto, as opções e o porquê de cada uma.
> - **Perguntas ainda por responder:** [[12.1 - Indice de Questoes em Aberto|IDX-12]] e os questionários por cargo em `40 - Descoberta e Validacao/`.
> - **Antes de imprimir:** preencher a data, o local e os participantes; remover este aviso.

---

## 0. Resumo para a Direção (linguagem simples)

**O que é o SGE.** É um sistema único para a vida da escola: matrículas, notas e faltas, pautas e boletins, tesouraria e caixa, documentos oficiais, horários, comunicação com os encarregados e proteção dos dados. Funciona mesmo sem internet: os professores lançam no telemóvel e o sistema sincroniza depois.

**Como chega à escola.** Em **5 entregas**, cada uma pronta antes do momento do ano em que é precisa (`DEC-007`, `DEC-013`):

| Entrega | Pronta antes de | O que traz |
| :---: | :--- | :--- |
| **E1** | Matrículas de 2027/2028 | Estrutura do ano, matrículas e processo do aluno, balcão da tesouraria, contas de acesso, dados antigos migrados |
| **E2** | 1.ª semana de aulas | Faltas e notas, horários, declarações, cobrança de dívidas e conciliação bancária |
| **E3** | Fim do I Trimestre | Conselhos de notas, boletins com comportamento, avisos aos encarregados, painéis da Direção |
| **E4** | Maio–junho de 2028 | Deliberação anual, 13ª Classe, certificados, passagem de ano |
| **E5** | Julho–agosto de 2028 | Concurso de admissão no SGE, portal para encarregados e alunos, disciplina completa |

**O que se pede à Comissão de Gestão.**
1. **Homologar as 26 decisões** da secção 4. Cada uma pode ser aprovada, aprovada com alteração, ou rejeitada.
2. **Responder aos questionários** por cargo. Há perguntas que só a escola sabe responder, como o regime de IVA, o título jurídico da escola, o software de faturação atual, prazos, limites e textos dos documentos. Essas respostas **não atrasam** a construção, porque o sistema guarda esses valores como **parâmetros configuráveis** (`DEC-009`). Têm é de chegar antes da entrega indicada.
3. **Entregar três coisas** que a construção precisa: o **regulamento interno** (antes da E3), **pautas preenchidas do ano anterior** para confirmar as fórmulas (antes da E2) e uma cópia do **alvará ou acordo** que define o estatuto da escola.

**O que já se sabe da lei** (investigação de 2026-11-08):
- **Faturação:** a escola tem de faturar as propinas, mesmo isenta de IVA. Se estiver no Regime Geral ou Simplificado de IVA, a fatura eletrónica é obrigatória desde 1 de janeiro de 2027, e o SGE liga-se ao software certificado (`DEC-002`).
- **Avaliação:** não há regulamento de avaliação publicado para o ensino técnico. As fórmulas ficam configuráveis e são confirmadas com as pautas reais.
- **Confirmação de matrícula:** é automática, e reter a confirmação por dívida não tem base legal.

---

## 1. Identificação da Sessão

| Campo | Registo |
| :--- | :--- |
| **Ata n.º** | `ATA-HOM-01` |
| **Data, hora de início e de fim** | [AAAA-MM-DD], [hh:mm]–[hh:mm] |
| **Local** | [Sala / serviço do IPCAG] |
| **Objeto** | Homologação das decisões `DEC-001` a `DEC-026` da especificação v2.0 do SGE |
| **Versão apresentada** | Especificação `2.0-rc1` de 2026-11-09 (repositório do projeto, commit indicado na capa impressa) |
| **Moderador / secretário** | [analista responsável do projeto] |

## 2. Participantes

Os cargos seguem o mapeamento de títulos da `DEC-021`. O título impresso é o que a escola usa.

| Papel no sistema | Título na escola | Nome (só com autorização) | Presente |
| :--- | :--- | :--- | :---: |
| `DIR_GERAL` | Coordenador(a) Geral da Comissão de Gestão | | ☐ |
| `SUB_PED` | Coordenador(a) para a Área Pedagógica | | ☐ |
| `SUB_ADM` | [título; se o cargo estiver vago, as funções são exercidas pelo `DIR_GERAL` — `DEC-021`] | | ☐ |
| `CHEFE_SEC_PED` | Chefe da Secretaria Pedagógica | | ☐ |
| `CHEFE_SEC_GER` | Chefe da Secretaria Geral | | ☐ |
| Equipa | Analista responsável do projeto | | ☐ |

## 3. Ordem de Trabalhos

1. Apresentação do SGE e das 5 entregas (resumo da secção 0).
2. Homologação das decisões, uma a uma (secção 4).
3. Entrega dos questionários por cargo e combinação dos prazos (secção 5).
4. Resultado e assinaturas (secção 7).

## 4. Decisões a Homologar

Resultado: ✅ homologada · ✏️ homologada com alteração · ❌ rejeitada · ❓ adiada. **Parecer** é o cargo que dá parecer na sua área antes da homologação pelo `DIR_GERAL` (REG-12, nota de autoridade).

| # | Decisão | Tema | O que foi decidido | Parecer | Resultado | Alteração acordada |
| :---: | :---: | :--- | :--- | :---: | :---: | :--- |
| 1 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-001 — Instalação única IPCAG ou produto multi-instituição\|DEC-001]] | Instalação única ou multi-instituição | (a) Instalação única IPCAG, com dados institucionais parametrizáveis | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 2 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-002 — Faturação AGT\|DEC-002]] | Faturação AGT e emissão de documentos fiscais | (b) Integrar com software certificado pela AGT via adaptador fiscal na E1; o SGE gere caixa, semáforo, conta corrente e quitação escolar; modo de contingência assíncrono com fila de emissão; fecha Q-001, Q-002, Q-024, Q-LEG-16, Q-LEG-17 | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 3 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-003 — Portal ou aplicação para encarregados e alunos\|DEC-003]] | Portal para encarregados e alunos | (b) Portal na E5; SMS avaliado na especificação da C12 | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 4 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-004 — Horários\|DEC-004]] | Horários | (b) Registo do horário feito à mão, com importação e deteção de choques | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 5 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-005 — Pagamentos\|DEC-005]] | Pagamentos | (a) Registo manual de borderôs na E1, com conciliação bancária na C10; (b) reavaliada depois da E5 | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 6 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-006 — Alojamento\|DEC-006]] | Alojamento | (a) Servidor local + réplica na nuvem, a confirmar na Fase B | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 7 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-007 — Data de arranque\|DEC-007]] | Data de arranque | (a) Início do Ano Letivo 2027/2028, com ponto de controlo na Fase E | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 8 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-008 — Fora do âmbito\|DEC-008]] | Fora do âmbito | (a) Lista recomendada | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 9 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-009 — Avançar com pendências de validação\|DEC-009]] | Pendências de validação | Avançar para a construção; regulamento interno, recálculo de pautas e homologação resolvidos durante o projeto, com regras parametrizáveis e pontos de controlo | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 10 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-010 — Integrar os ajustes da migração no modelo de dados\|DEC-010]] | Ajustes da migração (MIG-10 `AJ-nn`) | Aceitar todos; BI opcional com pendência; conta técnica própria; consola `MOD-MIG-01` na E1 | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 11 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-011 — Pagamentos por RUPE no fecho de caixa\|DEC-011]] | RUPE no fecho de caixa | Canal próprio do caixa, sem documento fiscal do IPCAG, fora da receita e da conciliação bancária | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 12 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-012 — Alinhar permissões RBAC e RLS\|DEC-012]] | Permissões: RBAC vs RLS | O DOC-01 manda; `ADMIN_TEC` só com dados técnicos; 5 casos da Secretaria; preços para todos e bolsas só para a Tesouraria e a Direção | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 13 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-013 — Entregas e prioridades\|DEC-013]] | Entregas E1–E5 e prioridades | Saúde na E1; núcleo da C13 na E2/E3; C10 dividida em E1/E2; 3 regras de alinhamento RF ↔ US | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 14 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-014 — Critérios de aceitação da operação (C18)\|DEC-014]] | Aceitação de C18 por RNF vs US | (a) Aceitação pelas metas do RNF-08 e procedimentos do OPS-09; sem US funcionais no DOC-03; mapeamento RF ↔ RNF no DOC-07 | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 15 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-015 — Âmbito e faseamento da Central de Avisos (C12 na E3 e E5)\|DEC-015]] | Faseamento da C12: central de avisos vs portal | (b) Central de avisos interna (`US-COM-01` a `06`) na E3; canal impresso garantido e SMS complementar com teto; portal (`US-COM-07`, `08`) na E5 | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 16 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-016 — Âmbito: Avaliação de desempenho e expediente geral fora das entregas E1–E5 (Q-036, Q-039)\|DEC-016]] | Âmbito: avaliação de desempenho e expediente geral | (a) Avaliação de desempenho e expediente geral fora das entregas E1–E5 (adicionados a DEC-008 como itens 9 e 10); RF-C19-33 e US-APD-07 passam a Won't | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 17 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-017 — Governação, Operação e Sustentabilidade Financeira do SGE (Q-013)\|DEC-017]] | Governação, operação e sustentabilidade financeira | (a) IPCAG é o dono do sistema e financia custos locais, nuvem e SMS (sob teto) via receitas de propinas; operação local por ADMIN_TEC (N1/N2) e suporte N3 externo sob SLA; resiliência offline garantida | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 18 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-018 — Concurso de Admissão de 2027/2028 Fora do SGE e Importação dos Admitidos na E1 (Q-017)\|DEC-018]] | Concurso de admissão 2027/2028: fora vs no SGE | (a) Concurso de admissão 2027/2028 corre fora do SGE (portal nacional `acessoetp.ao` / listas oficiais homologadas); admitidos importados na E1 via C17 (`MIG-D06`); capacidade C02 entra na E5 para 2028/2029 | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 19 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-019 — Governação de Papéis: Ponto de Contacto APD e Separação entre Funções Pedagógicas e Financeiras (Q-APD-04, Q-C15-04)\|DEC-019]] | Governação de papéis: ponto de contacto APD e visibilidade financeira do DT | (a) Ponto de contacto APD tutelado pelo DIR_GERAL com operação pelo CHEFE_SEC_GER (sem 13º papel RBAC); DT e Professores sem acesso a dívidas nem semáforo financeiro (RN-17.3, DEC-012 confirmadas) | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 20 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-020 — Título Jurídico e Enquadramento Institucional do IPCAG (Issue #38, Q-APD-01, Q-APD-02, Q-LEG-13)\|DEC-020]] | Título jurídico e enquadramento institucional | (a) SGE desacoplado via parametros_instituicao suportando tanto acordo de gestão (DP 302/19) como parceria privada (DP 37/23); pedido de cópia do alvará/acordo remetido como HITL para questionário DSC-02 em PC-E1 (DEC-009) | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 21 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-021 — Estrutura de Direção, Comissão de Gestão e Homologações Individuais vs Colegiais (Q-028, Q-C14-14)\|DEC-021]] | Estrutura de direção: Comissão de Gestão e homologações | (a) Títulos reais mapeados em cargos_institucionais (RN-16.20); DIR_GERAL acumula SUB_ADM na vacatura transitória; homologações no SGE individuais com reautenticação e fundamentação de atas colegiais | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 22 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-022 — Modelo de Horários: Sem Desdobramentos/Aulas Conjuntas e Regime de Horário da 13ª Classe (Q-C04-07, Q-C04-14)\|DEC-022]] | Horários: desdobramentos, turmas conjuntas e regime da 13ª Classe | (a) Sem desdobramentos nem aulas conjuntas em E1–E5 (`aulas_horario` 1:1 com turma-disciplina e sala); 13ª Classe em regime tutorial de Projecto Tecnológico sem sala fixa permanente nem bloqueio de 30–32h | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 23 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-023 — Modelo de Tesouraria: Contas Bancárias da Escola e Prestações Inteiras sem Pagamento Parcial (Q-C10-07, Q-C10-16)\|DEC-023]] | Tesouraria: contas bancárias por banco e prestações inteiras | (a) Catálogo bancos_angola complementado com contas_bancarias_escola (1:N); motor opera estritamente com prestações inteiras sem pagamentos parciais de quitação (talão insuficiente vira crédito do aluno) | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 24 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-024 — Regime de Alunos da 12ª com Cadeiras em Atraso: Vínculo e Inscrição em Exames (Q-C16-06, Q-031)\|DEC-024]] | Situação de aluno da 12ª com cadeiras em atraso | (a) Deliberação CONCLUIU_12_COM_CADEIRAS_PENDENTES e proposta CONDICIONADA_13A; vínculo sem turma para exames extraordinários; desbloqueia para 13ª após eliminação (RN-02.2, RN-18.5) | `SUB_PED` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 25 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-025 — Verificação de Documentos Pré-SGE: Exclusão do Portal Público e Autenticação por Reemissão (MIG-Q20)\|DEC-025]] | Verificação de documentos emitidos antes do SGE | (a) Exclusão do portal público (US-DOC-03 restrito a códigos com hash/QR do SGE/Plataforma Nacional); verificação interna pela Secretaria Pedagógica; autenticação pública requer emissão de 2.ª via no SGE | `SUB_PED` + `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |
| 26 | [[12 - Registo de Decisoes e Questoes em Aberto#DEC-026 — Enquadramento e Parametrização do Regime de IVA do IPCAG (Q-LEG-19, Q09-02)\|DEC-026]] | Regime de IVA e obrigações fiscais do IPCAG | (a) SGE configurável multi-regime em parametros_instituicao (GERAL, SIMPLIFICADO, EXCLUSAO) com isenção material do ensino (CIVA art. 12.º n.º 1 l); NIF, regime concreto e contabilista remetidos como HITL para questionário DSC-02 em PC-E1 (DEC-009) | `SUB_ADM` | ☐✅ ☐✏️ ☐❌ ☐❓ | |

## 5. Questionários e Prazos

As perguntas de **parâmetro** não bloqueiam a homologação nem a construção (`DEC-009`): o sistema guarda os valores como configuração. Cada questionário indica o ponto de controlo (E1, E2 ou E3) até ao qual a resposta é precisa.

| Questionário (índice: [[Caderno de Questionarios por Cargo — Indice Consolidado]]) | Destinatário | Entregue em | Prazo de resposta |
| :--- | :--- | :---: | :---: |
| [[Questionario por Cargo — Direcao Geral e Comissao de Gestao\|Direção Geral e Comissão de Gestão]] | `DIR_GERAL` | | |
| [[Questionario por Cargo — Subdirecao Pedagogica\|Subdireção Pedagógica]] | `SUB_PED` | | |
| [[Questionario por Cargo — Subdirecao Administrativa e Tesouraria\|Subdireção Administrativa e Tesouraria]] | `SUB_ADM` | | |
| [[Questionario por Cargo — Secretaria Pedagogica\|Secretaria Pedagógica]] | `CHEFE_SEC_PED` | | |
| [[Questionario por Cargo — Secretaria Geral e Administracao Tecnica\|Secretaria Geral e Administração Técnica]] | `CHEFE_SEC_GER` | | |
| [[Questionario por Cargo — Coordenadores de Turno e de Curso\|Coordenadores de Turno e de Curso]] | `COORD_TURNO`, `COORD_CURSO` | | |
| [[Questionario Institucional — Direcao Provincial da Educacao e INADE\|Direção Provincial da Educação e INADE]] | (externo) | | |

**Documentos a entregar pela escola:**
- ☐ regulamento interno, antes da E3;
- ☐ 3 ou mais pautas preenchidas do ano anterior, antes da E2 (recálculo — [[Plano de Validacao de Pautas]]);
- ☐ alvará ou acordo que define o estatuto do IPCAG (`DEC-020`);
- ☐ certidão de registo fiscal com o regime de IVA (`DEC-026`).

## 6. Questões Levantadas na Sessão

| # | Questão | Quem responde | Prazo | Passada ao REG-12 |
| :---: | :--- | :--- | :---: | :---: |
| 1 | | | | ☐ |

## 7. Resultado e Aprovação

**Resultado global:** ☐ Todas homologadas ☐ Homologadas com alterações (ver secção 4) ☐ Nova sessão em [data]

Com esta homologação, a especificação do SGE passa à **versão 2.0** e fica congelada. As alterações posteriores fazem-se por pedido de alteração registado no REG-12.

| Cargo | Parecer | Assinatura | Data |
| :--- | :---: | :---: | :---: |
| `SUB_PED` | ☐ Favorável ☐ Com reservas | | |
| `SUB_ADM` (ou `DIR_GERAL` em acumulação) | ☐ Favorável ☐ Com reservas | | |
| `DIR_GERAL` — **homologa** | ☐ Homologado ☐ Homologado com alterações | | |

## 8. Depois da Sessão

> [!todo] Ao receber a ata assinada
> 1. Digitalizar a secção 7 assinada e guardá-la **fora do repositório**, porque tem assinaturas e nomes. O repositório é público.
> 2. Na coluna "Homologação da Direção" do REG-12 §1, escrever `homologada (data, ATA-HOM-01)` para cada decisão; nas decisões com alteração, abrir um pedido de alteração.
> 3. Passar todos os documentos da especificação de `2.0-rc1` para `2.0` e criar a etiqueta `v2.0` no git.

## 9. Histórico

| Versão | Data | Alteração |
| :---: | :---: | :--- |
| 0.1 | 2026-11-09 | Rascunho gerado a partir do REG-12 §1 (26 decisões), para a Fase 4 da ORG-00 |
