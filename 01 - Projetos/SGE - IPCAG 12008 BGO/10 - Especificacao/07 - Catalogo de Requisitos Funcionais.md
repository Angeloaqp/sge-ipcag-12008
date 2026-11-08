---
title: "07 - Catálogo de Requisitos Funcionais (RF por Capacidade, Prioridade e Entrega)"
aliases:
  - "07 - Catalogo de Requisitos Funcionais"
  - "Catálogo de Requisitos Funcionais"
  - "RF-07"
created: 2026-11-02
updated: 2026-11-08
status: rascunho
version: "2.0-rc2"
doc_id: "RF-07"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - requisitos
  - catalogo
  - rastreabilidade
---

# Catálogo de Requisitos Funcionais — SGE IPCAG N.º 12008 / BGO

> [!abstract] Navegação
> - **Painel Principal:** [[Inicio|Início do Vault]] | **Índice do Projeto:** [[00 - MOC SGE IPCAG 12008 BGO|MOC]] | **Plano:** [[00.1 - Plano de Engenharia de Requisitos|PLN-00]] (§2.1 capacidades, §6 entregas, §8 *Definition of Ready*) | **Mapa de integração:** [[00.2 - Mapa de Integracao v2.0|INT-V2]]
> - **Âmbito e objetivos:** [[06 - Visao e Ambito|VIS-06]] (`O-01` a `O-13`, §5.2) | **Decisões:** [[12 - Registo de Decisoes e Questoes em Aberto|REG-12]] (`DEC-001` a `DEC-009`, `Q-001` a `Q-039`)
> - **Especificação:** [[01 - Dominio e Regras]] (RN) → [[02 - Fluxos de Trabalho]] → [[03 - User Stories]] (US) → [[04 - Telas e Documentos]] (MOD, DOF) → [[05 - Modelagem de Dados]] (tabelas)
> - **Rastreabilidade e cobertura:** [[Matriz de Rastreabilidade]]
> - **Fontes:** notas de capacidade, hoje arquivadas em `99 - Arquivo/Fontes Integradas v2.0/` ([[C03 - Processo Individual do Aluno|C03]], [[C04 - Horarios e Distribuicao de Servico Docente|C04]], [[C10 - Cobranca, Relatorios Financeiros e Conciliacao|C10]], [[C12 - Comunicacao com Encarregados e Alunos|C12]], [[C13 - Disciplina e Comportamento|C13]], [[C14 - Gestao de Contas e Acesso|C14]], [[C15 - Paineis de Gestao da Direcao|C15]], [[C16 - Passagem de Ano Letivo|C16]]) · [[11 - Protecao de Dados (APD)|APD-11]] §7 · [[10 - Migracao de Dados e Implantacao|MIG-10]] §11 · [[09 - Integracoes, Infraestrutura e Operacao|OPS-09]] · [[Achados dos Documentos Reais - Lote 1|DESC-L1]] · [[Sintese das Respostas da Fase B|DESC-RESP]] · [[Verificacao das Referencias Legais|LEG-VER]] §5

> [!important] Estado deste documento
> - **Rascunho `2.0-rc1`**, criado na integração da especificação v2.0 (`DEC-009`, mapa [[00.2 - Mapa de Integracao v2.0|INT-V2]] §4). Fecha as lacunas **L4** (priorização) e **L6** (capacidades em falta) do PLN-00 do lado do catálogo.
> - A **prioridade MoSCoW** e a **entrega** são **propostas** para a Fase E do PLN-00: seguem as notas de capacidade, o PLN-00 §6 e a VIS-06 §5. Só ficam firmes com a aprovação da Direção (Fase E) e a homologação da `DEC-009` (ponto de controlo antes da E1).
> - Foi construído **a partir das fontes e do mapa**, não do estado intermédio dos DOC-01 a DOC-05 durante a integração paralela. Os números das sub-regras novas de `RN-01` a `RN-10` (ex.: `RN-01.3` prova de 2.ª chamada, `RN-09.3` crédito do talão) foram conferidos com o [[01 - Dominio e Regras|DOC-01]] `2.0-rc1` em 2026-11-03; as famílias `RN-11` a `RN-18` seguem o mapa §2.1 (`RN-P-Cxx-nn` → `RN-xx.nn`). A entrega de cada RF foi conferida com a "Distribuição das Histórias por Entrega" do [[03 - User Stories|DOC-03]] `2.0-rc1`. **Regras de alinhamento (`DEC-013`, 2026-11-05):** (1) uma US tem a entrega mais cedo e a prioridade mais alta dos RF de que é a única ou a primeira consumidora; (2) um RF de proteção de dados ou de segurança (`C14`, `C19`) vale desde a primeira entrega que o usa, mesmo que as US ligadas cheguem mais tarde (ex.: `RF-C19-19`, `RF-C19-22`); (3) um RF com partes em entregas diferentes indica as duas (ex.: `RF-C19-27`, `RF-C13-02`) e conta na primeira.
> - O DOC-01 trata a prova de 2.ª chamada e o crédito do talão nas sub-regras `RN-01.3` e `RN-09.3`; o DOC-02 e o DOC-03 citam-nas pela regra-mãe (`RN-01`, `RN-09`).
> - **Nenhuma regra, lei ou número foi inventado.** Onde falta uma fonte, o requisito fica 🟡 com a questão que o bloqueia.

---

## 1. Convenções

### 1.1 Identificador
`RF-Cxx-nn` — `Cxx` é a capacidade do PLN-00 §2.1 (C01–C20) e `nn` um número sequencial dentro da capacidade. Os identificadores já propostos nas fontes **mantêm-se**:
- `RF-C17-01` a `RF-C17-16` = os da [[10 - Migracao de Dados e Implantacao|MIG-10]] §11;
- `RF-C19-nn` = `RF-P-APD-nn` da [[11 - Protecao de Dados (APD)|APD-11]] §7.1 (mesmo número: `RF-P-APD-29` → `RF-C19-29`), como a própria APD-11 prevê.

### 1.2 Colunas

| Coluna | Conteúdo |
| :--- | :--- |
| **Requisito** | O que o sistema faz, escrito para ser verificável (um teste de aceitação consegue dizer "cumpre / não cumpre"). |
| **O** | Objetivo da [[06 - Visao e Ambito|VIS-06]] §3 (`O-01` a `O-13`). |
| **Prio.** | MoSCoW: `M` *Must*, `S` *Should*, `C` *Could*, `W` *Won't* (fora desta linha de base). |
| **Entrega** | `E1` a `E5` (PLN-00 §6; VIS-06 §5.1). "pendente (`Q-037`)" / "pendente (`Q-038`)" quando a entrega depende dessas questões. |
| **Origem** | Lei (`COR-LEG-nn`), documento real (`A-nn` = achado An do DESC-L1), entrevista (`R-nn` = requisito Rn do DESC-RESP §4; `G-nn` = entrevista), decisão (`DEC-nnn`), nota de capacidade (`CAP-Cxx`), outras notas (`MIG-10`, `OPS-09`, `APD-11`, `INT-nn`). "v1.2" = já estava na especificação v1.2. |
| **RN** | Regras do DOC-01 com a numeração final do mapa (`RN-01` a `RN-18`; sub-regras `RN-xx.y`). |
| **US** | User stories do DOC-03 (as 32 da v1.2 e as dos épicos novos `EP-PIN`, `EP-HOR`, `EP-COB`, `EP-COM`, `EP-DIS`, `EP-CTA`, `EP-PNL`, `EP-PAS`). "—" = sem US (lacuna, ver [[Matriz de Rastreabilidade]] §3). |
| **Módulo / DOF** | Ecrã (`MOD-…`) e documento oficial (`DOF-01` a `DOF-26`) do DOC-04. |
| **Tabelas** | Tabelas principais do DOC-05 (as 44 da v1.2 e as novas das notas de capacidade e da APD-11 `ALT-05-nn`). |
| **Estado** | Ver §1.3. |

### 1.3 Estado do requisito (`DEC-009`)

| Marca | Significado |
| :--- | :--- |
| `definido` | Regra com fonte (lei confirmada pela LEG-VER, documento real, prática descrita pela escola ou decisão registada) e sem valor por validar. Como todas as decisões, fica sujeito à homologação geral da `DEC-009`. |
| `🟡 PC-E1` | **Provisório** — depende da **homologação das decisões** `DEC-001`–`DEC-009` pela Comissão de Gestão (inclui a `DEC-002`, que aguarda a Direção). Ponto de controlo **antes da E1**. |
| `🟡 PC-E2` | **Provisório** — depende do **recálculo de pautas preenchidas** ([[Plano de Validacao de Pautas|VAL-01]]; fórmulas, limiares, pesos). Ponto de controlo **antes da E2**. |
| `🟡 PC-E3` | **Provisório** — depende do **regulamento interno** (C13: tipos, medidas, escala de comportamento, tolerâncias). Ponto de controlo **antes da E3**. |
| `🟡 DoR-Ex` | **Provisório** — depende de uma questão em aberto que não pertence a nenhum dos três pontos de controlo da `DEC-009`; segundo a *Definition of Ready* (PLN-00 §8), tem de estar respondida **antes da entrega `Ex`** do requisito. |

Em todos os casos 🟡 o valor é **parâmetro configurável**, nunca constante (INT-V2 §3.2), e a questão que bloqueia vem a seguir à marca.

---

## 2. Catálogo por Capacidade

### C01 — Estrutura académica e calendário
**Âmbito:** dentro · **Entrega:** E1 · **Objetivos:** `O-02`, `O-07` · **Decisões:** `DEC-001`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C01-01** | Criar o Ano Letivo com os três trimestres (datas de abertura e fecho de cada trimestre e das épocas de exame) e homologá-lo pelo `SUB_PED`; um trimestre fechado não aceita lançamentos sem reabertura. | O-02 | M | E1 | v1.2; DESC-RESP §3 (calendário real); `Q-005` | RN-01, RN-18.1 | US-GOV-01 | MOD-GOV-01 | — | `anos_letivos`, `trimestres_letivos` | definido |
| **RF-C01-02** | Registar a **Área de Formação** ("Administração e Serviços"), a **Especialidade** e os cursos (Contabilidade e Gestão, Gestão de Recursos Humanos, Gestão Empresarial, Estatística e Planeamento) e as classes 10ª–13ª. | O-07 | M | E1 | `A-05`; DESC-RESP §2; INT-V2 §3.6 | — | US-GOV-02 | MOD-GOV-02 | — | `areas_formacao`, `cursos_tecnicos` | 🟡 PC-E1 · `Q-029` |
| **RF-C01-03** | Registar a matriz curricular por curso e classe: disciplinas, componente (Sócio-Ambiental-Cultural, Científica, Técnica), tempos semanais, disciplina nuclear e, como fonte, o decreto executivo de criação do curso; homologação pelo `SUB_PED`. | O-02 | M | E1 | v1.2; `COR-LEG-23`, `COR-LEG-29` | RN-02, RN-12.2 | US-GOV-02 | MOD-GOV-02 | — | `matrizes_curriculares`, `matriz_disciplinas`, `disciplinas` | definido |
| **RF-C01-04** | Guardar o **modelo de avaliação** de cada matriz como parâmetros: componentes `MTP`/`PP`/`PT`/`PG`, fórmulas de `M1`–`M3`, `CF` e `CA`, recurso, limiares de aprovação e de deficiência, e os rótulos alternativos de impressão (`MAC`/`NPP`/`NPT`); qualquer alteração fica versionada e auditada. | O-01 | M | E1 | `A-01`, `A-02`; DESC-RESP §1; `COR-LEG-13`, `-26`, `-27`; `DEC-009`; INT-V2 §3.3 | RN-01, RN-02 | US-GOV-02 | MOD-GOV-02 | — | `matrizes_curriculares`, `parametros_avaliacao` | 🟡 PC-E2 · `Q-025`, `Q-026` |
| **RF-C01-05** | Registar as 12 salas e laboratórios com tipo e lotação. | O-02 | M | E1 | v1.2 | — | US-GOV-03 | MOD-GOV-03 | — | `salas_fisicas` | definido |
| **RF-C01-06** | Abrir turmas por classe, curso e turno (impresso como "Período"), com sala fixa, lotação parametrizável (40–45 na prática) e Director de Turma nomeado. | O-02 | M | E1 | v1.2; `A-09`, `A-16`; `R-06`, `R-22` | RN-05 | US-GOV-03 | MOD-GOV-03 | — | `turmas`, `turma_disciplinas` | definido |
| **RF-C01-07** | Guardar os **parâmetros institucionais** de uma só instalação: designação, número da instituição por tipo de documento (12008 / 8009), NIF, cabeçalho e rodapé (códigos `IPCAG.SG-ACE`, `DEE-PEEP-001-ACE`) e rótulos impressos ("Período" = Turno, "Cadeira" = Disciplina). | O-07 | M | E1 | `DEC-001`; `A-03`, `A-09`, `A-14`; `COR-LEG-05`; INT-V2 §3.5, §3.13 | RN-10.6, RN-10.7 | — | MOD-GOV-01 | DOF-01 a DOF-26 (cabeçalho) | `parametros_instituicao`, `modelos_documento` | 🟡 PC-E1 · `Q-027`, `Q-033`, `Q-035` |

### C02 — Admissão à 10ª Classe
**Âmbito:** dentro · **Entrega:** E5 (o concurso de 2027/2028 corre previsivelmente fora do SGE — `Q-017`) · **Objetivo:** `O-01` · **Decisões:** `DEC-007`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C02-01** | Configurar o quadro de vagas por curso e turno e os parâmetros do concurso: mínimo de **10 valores em cada prova**, idade mínima de **15 anos completados no ano da matrícula**, sem idade máxima legal. | O-01 | M | E5 | v1.2; `COR-LEG-08`, `COR-LEG-11`; INT-V2 §3.9 | RN-01.2 | US-ADM-01 | MOD-PED-ADM | — | `quadros_vagas_admissao` | definido |
| **RF-C02-02** | Inscrever o candidato (com opções de curso), emitir a guia do emolumento de inscrição e a ficha `DOF-01`; entregar o aviso de privacidade. | O-01 | M | E5 | v1.2; `COR-LEG-07`; APD-11 (AV-01) | RN-01.2, RN-08 | US-ADM-01 | MOD-PED-ADM | DOF-01 | `candidaturas_10a` | definido |
| **RF-C02-03** | Depois de confirmado o pagamento, gerar o código de anonimato e distribuir os candidatos pelas salas. | O-01 | M | E5 | v1.2 | RN-01.2, RN-09 | US-ADM-02 | MOD-PED-ADM | DOF-01 (talão) | `codigos_anonimato`, `candidaturas_10a` | definido |
| **RF-C02-04** | Lançar as notas das provas só pelo código de anonimato, sem acesso ao nome do candidato. | O-01 | M | E5 | v1.2 | RN-01.2 | US-ADM-03 | MOD-PED-ADM | — | `codigos_anonimato` | definido |
| **RF-C02-05** | Descodificar o anonimato, ordenar os candidatos, excluir quem tem menos de 10 numa prova e desempatar pela **menor idade**. | O-01 | M | E5 | `COR-LEG-08`, `COR-LEG-09` | RN-01.2 | US-ADM-04 | MOD-PED-ADM | DOF-02 | `candidaturas_10a`, `codigos_anonimato` | definido |
| **RF-C02-06** | Publicar a lista de selecionados até **72 h** após o teste, receber reclamações até **24 h** após a publicação, registar a decisão em **24 h** e publicar a lista definitiva. | O-01 | M | E5 | `COR-LEG-12` | RN-01.2 | US-ADM-04 | MOD-PED-ADM | DOF-02 | `candidaturas_10a` | definido |
| **RF-C02-07** | Repescagem na 2.ª opção de curso como **prática interna** que se liga ou desliga por parâmetro. | O-01 | C | E5 | `COR-LEG-10`; INT-V2 §3.9 | RN-01.2 | US-ADM-04 | MOD-PED-ADM | DOF-02 | `quadros_vagas_admissao` | 🟡 DoR-E5 · `Q-LEG-12` |

> [!note] C02 — o que fica por decidir
> Inscrição por portal (`Q-LEG-12`) e Edital do concurso (`Q-022`) não têm RF: ficam em §3.2 como candidatos. A anonimização dos não admitidos e a pauta pública minimizada são `RF-C19-14` e `RF-C19-15`.

### C03 — Matrícula e processo do aluno
**Âmbito:** dentro · **Entrega:** E1 · **Objetivos:** `O-04`, `O-05` · **Fonte principal:** [[C03 - Processo Individual do Aluno|CAP-C03]] · **Regras:** `RN-05`, `RN-06`, `RN-11`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C03-01** | Converter o candidato admitido (ou o admitido importado — `Q-017`) em aluno com **N.º de Processo Individual** vitalício e matriculá-lo na 10ª Classe. | O-05 | M | E1 | v1.2 | RN-05 | US-MAT-01 | MOD-PED-MAT | DOF-03 | `alunos`, `matriculas_anuais` | definido |
| **RF-C03-02** | Registar o Boletim de Matrícula e o de Confirmação com os **campos reais** e a **numeração anual** (`N.º nnn/AAAA-AAAA`), e imprimir o comprovativo destacável sem dados de saúde. | O-05 | M | E1 | `A-12`, `A-13`; APD-11 `ALT-04-17`; CAP-C03 | RN-11.8, RN-11.14, RN-10.6 | US-PIN-09, US-MAT-01, US-MAT-02 | MOD-PED-MAT | DOF-03 | `matriculas_anuais`, `series_numeracao_documental` | definido |
| **RF-C03-03** | Gerar a confirmação de matrícula de cada aluno aprovado como **pré-gerada `Pendente`** até à entrega dos documentos e anulá-la automaticamente **60 dias** após o início do ano (prazo parametrizável). | O-05 | M | E1 | `R-05` (G-05); `COR-LEG-15`; INT-V2 §3.11 | RN-08.3, RN-18.6 | US-MAT-02 | MOD-PED-MAT | DOF-26 | `matriculas_anuais` | 🟡 DoR-E1 · `Q-LEG-05` |
| **RF-C03-04** | Registar a transferência de entrada com a transcrição homologada do histórico externo e o documento digitalizado. | O-06 | M | E1 | v1.2 | RN-06.1, RN-11.5 | US-MAT-03 | MOD-PED-HIST | — | `historico_externo_transcricoes`, `ficheiros_digitalizados` | definido |
| **RF-C03-05** | Atribuir o N.º de Ordem pela ordem alfabética do **nome completo como no BI**, congelar a lista de chamada depois do I Trimestre, pôr as entradas tardias no fim e manter o número de quem sai. | O-02 | M | E1 | v1.2; `R-06` (G-05); INT-V2 §3.11 | RN-05, RN-05.1 | US-MAT-04 | MOD-PED-MAT | — | `matriculas_anuais` | definido |
| **RF-C03-06** | Manter o **catálogo de documentos do processo** por tipo de ingresso e classe (obrigatório?, original?, digitalização?, validade, prazo, efeito da falta), homologado pelo `SUB_PED`; o atestado médico é só o indicador "entregue / não entregue". | O-04 | M | E1 | CAP-C03; `RF-C19-07` | RN-11.2 | US-PIN-01 | MOD-PIN-03 | — | `tipos_documento_processo`, `requisitos_documentais` | 🟡 PC-E1 · lista real de documentos em falta (DESC-L1 §6) |
| **RF-C03-07** | Registar a entrega de cada documento, a conferência do original e a digitalização, com versões e resumo SHA-256; o ficheiro carregado não se edita nem se apaga. | O-04 | M | E1 | CAP-C03 | RN-11.3, RN-11.4, RN-11.5 | US-PIN-02 | MOD-PIN-02 | — | `documentos_processo_aluno`, `ficheiros_digitalizados` | definido |
| **RF-C03-08** | Validar, rejeitar (com motivo) ou dispensar (com despacho homologado) cada documento do processo. | O-04 | M | E1 | CAP-C03 | RN-11.3 | US-PIN-03 | MOD-PIN-02 | — | `documentos_processo_aluno` | definido |
| **RF-C03-09** | Mostrar a **vista única do processo individual** e alertar os documentos em falta, rejeitados ou caducados (tolerância parametrizável, 60 dias na prática); imprimir o aviso de pendências. | O-04 | M | E1 | `R-07` (G-05); CAP-C03 | RN-11.1, RN-11.6 | US-PIN-04 | MOD-PIN-01 | DOF-14 | `documentos_processo_aluno` | definido |
| **RF-C03-10** | Impedir o registo do Certificado (`DOF-10`) quando há pendência documental **bloqueante**, com resposta distinta da pendência financeira. | O-04 | M | E4 | CAP-C03 | RN-11.7, RN-08.1 | US-PIN-05, US-DOC-02 | MOD-PED-DOC | DOF-10 | `documentos_processo_aluno` | 🟡 DoR-E4 · efeito a validar (`RN-11.7`) |
| **RF-C03-11** | Alterar dados de identificação civil por **pedido com comprovativo**, aprovado pelo `CHEFE_SEC_PED`, auditado, e listar os documentos emitidos com o dado antigo. | O-04 | M | E1 | CAP-C03; `RF-C19-10` | RN-11.8 | US-PIN-06 | MOD-PIN-04 | — | `pedidos_alteracao_dados`, `alunos`, `audit_logs` | definido |
| **RF-C03-12** | Mudar ou atualizar o encarregado com histórico de vínculos e indicação de **representante legal**; manter a ligação de irmãos para o desconto. | O-04 | M | E1 | CAP-C03; `RF-C19-03` | RN-11.9, RN-07 | US-PIN-07 | MOD-PIN-04 | — | `vinculos_encarregado_aluno`, `encarregados_educacao` | definido |
| **RF-C03-13** | Emitir, anular e reemitir o **cartão de estudante** (fotografia, N.º de Processo, curso, classe, período, QR), com anulação automática na transferência ou anulação da matrícula. | O-05 | S | E1 | `R-29` (G-14); CAP-C03 | RN-11.10, RN-11.11, RN-10.3 | US-PIN-08 | MOD-PIN-05 | DOF-13 | `cartoes_estudante`, `series_numeracao_documental`, `documentos_oficiais_emitidos` | 🟡 DoR-E1 · `Q-C03-08` (formato, emolumento) |
| **RF-C03-14** | Restringir por cargo o acesso aos anexos sensíveis do processo (cópias de BI, saúde) e registar cada leitura; o "problema de saúde" fica no compartimento de saúde. | O-09 | M | E1 | `R-08` (G-04); CAP-C03; `RF-C19-05`, `RF-C19-29` | RN-11.12 | US-PIN-04 | MOD-PIN-01 | — | `ficheiros_digitalizados`, `informacao_saude_matricula`, `audit_logs` | 🟡 PC-E1 · `Q-C03-16`; `R-08` dá acesso ao DT, a APD-11 só lhe dá o alerta de emergência |
| **RF-C03-15** | Na saída do aluno, registar os originais devolvidos ao encarregado e passar o processo digital ao arquivo histórico. | O-04 | C | E1 | CAP-C03 | RN-11.13 | — | MOD-PIN-02 | DOF-09 (guia) | `documentos_processo_aluno`, `alunos` | 🟡 DoR-E1 · `Q-C03-14` |

### C04 — Horários e distribuição de serviço docente
**Âmbito:** dentro (sem geração automática — `DEC-004`, `DEC-008`) · **Entrega:** E2 · **Objetivo:** `O-02` · **Fonte principal:** [[C04 - Horarios e Distribuicao de Servico Docente|CAP-C04]] · **Regras:** `RN-12`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C04-01** | Parametrizar a grelha de tempos letivos de cada turno (número de tempos, duração, horas de início e fim, intervalos). | O-02 | M | E2 | CAP-C04; `R-22` (G-10) | RN-12.1 | US-HOR-01 | MOD-HOR-01 | — | `tempos_letivos_turno` | 🟡 DoR-E2 · `Q-012`, `Q-C04-18` (45 ou 50 min; 32 h curriculares) |
| **RF-C04-02** | Registar o calendário de dias não letivos (feriados, pausas, atividades), usado para calcular as aulas previstas. | O-02 | M | E2 | CAP-C04; `Q-005` | RN-12.12 | US-HOR-01 | MOD-HOR-01 | — | `dias_nao_letivos` | definido |
| **RF-C04-03** | Registar por professor a carga de referência, os limites e as reduções por cargo. | O-02 | M | E2 | CAP-C04 | RN-12.4 | US-HOR-02 | MOD-HOR-02 | — | `regras_carga_letiva`, `funcionarios_docentes` | 🟡 PC-E1 · limites de carga a homologar |
| **RF-C04-04** | Registar as habilitações de cada professor por disciplina e as **acumulações** (mais de metade leciona noutra escola). | O-02 | M | E2 | CAP-C04; `R-23` (G-02, G-12) | RN-12.5, RN-12.6 | US-HOR-02 | MOD-HOR-02 | — | `habilitacoes_docentes`, `acumulacoes_docentes` | definido |
| **RF-C04-05** | Registar as indisponibilidades semanais de cada professor e respeitá-las no horário. | O-02 | M | E2 | CAP-C04; `R-23` | RN-12.7 | US-HOR-02 | MOD-HOR-02 | — | `indisponibilidades_docentes` | definido |
| **RF-C04-06** | Propor (Coordenador de Curso) e homologar (`SUB_PED`) a distribuição de serviço docente com controlo de carga, criando as alocações docentes; imprimir o mapa. | O-02 | M | E2 | CAP-C04; `Q-011` (respondida — a confirmar) | RN-12.3, RN-04 | US-HOR-03 | MOD-HOR-02 | DOF-15 | `planos_distribuicao_servico`, `alocacoes_docentes` | 🟡 DoR-E2 · `Q-011`, `Q-C04-16` |
| **RF-C04-07** | Registar à mão o horário semanal da turma e detetar em tempo real choques de professor, de espaço e de turma (bloqueantes) e avisos pedagógicos (não bloqueantes). | O-02 | M | E2 | `DEC-004`; CAP-C04; `R-22` | RN-12.8, RN-12.9, RN-12.10 | US-HOR-04 | MOD-HOR-03 | — | `horarios_turma`, `aulas_horario` | definido |
| **RF-C04-08** | Validar a completude do horário (horas curriculares da matriz) e publicá-lo, gerando as aulas previstas do trimestre. | O-02 | M | E2 | CAP-C04 | RN-12.8, RN-12.11, RN-12.2 | US-HOR-05 | MOD-HOR-03 | DOF-16 | `horarios_turma`, `aulas_horario`, `aulas_registadas` | definido |
| **RF-C04-09** | Abrir o sumário e a chamada a partir da aula prevista do horário, também *offline*; o professor só acede às turmas do seu horário vigente. | O-02 | M | E2 | CAP-C04; v1.2 | RN-12.13, RN-12.17, RN-03, RN-10.4 | US-HOR-06 | MOD-HOR-04 | — | `aulas_registadas`, `sumarios_e_faltas_alunos` | definido |
| **RF-C04-10** | Designar uma substituição pontual ou registar a aula como não lecionada (sem faltas de alunos), sem alterar a alocação. | O-02 | M | E2 | CAP-C04; `R-24` | RN-12.14 | US-HOR-07 | MOD-HOR-05 | — | `aulas_registadas` | definido |
| **RF-C04-11** | Agendar e registar aulas de reposição ligadas à aula não lecionada. | O-02 | S | E2 | CAP-C04 | RN-12.15 | US-HOR-08 | MOD-HOR-05 | — | `aulas_registadas` | definido |
| **RF-C04-12** | Alterar o horário a meio do trimestre com nova versão e data de vigência, mantendo as aulas já registadas. | O-02 | M | E2 | CAP-C04; DESC-RESP §3 (ajustes em setembro) | RN-12.11 | US-HOR-09 | MOD-HOR-03 | DOF-16 | `horarios_turma` | definido |
| **RF-C04-13** | Consultar e imprimir o horário por turma, professor ou espaço e o mapa de cumprimento de aulas (previstas, dadas, não dadas, repostas). | O-02 | S | E2 | CAP-C04 | RN-12.16 | US-HOR-10 | MOD-HOR-06 | DOF-16 | `aulas_horario`, `aulas_registadas` | definido |
| **RF-C04-14** | Importar o horário elaborado numa folha de cálculo com a mesma validação de choques e relatório de erros por linha. | O-02 | S | E2 | `DEC-004`; CAP-C04 | RN-12.18 | US-HOR-11 | MOD-HOR-03 | — | `horarios_turma`, `aulas_horario` | definido |

### C05 — Assiduidade de alunos
**Âmbito:** dentro · **Entrega:** E2 · **Objetivos:** `O-01`, `O-02`, `O-08` · **Regras:** `RN-03` (tipos de falta e atrasos: ver C13)

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C05-01** | Registar a falta por **tempo letivo**; a ausência a um **tempo duplo** conta **2 faltas**. | O-02 | M | E2 | v1.2; `R-01` (G-02, G-10, G-12); INT-V2 §3.11 | RN-03.1, RN-12.13 | US-PED-02, US-HOR-06 | MOD-DOC-FAL, MOD-HOR-04 | — | `sumarios_e_faltas_alunos` | definido |
| **RF-C05-02** | Justificar faltas por formulário numerado, com categoria de motivo de uma **lista fechada**, aprovação pelo Director de Turma **e** pelo Coordenador Pedagógico e anexo clínico no compartimento de saúde. | O-01 | M | E2 | v1.2; `A-08`; `R-03` (G-11, G-14); `RF-C19-06` | RN-03.4, RN-10.6 | US-PED-02 | MOD-DOC-FAL | — | `sumarios_e_faltas_alunos`, `justificacoes_faltas`, `series_numeracao_documental`, `documentos_saude` | 🟡 DoR-E2 · `Q-032` (circuito), `Q-LEG-04` (prazo) |
| **RF-C05-03** | Quando uma justificação é aprovada, **abater a falta em todas as disciplinas afetadas** sem intervenção de cada professor. | O-02 | M | E2 | `R-03` (G-11, G-14); INT-V2 §3.11 | RN-03.4 | US-PED-02 | MOD-DOC-FAL | — | `sumarios_e_faltas_alunos` | definido |
| **RF-C05-04** | Gerar alertas internos quando o aluno atinge **80%** (e, se a escola o ativar, **50%**) do limite de faltas numa disciplina. | O-01 | M | E2 | `R-26`; CAP-C15; CAP-C12 | RN-03.5, RN-17.8 | US-PNL-08 | MOD-ALR, MOD-DOC-FAL | — | `alertas_gestao`, `sumarios_e_faltas_alunos` | 🟡 PC-E2 · `Q-C12-05` (50% e 80% ou só 80%) |
| **RF-C05-05** | Declarar a retenção por excesso de faltas injustificadas quando é ultrapassado o limite parametrizado por disciplina. | O-01 | M | E2 | v1.2; `COR-LEG-13` (sem fonte publicada) | RN-03.6 | US-PED-02 | MOD-DOC-FAL | — | `sumarios_e_faltas_alunos`, `avaliacoes_trimestrais` | 🟡 PC-E2 · `Q-LEG-01` (limite) |

### C06 — Avaliação e pautas
**Âmbito:** dentro · **Entrega:** E2 · **Objetivos:** `O-01`, `O-02`, `O-08` · **Regras:** `RN-01`, `RN-04`, `RN-10.4` · **Nomenclatura canónica:** `MTP`, `PP`, `PT`, `PG`, `M1`–`M3`, `CF`, `CA` (INT-V2 §3.3)

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C06-01** | Registar a dosificação trimestral e as **provas unificadas** (`PT`, `PG`) elaboradas pelo Coordenador de Disciplina, com **variante A (Manhã), B (Tarde)** e de 2.ª chamada, e o visto do Coordenador Pedagógico. | O-01 | M | E2 | v1.2; DESC-RESP §1; INT-V2 §3.11 | RN-01.4 | US-PED-01 | MOD-DOC-DOS | — | `dosificacoes_trimestrais`, `provas_unificadas` | definido |
| **RF-C06-02** | Lançar `MTP`, `PP` e `PT` por aluno na mini-pauta, com os rótulos de impressão do modelo (`MAC`/`NPP`/`NPT`), no telemóvel ou nos PCs da Sala de Professores. | O-02 | M | E2 | v1.2; `A-01`, `A-02`; `R-31` (G-12); `COR-LEG-26`, `-27` | RN-01 | US-PED-04 | MOD-DOC-PAU | DOF-04 | `avaliacoes_trimestrais` | 🟡 PC-E2 · `Q-026` |
| **RF-C06-03** | Calcular `M1` e `M2` = `round_med((MTP + PP + PT) / 3)` e `M3` a partir de `MTP` e `PP`, com a fórmula guardada no modelo de avaliação. | O-01 | M | E2 | `A-01`; DESC-RESP §1; INT-V2 §3.3 | RN-01 | US-PED-04 | MOD-DOC-PAU | DOF-04 | `avaliacoes_trimestrais` | 🟡 PC-E2 · `Q-025` (fórmula de `M3`) |
| **RF-C06-04** | Deixar **pendente** a célula de quem faltou à prova com motivo validado (DT + Coordenação Pedagógica) até à **prova de 2.ª chamada**, dentro do prazo parametrizado do trimestre. | O-01 | M | E2 | DESC-RESP §1; INT-V2 §3.11 | RN-01.3 | US-PED-04 | MOD-DOC-PAU | DOF-04 | `avaliacoes_trimestrais` | 🟡 PC-E2 · prazo da 2.ª chamada |
| **RF-C06-05** | Conceder e homologar a dispensa (`DISP`) numa disciplina elegível, com ajuste neutro do denominador da média e detalhe clínico só no compartimento de saúde. | O-01 | M | E2 | v1.2; `RF-C19-05` | RN-01.1 | US-PED-03 | MOD-DOC-FAL | — | `dispensas_medicas`, `documentos_saude` | 🟡 PC-E2 · `Q-LEG-01` |
| **RF-C06-06** | Substituir o professor a meio do ano sem perder notas (a mini-pauta pertence à turma × disciplina) e permitir a avocação pelo `SUB_PED`. | O-02 | M | E2 | v1.2 | RN-04, RN-04.1 | US-PED-05 | MOD-DOC-PAU | — | `alocacoes_docentes`, `avaliacoes_trimestrais` | definido |
| **RF-C06-07** | Trabalhar *offline* até **7 dias** sem perder lançamentos, sincronizar com registo de conflitos e limpar os dados do dispositivo depois da confirmação do servidor. | O-08 | M | E2 | v1.2; PLN-00 §5.3; `R-31`; `RF-C19-26` | RN-10.4, RN-16.15 | US-PED-04, US-CTA-09 | MOD-DOC-PAU | — | `operacoes_sincronizacao`, `conflitos_sincronizacao` | definido |
| **RF-C06-08** | Reabrir temporariamente uma pauta homologada só por ordem da Direção, com motivo e registo imutável. | O-01 | M | E3 | v1.2 | RN-10 | US-GOV-04 | MOD-GOV-04 | — | `reaberturas_pauta_direcao`, `audit_logs` | definido |

### C07 — Conselho de notas, transição e exames
**Âmbito:** dentro · **Entrega:** E3 (conselho trimestral, Pauta Geral) e E4 (recurso, transição, exames extraordinários) · **Objetivo:** `O-01` · **Regras:** `RN-01`, `RN-02`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C07-01** | Consolidar a turma (DT), realizar o conselho de notas trimestral e homologar a **Pauta Geral** com as categorias impressas. | O-01 | M | E3 | v1.2; `A-04`, `A-10` | RN-02.3, RN-10.7 | US-PED-06 | MOD-DOC-CON | DOF-05 | `avaliacoes_trimestrais` | 🟡 PC-E2 |
| **RF-C07-02** | Lançar a **Prova Global** no III Trimestre e calcular `CF = round_med((M1 + M2 + M3) / 3)` e `CA = round_med(CF × 0,6 + PG × 0,4)`. | O-01 | M | E4 | `A-01`; DESC-RESP §1; `COR-LEG-26`; INT-V2 §3.3 | RN-01 | US-PED-06 | MOD-DOC-CON | DOF-04, DOF-05 | `resultados_anuais_disciplina` | 🟡 PC-E2 · `Q-025` |
| **RF-C07-03** | Admitir a **Exame de Recurso** (julho) quem tem `CA < 10` e `CF ≥ 7` e calcular a nota depois do recurso pela fórmula parametrizada. | O-01 | M | E4 | DESC-RESP §1; `COR-LEG-13`, `-26` | RN-01, RN-02 | US-PED-06 | MOD-DOC-CON | DOF-05 | `resultados_anuais_disciplina` | 🟡 PC-E2 · `Q-025` (fórmula do recurso) |
| **RF-C07-04** | Propor a deliberação anual (10ª e 11ª): aprova com `CA ≥ 10`; transita com deficiência com até **2** disciplinas entre 7 e 9, salvo Língua Portuguesa e uma nuclear em simultâneo; o retido repete a classe inteira. A proposta só vale depois de homologada. | O-01 | M | E4 | DESC-RESP §1; `COR-LEG-13`; `RF-C19-21` | RN-02, RN-02.1 | US-PED-06 | MOD-DOC-CON | DOF-05 | `resultados_anuais_disciplina`, `cadeiras_em_atraso` | 🟡 PC-E2 · `Q-LEG-06` |
| **RF-C07-05** | Na 12ª Classe, deliberar sem Língua Portuguesa e sem transição com deficiência: passa à 13ª quem aprova a todas e não tem cadeiras em atraso. | O-01 | M | E4 | `A-07`; DESC-RESP §1 | RN-02.2 | US-PED-06, US-13C-01 | MOD-DOC-CON | DOF-05 | `resultados_anuais_disciplina`, `cadeiras_em_atraso` | 🟡 PC-E2 · `Q-031` (respondida — a confirmar) |
| **RF-C07-06** | Inscrever em **Exame Extraordinário** (maio) as cadeiras em atraso, com a taxa por disciplina. | O-01 | M | E4 | v1.2; DESC-RESP §1 | RN-02, RN-08 | US-DEF-01 | MOD-PED-DEF | — | `exames_extraordinarios`, `cadeiras_em_atraso` | definido |
| **RF-C07-07** | Lançar a nota do Exame Extraordinário (eliminação com nota ≥ 10), registar Livro/Folha/Termo e imprimir a pauta e o termo. | O-01 | M | E4 | v1.2; `R-17` | RN-02, RN-10.2 | US-DEF-02 | MOD-PED-DEF | DOF-07 | `exames_extraordinarios`, `cadeiras_em_atraso`, `documentos_oficiais_emitidos` | 🟡 DoR-E4 · `Q-023` (base legal do `DOF-07`) |

### C08 — Regime da 13ª Classe
**Âmbito:** dentro · **Entrega:** E4 · **Objetivos:** `O-01`, `O-06` · **Regras:** `RN-06` · **Estrutura:** Projecto Tecnológico (12ª e 13ª), Estágio (13ª), PAP = defesa do relatório (INT-V2 §3.7)

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C08-01** | Validar a aptidão do aluno para a 13ª Classe (12ª aprovada, 0 cadeiras em atraso) antes de abrir o processo da 13ª. | O-01 | M | E4 | v1.2; DESC-RESP §1 | RN-02.2, RN-06.2 | US-13C-01 | MOD-DOC-13C | — | `processos_13_classe`, `cadeiras_em_atraso` | definido |
| **RF-C08-02** | Alocar o estágio curricular a uma empresa parceira, com tutor interno e supervisor na empresa, e emitir a carta de apresentação só com os dados necessários. | O-06 | M | E4 | `R-21` (G-08); `RF-C19-27` | RN-06.2 | US-13C-01 | MOD-DOC-13C | DOF-08 (`DOF-08A`) | `processos_13_classe`, `empresas_parceiras` | definido |
| **RF-C08-03** | Avaliar o **Projecto Tecnológico** como disciplina na 12ª e na 13ª Classes. | O-01 | M | E4 | `A-06`; `COR-LEG-28` | RN-06.2 | US-13C-02 | MOD-DOC-13C | — | `processos_13_classe`, `avaliacoes_trimestrais` | 🟡 DoR-E4 · `Q-030` |
| **RF-C08-04** | Registar e homologar a nota de estágio dada pelo supervisor da empresa. | O-01 | M | E4 | v1.2; `R-21` | RN-06.2 | US-13C-02 | MOD-DOC-13C | — | `processos_13_classe` | definido |
| **RF-C08-05** | Só marcar a defesa da PAP com estágio concluído, parecer positivo do orientador, 0 cadeiras em atraso e propinas e taxa de defesa pagas. | O-01 | M | E4 | `R-20` (G-08) | RN-06.3, RN-08 | US-13C-02 | MOD-DOC-13C | — | `processos_13_classe`, `conta_corrente_propinas` | definido |
| **RF-C08-06** | Constituir o júri da PAP com membros externos (empresas), registar a ata da defesa e a nota. | O-01 | M | E4 | `R-21`; `COR-LEG-16` | RN-06.2 | US-13C-02 | MOD-DOC-13C | DOF-08 (`DOF-08B`) | `processos_13_classe`, `documentos_oficiais_emitidos` | definido |
| **RF-C08-07** | Calcular a `MFC` com pesos parametrizáveis da Média do Plano Curricular, do Estágio, do Projecto Tecnológico e da PAP. | O-01 | M | E4 | DESC-RESP §1; `COR-LEG-17`; `DEC-009` | RN-06.2 | US-13C-02 | MOD-DOC-13C | DOF-10 | `processos_13_classe` | 🟡 PC-E2 · `Q-030`, `Q-LEG-07` (pesos) |

### C09 — Emissão documental e certificação
**Âmbito:** dentro · **Entrega:** E2 (requerimento, declarações, guia, QR), E3 (boletins), E4 (certificados, registo) · **Objetivos:** `O-04`, `O-05`, `O-06` · **Regras:** `RN-08`, `RN-10`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C09-01** | Registar o **requerimento de declaração** numerado, com recibo de pedido destacável, requerente e legitimidade (aluno maior, representante legal ou terceiro autorizado). | O-05 | M | E2 | `A-11`, `A-13`; `R-16` (G-04, G-13); `RF-C19-31`; INT-V2 §3.11 | RN-10.6 | US-DOC-01 | MOD-PED-DOC | DOF-09 (`DOF-09D`) | `requerimentos_declaracao`, `series_numeracao_documental` | definido |
| **RF-C09-02** | Verificar o semáforo financeiro num **balcão único** antes de emitir um documento sujeito a taxa; a Guia de Transferência tem a exceção prevista. | O-04 | M | E2 | v1.2; `R-16`; CAP-C10 | RN-08, RN-13.8 | US-DOC-01 | MOD-PED-DOC | DOF-09 | `conta_corrente_propinas`, `documentos_oficiais_emitidos` | 🟡 DoR-E2 · `Q-034` (taxas e RUPE) |
| **RF-C09-03** | Emitir a declaração de estudante e a declaração com notas, com os campos que o efeito exige, em **≤ 5 dias úteis** (alerta antes do prazo); 2.ª via por erro da escola no mesmo prazo. | O-05 | M | E2 | `COR-LEG-20`; `R-16`; `RF-C19-30`; INT-V2 §3.10 | RN-10.5 | US-DOC-01 | MOD-PED-DOC | DOF-09 (`DOF-09A`, `DOF-09B`) | `documentos_oficiais_emitidos`, `requerimentos_declaracao` | definido |
| **RF-C09-04** | Emitir a guia de transferência de saída com os dados mínimos para a escola de destino e anular o cartão de estudante. | O-05 | M | E2 | v1.2; `RF-C19-27` | RN-10, RN-11.10 | US-DOC-01 | MOD-PED-DOC | DOF-09 (`DOF-09C`) | `documentos_oficiais_emitidos`, `cartoes_estudante` | definido |
| **RF-C09-05** | Emitir o boletim de notas trimestral e anual com faltas por tipo e comportamento; reter o boletim do aluno com dívida na reunião de entrega, se a escola mantiver a prática. | O-04 | M | E3 | v1.2; `A-01`, `A-08`; `R-12` (G-11); INT-V2 §3.11 | RN-08.2, RN-15.7 | US-DOC-01 | MOD-PED-DOC | DOF-06 | `documentos_oficiais_emitidos`, `avaliacoes_trimestrais`, `comportamento_trimestral` | 🟡 PC-E3 · `Q-C13-02` (escala do comportamento; núcleo da C13 na E3 — `DEC-013`) |
| **RF-C09-06** | Numerar cada tipo de documento por série anual numa **fonte única de numeração**, atribuída de forma atómica e sem reutilizar números. | O-06 | M | E1 | `A-13`; INT-V2 §2.4 | RN-10.6, RN-11.14 | US-PIN-09, US-DOC-01 | MOD-PED-DOC | DOF-03, DOF-09, DOF-13, DOF-21 | `series_numeracao_documental` | definido |
| **RF-C09-07** | Imprimir em cada documento o cabeçalho e o rodapé oficiais e, nos blocos de assinatura, o **título configurado** e o nome de quem tinha a atribuição na data. | O-06 | M | E1 | `A-04`, `A-14`; `COR-LEG-21`, `-22`; INT-V2 §3.4 | RN-10.7, RN-16.20 | US-CTA-15 | MOD-GOV-06 | DOF-01 a DOF-26 | `cargos_institucionais`, `atribuicoes_cargo`, `modelos_documento`, `parametros_instituicao` | 🟡 PC-E1 · `Q-028`, `Q-035` |
| **RF-C09-08** | Emitir o **Certificado** pela escola com registo de arquivo (livro de registo e/ou base de dados, número sequencial, código alfanumérico) e QR, depois de verificar as pendências financeira e documental. | O-06 | M | E4 | v1.2; `COR-LEG-18`, `-19`; `R-18` (G-01) | RN-10.2, RN-10.5, RN-08.1 | US-DOC-02 | MOD-PED-DOC | DOF-10 (`DOF-10A`) | `documentos_oficiais_emitidos` | 🟡 DoR-E4 · `Q-020` |
| **RF-C09-09** | Exportar a ficha de dados para o **Diploma**, que é emitido pelo Ministério da Educação. | O-06 | M | E4 | `COR-LEG-18`; `R-18` | RN-10.5 | US-DOC-02 | MOD-PED-DOC | DOF-10 (`DOF-10B`) | `documentos_oficiais_emitidos`, `processos_13_classe` | 🟡 DoR-E4 · `Q-021` (respondida — a confirmar) |
| **RF-C09-10** | Manter livros de registo separados para Termos de Exame, Certificados e Atas da PAP, com a numeração de cada livro. | O-06 | M | E4 | `R-17` (G-04); `COR-LEG-19` | RN-10.2 | US-DOC-02, US-DEF-02, US-13C-02 | MOD-PED-DOC | DOF-07, DOF-08, DOF-10 | `documentos_oficiais_emitidos` | definido |
| **RF-C09-11** | Registar os títulos escolares na **Plataforma Nacional de Certificação** (código e QR oficiais), por integração ou registo manual. | O-06 | S | E4 | `COR-LEG-19`; `R-17`; OPS-09 `INT-10` | RN-10.2 | — | MOD-PED-DOC | DOF-10 | `documentos_oficiais_emitidos` | 🟡 DoR-E4 · `Q-020` (âmbito e forma) |
| **RF-C09-12** | Responder no **portal público de verificação QR** com o mínimo (tipo, número, data, estado, titular, curso e classificação final nos certificados), com aviso de privacidade e registo das consultas. | O-06 | M | E2 | v1.2; `R-19` (G-01); `RF-C19-16`, `-17`; OPS-09 `INT-07` | RN-10.3 | US-DOC-03 | MOD-PUB-QR | — | `documentos_oficiais_emitidos`, `consultas_portal_verificacao` | definido |

### C10 — Tesouraria
**Âmbito:** dentro (parcial — sem gateway, sem contabilidade geral) · **Entrega:** E1 (propinas, bolsas, documentos fiscais, caixa — PLN-00 §6) e E2 (dívidas, relatórios e conciliação, antes do fim do primeiro mês de cobrança — CAP-C10 §12) · **Objetivos:** `O-03`, `O-04`, `O-05`, `O-08` · **Decisões:** `DEC-002` (aguarda Direção), `DEC-005` · **Regras:** `RN-07`, `RN-08`, `RN-09`, `RN-13`

> [!warning] Documento fiscal (`DEC-002`)
> O catálogo descreve o **documento** (Fatura, Fatura-Recibo, Recibo, Nota de Crédito — `COR-LEG-01` a `06`), não quem o emite: o SGE certificado ou o software certificado atrás de um adaptador (INT-V2 §3.8). Todos os RF que tocam o documento fiscal ficam 🟡 PC-E1 até a `DEC-002` ser decidida.

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C10-01** | Parametrizar a tabela de propinas em **10 prestações** (setembro a junho; setembro pago na matrícula) com dia de vencimento fixo, a tabela de emolumentos e a regra da multa por mora. | O-03 | M | E1 | v1.2; `R-09` (G-03); CAP-C10 | RN-13.3 | US-TES-01 | MOD-TES-TAB | — | `tabelas_precos_emolumentos`, `parametros_cobranca` | 🟡 PC-E1 · regra da multa (CAP-C10 `Q-C10`) |
| **RF-C10-02** | Conceder e homologar bolsas (50% / 100%), isenções diocesanas e descontos de irmãos, com vigência e cálculo transparente. | O-03 | M | E1 | v1.2; DESC-RESP §2 | RN-07, RN-07.1, RN-07.2 | US-TES-02 | MOD-TES-TAB | — | `beneficios_bolsas_matricula` | 🟡 PC-E1 · regras escritas de bolsas e isenções em falta (DESC-L1 §6) |
| **RF-C10-03** | Manter a conta corrente de propinas por matrícula com os estados da prestação (incluindo `Em Acordo de Pagamento`) e o semáforo financeiro. | O-04 | M | E1 | v1.2; CAP-C10 | RN-08, RN-13.1, RN-13.8 | US-TES-03, US-COB-01 | MOD-TES-CXA | — | `conta_corrente_propinas` | definido |
| **RF-C10-04** | Registar cada borderô / talão bancário uma só vez e usar o seu saldo para liquidar várias prestações ou irmãos, sem nunca ultrapassar o valor. | O-03 | M | E1 | v1.2 | RN-09.1 | US-TES-03 | MOD-TES-CXA | — | `borderos_bancarios`, `alocacoes_saldo_bordero` | definido |
| **RF-C10-05** | Guardar o excedente de um talão como **crédito do aluno** para o mês seguinte; um talão de valor inferior não quita o mês. | O-03 | M | E1 | `R-10` (G-03, G-07); INT-V2 §3.11 | RN-09.3 | US-TES-03 | MOD-TES-CXA | — | `alocacoes_saldo_bordero`, `conta_corrente_propinas` | 🟡 PC-E1 · validar em E1 |
| **RF-C10-06** | Emitir o documento fiscal do tipo legal (Fatura, Fatura-Recibo ou Recibo) com numeração sequencial por tipo e ano fiscal, NIF do IPCAG e menção do motivo de isenção, por um **ponto único de emissão**. | O-03 | M | E1 | `COR-LEG-01` a `-05`; `R-14` (G-03); `DEC-002` | RN-09 | US-TES-03 | MOD-TES-CXA | DOF-11 (`DOF-11A`, `-11D`, `-11E`) | `recibos_oficiais`, `itens_recibo` | 🟡 PC-E1 · `DEC-002`, `Q-001`, `Q-003`, `Q-004` |
| **RF-C10-07** | Corrigir só por **Nota de Crédito** e declarar fraude de borderô sem alterar nem apagar documentos; `INVALIDADO_POR_FRAUDE` qualifica o documento bancário, nunca a pessoa. | O-03 | M | E1 | v1.2; `COR-LEG-03`; `RF-C19-25` | RN-09, RN-13.20 | US-TES-04 | MOD-TES-EST | DOF-11 (`DOF-11B`) | `notas_estorno`, `borderos_bancarios` | 🟡 PC-E1 · `DEC-002` |
| **RF-C10-08** | Fechar o caixa por turno e por canal (TPA, depósito/transferência, Multicaixa Express e RUPE — `DEC-011`), com conferência pela Secretaria Geral e homologação pelo `SUB_ADM`. | O-03 | M | E1 | v1.2; `R-13` (G-03, G-06, G-07) | RN-09.2 | US-TES-05 | MOD-TES-EST | DOF-11 (`DOF-11C`) | `sessoes_fecho_caixa` | 🟡 PC-E1 · `DEC-002` (consolida documentos fiscais; canal RUPE decidido na `DEC-011`) |
| **RF-C10-09** | Fechar administrativamente o caixa de um operador ausente, com dupla autorização e menção no mapa de fecho. | O-03 | M | E1 | CAP-C10 | RN-09.4, RN-13.18 | US-COB-14 | MOD-TES-EST | DOF-11 (`DOF-11C`) | `sessoes_fecho_caixa` | definido |
| **RF-C10-10** | **Só se o SGE for o emissor** (`DEC-002` (a)): modo de contingência com documentos marcados e comunicados à AGT depois. | O-08 | C | E1 | `COR-LEG-06` | RN-09.5 | — | MOD-TES-CXA | DOF-11 | `recibos_oficiais` | 🟡 PC-E1 · `DEC-002` (passa a `M` com a opção (a), a `W` com a (b)) |
| **RF-C10-11** | Consultar a dívida de cada aluno separada em exigível, reescalonada e vincenda, com a antiguidade por escalões, incluindo dívidas de anos anteriores e de ex-alunos. | O-04 | M | E2 | CAP-C10; `R-11` | RN-13.1, RN-13.2, RN-13.10, RN-18.10 | US-COB-01 | MOD-TES-COB | — | `conta_corrente_propinas` | definido |
| **RF-C10-12** | Gerar avisos de cobrança escalonados (níveis 1, 2 e 3) só com os dados financeiros mínimos, impressos até haver outro canal. | O-03 | S | E2 | CAP-C10; `DEC-003` | RN-13.5, RN-13.6, RN-14.4 | US-COB-02 | MOD-TES-COB | DOF-17 | `avisos_cobranca`, `avisos` | 🟡 PC-E1 · níveis e prazos a homologar |
| **RF-C10-13** | Propor e homologar um **acordo de pagamento**; enquanto estiver em dia, o semáforo deixa de bloquear. | O-04 | S | E2 | CAP-C10; `R-11` | RN-13.7, RN-13.8 | US-COB-03 | MOD-TES-COB | DOF-18 | `acordos_pagamento`, `parcelas_acordo`, `parcelas_acordo_prestacoes` | 🟡 PC-E1 · quem homologa |
| **RF-C10-14** | Declarar automaticamente o incumprimento de um acordo e repor o bloqueio. | O-04 | S | E2 | CAP-C10 | RN-13.9 | US-COB-04 | MOD-TES-COB | — | `acordos_pagamento` | definido |
| **RF-C10-15** | Perdoar a multa por mora só com autorização registada e motivo. | O-03 | S | E1 | CAP-C10 | RN-13.4 | US-COB-05 | MOD-TES-COB | — | `ajustes_conta_corrente` | 🟡 PC-E1 · quem autoriza |
| **RF-C10-16** | Emitir o extrato de conta corrente para o encarregado (documento informativo, não fiscal). | O-05 | C | E2 | CAP-C10 | RN-13.6 | US-COB-06 | MOD-TES-COB | DOF-19 | `conta_corrente_propinas` | 🟡 DoR-E2 · `Q-C10-13` (emolumento?) |
| **RF-C10-17** | Relatório de receita mensal por canal, curso e turno, reprodutível e com exportação auditada. | O-03 | M | E2 | CAP-C10; `R-28` | RN-13.11, RN-13.17 | US-COB-07 | MOD-TES-REL | — | `recibos_oficiais`, `itens_recibo` | 🟡 PC-E1 · `DEC-002` (dados do documento fiscal vêm do emissor) |
| **RF-C10-18** | Relatório de dívida acumulada e taxa de inadimplência. | O-03 | M | E2 | CAP-C10; `R-28` | RN-13.11 | US-COB-08 | MOD-TES-REL | — | `conta_corrente_propinas` | definido |
| **RF-C10-19** | Relatório do custo das bolsas, dos descontos e das multas perdoadas. | O-03 | S | E2 | CAP-C10 | RN-13.12 | US-COB-09 | MOD-TES-REL | — | `beneficios_bolsas_matricula`, `ajustes_conta_corrente` | definido |
| **RF-C10-20** | Relatório de emolumentos pagos, consumidos e por consumir. | O-03 | C | E2 | CAP-C10 | RN-13.13 | US-COB-10 | MOD-TES-REL | — | `itens_recibo`, `documentos_oficiais_emitidos` | 🟡 PC-E1 · `DEC-002` (dados do documento fiscal vêm do emissor) |
| **RF-C10-21** | Importar o extrato bancário e conciliar as linhas com os borderôs registados (correspondência e diferenças). | O-03 | M | E2 | `DEC-005`; CAP-C10; OPS-09 `INT-01` | RN-13.14, RN-13.15 | US-COB-11 | MOD-TES-CON | — | `extratos_bancarios`, `linhas_extrato_bancario`, `correspondencias_conciliacao`, `periodos_conciliacao` | 🟡 DoR-E2 · `Q-007` (bancos e formato do extrato) |
| **RF-C10-22** | Tratar o borderô não encontrado ou divergente no extrato até à confirmação ou à declaração de fraude. | O-03 | M | E2 | CAP-C10 | RN-13.16 | US-COB-12 | MOD-TES-CON | — | `correspondencias_conciliacao`, `borderos_bancarios` | definido |
| **RF-C10-23** | Homologar o fecho mensal da conciliação por conta e imprimir o mapa. | O-03 | S | E2 | CAP-C10 | RN-13.19 | US-COB-13 | MOD-TES-CON | DOF-20 | `periodos_conciliacao` | definido |
| **RF-C10-24** | Distinguir os emolumentos pagos ao Estado por **RUPE** (comprovativo registado, sem documento fiscal da escola) das receitas do IPCAG. | O-03 | C | E1 | `R-15`; `A-15` | RN-08, RN-13.11 | — | MOD-TES-CXA | — | `itens_recibo` | 🟡 DoR-E1 · `Q-034` |
| **RF-C10-25** | Exportar para a Diocese de Caxito os mapas de bolsas e isenções e a lista nominal de bolseiros diocesanos. | O-03 | C | E2 | DESC-RESP §2; OPS-09 `INT-09` | RN-07 | — | MOD-TES-TAB | — | `beneficios_bolsas_matricula`, `comunicacoes_destinatarios` | 🟡 DoR-E2 · OPS-09 `Q09-15` |
| **RF-C10-26** | Conciliar automaticamente pagamentos por referência Multicaixa / gateway. | O-03 | W | fora das E1–E5 | `DEC-005` | RN-13.21 | US-COB-15 | — | — | — | fora da linha de base (`DEC-005`) |

### C11 — Recursos humanos
**Âmbito:** dentro (parcial — sem processamento salarial, `DEC-008`) · **Entrega:** E1 (cadastro) e E2 (ponto), proposta da VIS-06 §5.1 · **Objetivo:** `O-02`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C11-01** | Registar docentes e funcionários com N.º de Agente, vínculo e cargo; o cadastro é a origem da conta (C14) e da distribuição docente (C04). | O-02 | M | E1 | v1.2; `A-15`; CAP-C14 | RN-16.2 | US-DOC-04 | MOD-GER-RH | — | `funcionarios_docentes` | definido |
| **RF-C11-02** | Registar as faltas dos professores por tempo letivo (pelo Coordenador de Turno), ligadas às aulas não lecionadas. | O-02 | M | E2 | `R-24` (G-06, G-10) | RN-12.14 | US-DOC-04, US-HOR-07 | MOD-GER-RH, MOD-HOR-05 | — | `assiduidade_funcionarios`, `aulas_registadas` | definido |
| **RF-C11-03** | Registar o ponto e a assiduidade dos funcionários administrativos. | O-02 | M | E2 | v1.2 | — | US-DOC-04 | MOD-GER-RH | — | `assiduidade_funcionarios` | definido |
| **RF-C11-04** | Exportar o mapa mensal de efetividade e faltas para os descontos (salários processados fora do SGE). | O-02 | S | E2 | `R-24`; `Q-010` (respondida — a confirmar) | — | US-DOC-04 | MOD-GER-RH | — | `assiduidade_funcionarios`, `aulas_registadas` | 🟡 DoR-E2 · `Q-010` |

> [!note] C11 — avaliação de desempenho
> Fica como candidato (§3.2): depende da `Q-036`. Se entrar, aplica-se o `RF-C19-33`.

### C12 — Comunicação com encarregados e alunos
**Âmbito:** dentro · **Entrega:** portal na **E5** (`DEC-003`); central de avisos (impresso + SMS) **pendente da `Q-037`** — proposta da CAP-C12: E3 · **Objetivo:** `O-11` · **Fonte principal:** [[C12 - Comunicacao com Encarregados e Alunos|CAP-C12]] · **Regras:** `RN-14`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C12-01** | Aprovar os modelos de mensagem e recusar os que usam campos fora da lista permitida (sem notas, valores em dívida, motivos disciplinares nem saúde); avisar quando o texto excede uma SMS. | O-11 | M | pendente (`Q-037`) | CAP-C12; APD-11 §7.4 | RN-14.4 | US-COM-01 | MOD-COM-01 | — | `modelos_mensagem` | definido |
| **RF-C12-02** | Gerar avisos automáticos a partir dos gatilhos (faltas 50% e 80%, propina vencida, resultados publicados, convocatória, documento pronto), sem repetir o mesmo aviso. | O-11 | M | pendente (`Q-037`) | `R-26` (G-11, G-13); CAP-C12 | RN-14.5, RN-03.5 | US-COM-02 | MOD-COM-02 | — | `avisos`, `modelos_mensagem` | 🟡 DoR-E3 · `Q-C12-05` (limiares) |
| **RF-C12-03** | Enviar cada aviso pelo canal disponível e, se falhar ou o telefone for inválido, passá-lo para a lista de impressos do Director de Turma, com recibo de entrega. | O-11 | M | pendente (`Q-037`) | CAP-C12 | RN-14.1, RN-14.8 | US-COM-02 | MOD-COM-02 | DOF-22 | `avisos` | definido |
| **RF-C12-04** | Emitir convocatórias numeradas (o SMS não leva o motivo), registar a comparência e alertar a Direção depois de duas faltas seguidas. | O-11 | M | pendente (`Q-037`) | CAP-C12; `R-02` | RN-14.7, RN-10.6 | US-COM-03 | MOD-COM-02 | DOF-21 | `convocatorias`, `series_numeracao_documental` | definido |
| **RF-C12-05** | Verificar os telefones dos encarregados (código de confirmação), marcar os inválidos e listar os contactos a atualizar por turma. | O-11 | M | pendente (`Q-037`) | CAP-C12; `R-26` (20–30% de telefones errados) | RN-14.3 | US-COM-04 | MOD-COM-03 | — | `contactos_encarregado` | definido |
| **RF-C12-06** | Enviar SMS por fornecedor com teto mensal, alerta de consumo e relatório de envios, entregas, falhas e custos. | O-11 | S | pendente (`Q-037`) | CAP-C12; OPS-09 `INT-04` | RN-14.6 | US-COM-05 | MOD-COM-01 | — | `avisos` | 🟡 DoR-E3 · `Q-037`, `Q-C12-06` (orçamento) |
| **RF-C12-07** | Registar o consentimento e a recusa de avisos não essenciais; as convocatórias e os avisos essenciais continuam a sair. | O-11 | M | pendente (`Q-037`) | CAP-C12; `RF-C19-02` | RN-14.9 | US-COM-06 | MOD-COM-03 | — | `consentimentos` (finalidade `CON-05`) | definido |
| **RF-C12-08** | **Portal do encarregado:** ativação presencial; consulta de notas, faltas, pagamentos, horário e convocatórias dos seus educandos; descarga do boletim e do recibo com QR com a mesma regra do balcão. | O-11 | M | E5 | `DEC-003`; `R-27` (G-13); CAP-C12 | RN-14.10, RN-08 | US-COM-07, US-CTA-14 | MOD-COM-04 | DOF-06, DOF-11 | `avisos`, `consentimentos`, `usuarios_sistema` | 🟡 DoR-E5 · `Q-C12-03`, `Q-016` |
| **RF-C12-09** | **Portal do aluno:** faltas (justificadas em todas as disciplinas afetadas), horário e avisos próprios quando for maior de idade. | O-11 | S | E5 | `DEC-003`; CAP-C12 | RN-14.10, RN-14.2 | US-COM-08 | MOD-COM-04 | — | `alunos` | 🟡 DoR-E5 · `Q-C12-04` |

> [!note] C12 — fora do âmbito
> Chat livre, grupos de WhatsApp e aplicação nativa ficam fora (CAP-C12 §1.3). WhatsApp Business é `Q-C12-02` (candidato, §3.2).

### C13 — Disciplina e comportamento
**Âmbito:** dentro · **Entrega:** núcleo (tipos de falta, comportamento trimestral, catálogo) **pendente da `Q-038`** — proposta da CAP-C13: E2/E3, porque o boletim real do I Trimestre já o imprime; ocorrências, medidas e processos na **E5** (VIS-06) · **Objetivo:** `O-12` · **Fonte principal:** [[C13 - Disciplina e Comportamento|CAP-C13]] · **Regras:** `RN-15` (todas 🟡 PC-E3, regulamento interno)

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C13-01** | Distinguir a falta **por não comparência** da falta **por indisciplina**; a falta por indisciplina cria uma ocorrência ligada e não entra no circuito normal de justificação. | O-12 | M | E2 *(núcleo da C13 — `DEC-013`)* | `A-08`; `R-02` (G-10); CAP-C13 | RN-03.2, RN-15.1 | US-DIS-01, US-PED-02 | MOD-DIS-01, MOD-DOC-FAL | — | `sumarios_e_faltas_alunos`, `ocorrencias_disciplinares` | 🟡 PC-E3 · `Q-C13-03` |
| **RF-C13-02** | Parametrizar o regulamento interno: tipos de ocorrência e gravidade, medidas e quem as aplica, escala do comportamento e tolerâncias de atraso. | O-12 | M | E3 *(escala do comportamento)* / E5 *(resto do regulamento)* — `DEC-013` | CAP-C13; `DEC-009` | RN-15.4 | — | MOD-DIS-05 | — | `tipos_ocorrencia`, `medidas_disciplinares_catalogo` | 🟡 PC-E3 · `Q-C13-06` (cópia do regulamento) |
| **RF-C13-03** | Propor (DT) o comportamento de cada aluno com as ocorrências do trimestre à vista, confirmá-lo no conselho de notas e imprimi-lo no boletim; depois da homologação só muda por reabertura. | O-12 | M | E3 *(núcleo da C13 — `DEC-013`)* | `A-08`; DESC-RESP §1; CAP-C13 | RN-15.7 | US-DIS-04 | MOD-DIS-03 | DOF-06 | `comportamento_trimestral` | 🟡 PC-E3 · `Q-C13-02` (escala) |
| **RF-C13-04** | Registar entradas tardias com a tolerância do 1.º tempo; depois dela, falta de não comparência nesse tempo. | O-12 | S | E5 | `R-01`; CAP-C13 | RN-03.3, RN-15.2 | US-DIS-05 | MOD-DIS-02 | — | `atrasos_alunos` | 🟡 PC-E3 · `Q-C13-04` |
| **RF-C13-05** | Registar ocorrências em sala e no recinto (tipo, gravidade, descrição, relator, testemunhas) e imprimir a participação. | O-12 | M | E5 | `R-02` (G-10); CAP-C13 | RN-15.3 | US-DIS-02 | MOD-DIS-02 | DOF-23 | `ocorrencias_disciplinares` | 🟡 PC-E3 |
| **RF-C13-06** | Aplicar as medidas permitidas a cada cargo e recusar as que exigem processo disciplinar; notificar o Director de Turma. | O-12 | M | E5 | CAP-C13 | RN-15.5 | US-DIS-02 | MOD-DIS-02 | — | `medidas_aplicadas`, `medidas_disciplinares_catalogo` | 🟡 PC-E3 · `Q-C13-05` |
| **RF-C13-07** | Instaurar, instruir e decidir o processo disciplinar, com audição obrigatória (ou falta de comparência registada), e notificar a decisão. | O-12 | S | E5 | CAP-C13 | RN-15.6 | US-DIS-03 | MOD-DIS-04 | DOF-24 | `processos_disciplinares` | 🟡 PC-E3 · `Q-C13-06` (recurso) |
| **RF-C13-08** | Restringir o histórico disciplinar por cargo e nunca o incluir em declarações ou documentos para terceiros. | O-12 | M | E5 | CAP-C13; APD-11 `ALT-05-26` | RN-15.8 | US-DIS-06 | MOD-DIS-04 | — | `ocorrencias_disciplinares`, `processos_disciplinares` | 🟡 PC-E3 · `Q-C13-07` |

### C14 — Gestão de contas e acesso
**Âmbito:** dentro (contas externas só na E5 — `DEC-003`) · **Entrega:** E1 · **Objetivos:** `O-09`, `O-10` · **Fonte principal:** [[C14 - Gestao de Contas e Acesso|CAP-C14]] · **Regras:** `RN-16`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C14-01** | Criar a conta nominal e única de um funcionário só a partir do cadastro e de uma aprovação; prever o arranque e a substituição do papel `DIR_GERAL`. | O-09 | M | E1 | CAP-C14 | RN-16.1, RN-16.2, RN-16.4 | US-CTA-01 | MOD-GOV-06 | — | `usuarios_sistema`, `funcionarios_docentes` | definido |
| **RF-C14-02** | Ativar a conta com código presencial, definir a palavra-passe segundo a política e aceitar o termo de sigilo no primeiro acesso. | O-09 | M | E1 | CAP-C14; `RF-C19-24` | RN-16.11 | US-CTA-02 | MOD-SEG-02, MOD-SEG-04 | — | `codigos_acesso_presencial`, `usuarios_sistema` | 🟡 DoR-E1 · valores da política no RNF-08 |
| **RF-C14-03** | Atribuir cargos com escopo (turma, curso, turno) e vigência, permitindo acumulações (ex.: `PROF` + `DIR_TURMA`). | O-09 | M | E1 | CAP-C14 | RN-16.3 | US-CTA-03 | MOD-GOV-06 | — | `atribuicoes_cargo`, `cargos_institucionais` | definido |
| **RF-C14-04** | Recusar a acumulação de cargos incompatíveis (segregação de funções como controlo interno). | O-09 | M | E1 | CAP-C14; VIS-06 `R-05`; `COR-LEG-21` | RN-16.5 | US-CTA-03 | MOD-GOV-06 | — | `atribuicoes_cargo` | 🟡 PC-E1 · lista de incompatibilidades a homologar |
| **RF-C14-05** | Mudar de cargo sem perder o histórico de autoria nem deixar dados do cargo anterior no dispositivo. | O-09 | M | E1 | CAP-C14 | RN-16.3, RN-16.15 | US-CTA-04 | MOD-GOV-06 | — | `atribuicoes_cargo`, `dispositivos_autorizados` | definido |
| **RF-C14-06** | Suspender e reativar uma conta com motivo e prazo. | O-09 | S | E1 | CAP-C14 | RN-16.6, RN-16.10 | US-CTA-05 | MOD-GOV-06 | — | `usuarios_sistema` | definido |
| **RF-C14-07** | Desativar a conta na saída do funcionário, preservando a autoria, gerando as pendências (caixa aberto, mini-pautas, alocações) e recusando operações *offline* posteriores. | O-09 | M | E1 | CAP-C14 | RN-16.7, RN-16.8, RN-16.9 | US-CTA-06 | MOD-GOV-06 | — | `usuarios_sistema`, `operacoes_sincronizacao` | definido |
| **RF-C14-08** | Exigir segundo fator (MFA) à Direção, à Tesouraria e à administração técnica. | O-09 | M | E1 | CAP-C14; PLN-00 §5.3 | RN-16.12 | US-CTA-07 | MOD-SEG-02 | — | `fatores_autenticacao`, `eventos_autenticacao` | definido |
| **RF-C14-09** | Repor o acesso presencialmente, sem depender de email. | O-10 | M | E1 | CAP-C14 | RN-16.16 | US-CTA-08 | MOD-SEG-01 | — | `codigos_acesso_presencial` | definido |
| **RF-C14-10** | Autorizar o dispositivo do professor e usar um PIN local para trabalhar *offline*. | O-08 | M | E2 | CAP-C14 | RN-16.15 | US-CTA-09 | MOD-SEG-03 | — | `dispositivos_autorizados` | definido |
| **RF-C14-11** | Expirar as sessões por inatividade, com bloqueio de ecrã nos balcões (15 min proposto). | O-09 | M | E1 | CAP-C14; PLN-00 §5.3 | RN-16.13 | US-CTA-10 | MOD-SEG-02 | — | `sessoes_utilizador`, `parametros_seguranca` | 🟡 DoR-E1 · valor no RNF-08 |
| **RF-C14-12** | Pedir nova autenticação antes de cada ação crítica (homologar, estornar, reabrir, fechar caixa). | O-09 | M | E1 | CAP-C14 | RN-16.14 | US-CTA-11 | MOD-SEG-02 | — | `eventos_autenticacao` | definido |
| **RF-C14-13** | Dar à administração técnica (`ADMIN_TEC`) a gestão das contas sem acesso a notas nem a dados financeiros. | O-09 | M | E1 | CAP-C14; OPS-09 §5.5 | RN-16.17 | US-CTA-12 | MOD-SEG-01 | — | `usuarios_sistema`, `atribuicoes_cargo` | 🟡 PC-E1 · `Q-013` (quem ocupa o perfil) |
| **RF-C14-14** | Auditar todas as operações de conta e rever os acessos no início de cada ano letivo. | O-09 | S | E1 (consulta) / E4 (revisão anual) | CAP-C14 | RN-16.18, RN-16.19 | US-CTA-13 | MOD-GOV-06 | — | `eventos_autenticacao`, `audit_logs` | definido |
| **RF-C14-15** | Ativar presencialmente a conta de um encarregado no portal. | O-11 | S | E5 | `DEC-003`; CAP-C14 §11 | RN-14.10 | US-CTA-14 | MOD-COM-03 | — | `usuarios_sistema`, `codigos_acesso_presencial` | 🟡 DoR-E5 · `Q-C12-04` |
| **RF-C14-16** | Configurar os **títulos dos cargos** impressos (ex.: "Coordenadora Geral da Comissão de Gestão") e ligá-los aos papéis do sistema, com vigência. | O-09 | M | E1 | `A-04`; `COR-LEG-21`, `-22`; INT-V2 §3.4 | RN-16.20, RN-10.7 | US-CTA-15 | MOD-GOV-06 | — | `cargos_institucionais`, `atribuicoes_cargo` | 🟡 PC-E1 · `Q-028` |

### C15 — Relatórios e indicadores
**Âmbito:** dentro (parcial — sem indicadores de salários nem de património) · **Entrega:** E3 (painéis), E4 (mapas GEPE, tendências); alerta de faltas antecipado para a E2 · **Objetivo:** `O-07` · **Fonte principal:** [[C15 - Paineis de Gestao da Direcao|CAP-C15]] · **Regras:** `RN-17`

> [!warning] Tabelas da C15
> O mapa INT-V2 §2.4 diz "C15: sem tabelas; só vistas e indicadores", mas a CAP-C15 §9 propõe três tabelas no Grupo 6 (`indicadores_catalogo`, `instantaneos_indicadores`, `alertas_gestao`). O catálogo cita-as; a decisão final cabe ao [[05 - Modelagem de Dados|DOC-05]].

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C15-01** | Manter o **catálogo de indicadores** com uma só definição versionada por indicador (fórmula, fontes, denominador, cargos autorizados, limiares), aprovada pela Direção. | O-07 | M | E3 | CAP-C15 | RN-17.1, RN-17.7, RN-17.13 | — | MOD-GOV-08 | — | `indicadores_catalogo` | definido |
| **RF-C15-02** | Painel do Director Geral: receita vs. dívida, assiduidade docente e aulas não dadas, alunos em risco por faltas, pedidos pendentes há mais de 3 dias, estado das mini-pautas; valores provisórios distinguidos dos oficiais. | O-07 | M | E3 | `R-28` (G-01); CAP-C15 | RN-17.2, RN-17.4, RN-17.5, RN-17.6 | US-PNL-01 | MOD-GOV-07 | — | `instantaneos_indicadores` | definido |
| **RF-C15-03** | Painel do Subdirector Pedagógico **sem** dados financeiros. | O-07 | M | E3 | CAP-C15 | RN-17.3 | US-PNL-02 | MOD-GOV-07 | — | `instantaneos_indicadores` | definido |
| **RF-C15-04** | Painel do Subdirector Administrativo **sem** notas. | O-07 | M | E3 | CAP-C15 | RN-17.3 | US-PNL-03 | MOD-GOV-07 | — | `instantaneos_indicadores` | definido |
| **RF-C15-05** | Painéis do Coordenador de Curso, do Coordenador de Disciplina e do Coordenador de Turno, limitados ao seu escopo. | O-07 | S | E3 | CAP-C15 | RN-17.2 | US-PNL-04, US-PNL-05, US-PNL-06 | MOD-DOC-PNL | — | `instantaneos_indicadores` | definido |
| **RF-C15-06** | Painel do Director de Turma com a situação da sua turma. | O-07 | M | E3 | CAP-C15 | RN-17.2 | US-PNL-07 | MOD-DOC-PNL | — | `instantaneos_indicadores` | definido |
| **RF-C15-07** | Caixa única de alertas de gestão por destinatário (cargo + escopo), sem duplicados abertos, com estados visto e tratado. | O-07 | M | E2 | CAP-C15 | RN-17.12 | US-PNL-08, US-PNL-10 | MOD-ALR | — | `alertas_gestao` | definido |
| **RF-C15-08** | Projetar o risco de retenção por notas e listar os alunos em risco. | O-01 | S | E3 | CAP-C15 | RN-17.9, RN-02 | US-PNL-09 | MOD-GOV-07 | — | `instantaneos_indicadores` | 🟡 PC-E2 · regras de transição |
| **RF-C15-09** | Acompanhar conflitos de sincronização e dispositivos sem sincronizar há mais do que o limiar. | O-08 | M | E3 | CAP-C15 | RN-17.12, RN-10.4 | US-PNL-10 | MOD-ALR | — | `alertas_gestao`, `conflitos_sincronizacao` | definido |
| **RF-C15-10** | Guardar instantâneos para tendências e exportar indicadores sem dados nominais, com registo da exportação. | O-07 | C | E4 | CAP-C15; `RF-C19-19` | RN-17.10, RN-17.11 | US-PNL-11 | MOD-GOV-07 | — | `instantaneos_indicadores`, `audit_logs` | definido |
| **RF-C15-11** | Calcular e imprimir as estatísticas da Mini-Pauta e da Pauta Geral (positivas e negativas, transita, transita com deficiência, desistentes). | O-07 | M | E3 (I Trimestre) / E4 (anual) | `A-10`; CAP-C15 | RN-17.14, RN-02.3 | US-PNL-12 | MOD-DOC-PAU, MOD-DOC-CON | DOF-04, DOF-05 | `avaliacoes_trimestrais`, `resultados_anuais_disciplina` | 🟡 PC-E2 |
| **RF-C15-12** | Exportar os **mapas estatísticos** oficiais (PDF e Excel/CSV) por curso, classe, turno, género e idade, sem recontagem manual. | O-07 | M | E4 | v1.2; `COR-LEG-25`; DESC-RESP §2; OPS-09 `INT-06` | RN-10 | US-DOC-05 | MOD-GOV-05 | DOF-12 | `matriculas_anuais`, `alunos`, `comunicacoes_destinatarios` | 🟡 DoR-E4 · `Q-018`, `Q-LEG-15` (modelo e prazo) |

### C16 — Passagem de ano letivo
**Âmbito:** dentro · **Entrega:** E4 · **Objetivo:** `O-13` · **Fonte principal:** [[C16 - Passagem de Ano Letivo|CAP-C16]] · **Regras:** `RN-18`, `RN-05.2`, `RN-07.3`, `RN-10.8`

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C16-01** | Pôr o ano letivo em encerramento e acompanhar a lista de verificação (pautas finais, recursos, exames, dossiê de encerramento de cada turma). | O-13 | M | E4 | CAP-C16 | RN-18.2, RN-18.3, RN-10.8 | US-PAS-01 | MOD-PAS-01 | — | `encerramentos_ano_letivo` | definido |
| **RF-C16-02** | Gerar em massa a proposta de destino de cada aluno conforme a deliberação final, numa execução repetível e homologada. | O-13 | M | E4 | CAP-C16 | RN-18.5, RN-18.16 | US-PAS-02 | MOD-PAS-02 | DOF-25 | `execucoes_passagem_ano`, `propostas_confirmacao_matricula` | 🟡 PC-E2 · depende das regras de transição |
| **RF-C16-03** | Retirar a confirmação automática a quem reprovou por faltas injustificadas, deixando o reingresso por despacho. | O-13 | M | E4 | `COR-LEG-14`; `R-04` (G-02) | RN-18.5, RN-03.6 | US-PAS-02 | MOD-PAS-02 | — | `propostas_confirmacao_matricula` | definido |
| **RF-C16-04** | Transportar as cadeiras em atraso para o ano seguinte. | O-13 | M | E4 | CAP-C16; DESC-RESP §1 | RN-18.9 | US-PAS-02 | MOD-PAS-02 | — | `cadeiras_em_atraso`, `propostas_confirmacao_matricula` | 🟡 DoR-E4 · `Q-C16-06` |
| **RF-C16-05** | Planear e criar as turmas do ano seguinte; o N.º de Ordem não transita. | O-13 | M | E4 | CAP-C16 | RN-18.7, RN-18.8, RN-05.2 | US-PAS-03 | MOD-PAS-03 | — | `turmas`, `matriculas_anuais` | definido |
| **RF-C16-06** | Propor a renovação de bolsas e benefícios (nunca automática) para decisão. | O-13 | S | E4 | CAP-C16 | RN-07.3, RN-18.11 | US-PAS-04 | MOD-PAS-04 | — | `propostas_renovacao_beneficio`, `beneficios_bolsas_matricula` | definido |
| **RF-C16-07** | Homologar o encerramento, imprimir o mapa de passagem e pôr o ano encerrado só de leitura, com dois anos a coexistir na transição. | O-13 | M | E4 | CAP-C16 | RN-18.1, RN-18.4, RN-18.12 | US-PAS-05 | MOD-PAS-01 | DOF-25 | `encerramentos_ano_letivo`, `anos_letivos` | definido |
| **RF-C16-08** | Converter a proposta em confirmação de matrícula `Pendente` (pré-gerada, anulada aos 60 dias) e imprimir o aviso ao encarregado. | O-13 | M | E4 | CAP-C16; `R-05` (G-05); `COR-LEG-15` | RN-18.6, RN-08.3 | US-PAS-06 | MOD-PAS-02 | DOF-26 | `propostas_confirmacao_matricula`, `matriculas_anuais` | 🟡 DoR-E4 · `Q-LEG-05` |
| **RF-C16-09** | Manter as dívidas na matrícula de origem, liquidáveis no ano seguinte; o bloqueio da confirmação por dívida é um parâmetro que se liga ou desliga. | O-13 | M | E4 | CAP-C16; `R-11`; `COR-LEG-15` | RN-18.10, RN-08.3 | US-PAS-06 | MOD-PAS-02 | — | `conta_corrente_propinas`, `propostas_confirmacao_matricula` | 🟡 PC-E1 · bloqueio compatível com a confirmação automática |
| **RF-C16-10** | Tratar as saídas do ciclo (concluintes, transferidos, desistentes), atualizar a situação académica vitalícia e arquivar os processos. | O-13 | S | E4 | CAP-C16 | RN-18.14, RN-18.15 | US-PAS-07 | MOD-PAS-05 | — | `alunos` | definido |
| **RF-C16-11** | Retificar uma deliberação depois do encerramento com análise de impacto e registo. | O-13 | S | E4 | CAP-C16 | RN-18.13 | US-PAS-08 | MOD-PAS-02 | — | `execucoes_passagem_ano`, `audit_logs` | definido |

### C17 — Migração de dados e arranque
**Âmbito:** dentro · **Entrega:** E1 (com etapas na E2 e na E4) · **Objetivo:** `O-06` · **Fonte:** [[10 - Migracao de Dados e Implantacao|MIG-10]] §11 (IDs mantidos)

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C17-01** | Consola de migração de acesso restrito: carregar ficheiros modelo, validar e mostrar o relatório de ocorrências por linha. | O-06 | M | E1 | MIG-10 §4, §11 | RN-10 | `US-MIG-01` | MOD-MIG-01 | — | área de preparação (MIG-10 §3) | definido |
| **RF-C17-02** | Área de preparação separada da produção; nada entra em produção sem lote aprovado. | O-06 | M | E1 | MIG-10 §6.4 | RN-10 | `US-MIG-01` | MOD-MIG-01 | — | área de preparação | definido |
| **RF-C17-03** | Validar com as mesmas regras de domínio do SGE e com as regras de qualidade do MIG-10 §5. | O-06 | M | E1 | MIG-10 §5 | RN-01 a RN-10 | `US-MIG-01` | MOD-MIG-01 | — | tabelas de destino (MIG-10 §3.2) | definido |
| **RF-C17-04** | Digitação assistida numa grelha igual ao documento em papel, com alunos e disciplinas pré-carregados e totais de controlo. | O-06 | M | E1 | MIG-10 §2.2 | — | `US-MIG-02` | MOD-MIG-01 | — | área de preparação | definido |
| **RF-C17-05** | Dupla digitação cega com comparação automática e resolução das divergências por um terceiro. | O-06 | M | E1 | MIG-10 §2.2 | — | `US-MIG-02` | MOD-MIG-01 | — | área de preparação | definido |
| **RF-C17-06** | Anexar ao lote a imagem da fonte. | O-06 | S | E1 | MIG-10 §7.1 | — | `US-MIG-01`, `US-MIG-02` | MOD-MIG-01 | — | `ficheiros_digitalizados` | definido |
| **RF-C17-07** | Recarga idempotente por chave natural (repetir não duplica) e carga delta. | O-06 | M | E1 | MIG-10 §3.1 | RN-05 | `US-MIG-03` | MOD-MIG-01 | — | tabelas de destino | definido |
| **RF-C17-08** | Detetar duplicados de alunos e encarregados e fundi-los de forma controlada, com auditoria. | O-06 | M | E1 | MIG-10 §5.2; CAP-C03 §1.3 | RN-05, RN-10 | `US-MIG-03` | MOD-MIG-01 | — | `alunos`, `encarregados_educacao`, `audit_logs` | definido |
| **RF-C17-09** | Recalcular médias, deliberações e `MFC` e sinalizar as divergências face aos valores oficiais. | O-01 | M | E1 | MIG-10 §6; `DEC-009` | RN-01, RN-02, RN-06 | `US-MIG-04` | MOD-MIG-01 | — | `resultados_anuais_disciplina`, `historico_externo_transcricoes` | 🟡 PC-E2 · `Q-025` |
| **RF-C17-10** | Relatórios de reconciliação exportáveis (contagens, totais de controlo, dívida, créditos, bolsas). | O-06 | M | E1 | MIG-10 §6.1, §6.2 | RN-09 | `US-MIG-05` | MOD-MIG-01 | — | tabelas de destino | definido |
| **RF-C17-11** | Marcar a proveniência e auditar a carga, a aprovação e as correções. | O-06 | M | E1 | MIG-10 §7.1, §7.2 | RN-10 | `US-MIG-05` | MOD-MIG-01 | — | `audit_logs` | definido |
| **RF-C17-12** | Marcar os documentos gerados em ensaio com "ENSAIO — SEM VALIDADE". | O-06 | S | E1 | MIG-10 §8.4 | RN-10 | `US-MIG-05` | MOD-MIG-01 | — | `documentos_oficiais_emitidos` | definido |
| **RF-C17-13** | Ajustar um saldo migrado só com despacho do `SUB_ADM`. | O-03 | M | E1 | MIG-10 §7.4 | RN-09 | `US-MIG-05` | MOD-MIG-01 | — | `conta_corrente_propinas`, `ajustes_conta_corrente` | definido |
| **RF-C17-14** | Obrigar à conferência do histórico migrado antes da primeira certificação de cada aluno. | O-06 | M | E2 | MIG-10 §7.6 | RN-10.5 | `US-MIG-06` | MOD-MIG-01 | — | `historico_externo_transcricoes` | definido |
| **RF-C17-15** | Migrar a pedido um antigo aluno (lote individual) depois do arranque. | O-06 | S | E4 | MIG-10 §2.3 | RN-10 | `US-MIG-07` | MOD-MIG-01 | — | tabelas de destino | definido |
| **RF-C17-16** | Fechar a consola depois do último Termo de Aceitação (fica o modo a pedido) e desativar a conta técnica. | O-09 | M | E4 | MIG-10 §6.4 | RN-16.21 | `US-MIG-07` | MOD-MIG-01 | — | `usuarios_sistema` | definido |

> [!note] C17 — admitidos de 2027/2028
> Se o concurso de 2027/2028 correr fora do SGE (`Q-017`), os admitidos entram por estes RF antes das matrículas (VIS-06 §5.1).

### C18 — Operação do sistema
**Âmbito:** dentro (servidor local + réplica na nuvem — `DEC-006`) · **Entrega:** infraestrutura antes da E1; operação completa na E2 (VIS-06) · **Objetivos:** `O-08`, `O-10` · **Fontes:** [[09 - Integracoes, Infraestrutura e Operacao|OPS-09]] §5, [[08 - Requisitos Nao Funcionais|RNF-08]] · **Aceitação:** metas do RNF-08 e procedimentos do OPS-09 ([[12 - Registo de Decisoes e Questoes em Aberto#DEC-014 — Critérios de aceitação da operação (C18)|DEC-014]])

> [!info] Aceitação Técnica da Operação (DEC-014)
> Conforme a `DEC-014`, os requisitos operacionais de C18 são atributos não funcionais de engenharia geridos pelo Administrador Técnico e N3, sem ecrãs de utilizador final da escola. São aceites pelas metas do [[08 - Requisitos Nao Funcionais|RNF-08]] e procedimentos do [[09 - Integracoes, Infraestrutura e Operacao|OPS-09]], mapeados na coluna US abaixo, dispensando US no DOC-03. Lacuna `L-RF-02` fechada.

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US / Critério de Aceitação RNF | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C18-01** | Fazer cópias de segurança diárias cifradas (regra 3-2-1: nuvem e disco externo) no fecho do turno da tarde e verificar o restauro. | O-08 | M | E1 | `R-30`; OPS-09 §5.1; `DEC-006` | RN-10 | `RNF-BKP-01/05/07` (OPS-09 §5.1) | — | — | todas | 🟡 PC-E1 · `Q-006`, `Q-016` (residência dos dados) |
| **RF-C18-02** | Replicar o servidor local para a nuvem e resolver conflitos com uma autoridade central definida. | O-08 | M | E1 | `DEC-006`; OPS-09 §3.5 | RN-10.4 | `RNF-BKP-01, RNF-OFF-08` (OPS-09 §3.5) | — | — | `operacoes_sincronizacao`, `conflitos_sincronizacao` | 🟡 PC-E1 · `Q-015` |
| **RF-C18-03** | Recuperar o serviço com perda máxima de 24 h de dados e em menos de 4 h, com o procedimento ensaiado antes de cada entrega. | O-08 | M | E2 | PLN-00 §5.3; OPS-09 §5.2; RNF-08 | — | `RNF-BKP-02/03, RNF-DIS-05` (OPS-09 §5.2) | — | — | — | definido |
| **RF-C18-04** | Monitorizar o servidor, a réplica, as cópias e a sincronização e enviar alertas técnicos à administração técnica. | O-08 | S | E2 | OPS-09 §5.3 | RN-17.12 | `RNF-DIS-01, RNF-AUD-04` (OPS-09 §5.3) | MOD-SEG-01, MOD-ALR | — | `alertas_gestao` | definido |
| **RF-C18-05** | Aplicar atualizações fora dos períodos críticos do calendário (matrículas, provas, conselhos), com possibilidade de reversão. | O-08 | S | E2 | OPS-09 §5.4, §6; DESC-RESP §3 | — | `RNF-MAN-01/02/08` (OPS-09 §5.4) | MOD-SEG-01 | — | — | definido |
| **RF-C18-06** | Registar e acompanhar os pedidos de suporte dos utilizadores. | O-10 | C | E2 | OPS-09 §5.6 | — | `RNF-USA-09` (OPS-09 §5.6) | — | — | — | 🟡 DoR-E2 · `Q-013` (quem dá suporte) |
| **RF-C18-07** | Disponibilizar um ambiente de formação só com dados sintéticos ou anonimizados, para a formação por cargo (≤ 2 h por cargo). | O-10 | M | E1 | MIG-10 §9; OPS-09 §5.7; APD-11 `RNF-PRV-06`; PLN-00 §5.3 | — | `RNF-USA-01, RNF-PRV-06` (OPS-09 §5.7) | — | — | — | definido |

### C19 — Proteção de dados
**Âmbito:** dentro · **Entrega:** transversal, desde a E1 (VIS-06) · **Objetivo:** `O-09` · **Fonte:** [[11 - Protecao de Dados (APD)|APD-11]] §7.1 (`RF-C19-nn` = `RF-P-APD-nn`; entrega sugerida pela APD-11; prioridade atribuída aqui) · **Lei:** Lei n.º 22/11

| ID | Requisito | O | Prio. | Entrega | Origem | RN | US | Módulo | DOF | Tabelas | Estado |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RF-C19-01** | Guardar os avisos de privacidade em versões e registar, por titular, que aviso foi entregue, quando e a quem. | O-09 | M | E1 | APD-11 (art. 25.º; AV-01…AV-10) | RN-10 | US-APD-01 | MOD-GOV-09 | — | `avisos_privacidade`, `avisos_entregues` | definido |
| **RF-C19-02** | Registar consentimentos por finalidade (quem consentiu, versão, data, prova) e a revogação com efeito imediato. | O-09 | M | E1 | APD-11 (CON-01…CON-08) | RN-10 | US-PIN-09, US-COM-06 | MOD-GOV-09, MOD-COM-03 | DOF-03 | `consentimentos` | definido |
| **RF-C19-03** | Indicar se o encarregado é representante legal e com que título; só o representante legal dá os consentimentos de um menor. | O-09 | M | E1 | APD-11 (arts. 13.º, 14.º); `ALT-05-01` | RN-11.9 | US-PIN-07 | MOD-PIN-04 | — | `encarregados_educacao` | definido |
| **RF-C19-04** | Listar diariamente os alunos que fazem 18 anos para entregar o aviso e reconfirmar os consentimentos pelo próprio aluno. | O-09 | M | E1 | APD-11 (art. 25.º, n.º 4) | RN-10 | US-APD-01 | MOD-GOV-09 | — | `alunos`, `consentimentos` | definido |
| **RF-C19-05** | Guardar atestados e motivos clínicos num **compartimento de saúde** separado, com acesso só a `CHEFE_SEC_PED` e `SUB_PED`; os outros cargos veem só `DISP`, abrangência e estado. | O-09 | M | E1 *(compartimento; atestados da `DISP` a partir da E2 — `DEC-013`)* | APD-11 (arts. 14.º, 31.º) | RN-01.1, RN-11.12 | US-PED-03 | MOD-DOC-FAL | — | `documentos_saude`, `dispensas_medicas` | definido |
| **RF-C19-06** | Usar uma lista fechada de categorias de motivo na justificação de faltas, sem texto clínico livre. | O-09 | M | E2 | APD-11; `ALT-05-10` | RN-03.4 | US-PED-02 | MOD-DOC-FAL | — | `sumarios_e_faltas_alunos` | definido |
| **RF-C19-07** | Tratar o atestado médico da matrícula só como indicador "entregue / não entregue", sem ficheiro. | O-09 | M | E1 | APD-11 (arts. 11.º, 14.º) | RN-11.2 | US-PIN-01 | MOD-PIN-03 | — | `requisitos_documentais` | 🟡 DoR-E1 · `Q-APD-05` |
| **RF-C19-08** | Registar os pedidos dos titulares, contar o prazo de 60 dias úteis, alertar aos 40 dias e guardar a resposta e a prova de envio. | O-09 | M | E2 | APD-11 (arts. 26.º–28.º) | RN-10 | US-APD-03 | MOD-GOV-09 | — | `pedidos_titulares` | definido |
| **RF-C19-09** | Gerar o relatório de acesso do titular em PDF (dados por categoria, finalidades, destinatários, origem). | O-09 | S | E2 | APD-11 (art. 26.º) | RN-10 | US-APD-03 | MOD-GOV-09 | — | `pedidos_titulares`, `comunicacoes_destinatarios` | 🟡 DoR-E2 · `Q-APD-21` (saúde) |
| **RF-C19-10** | Ao retificar dados de identificação, listar os documentos emitidos com o dado antigo e os destinatários a notificar. | O-09 | M | E1 *(`DEC-013`: a retificação existe desde a E1 — `US-PIN-06`)* | APD-11 (art. 28.º) | RN-11.8 | US-PIN-06 | MOD-PIN-04 | — | `pedidos_alteracao_dados`, `documentos_oficiais_emitidos` | definido |
| **RF-C19-11** | Ao reemitir um documento, marcar o anterior `SUBSTITUIDO` e indicar no portal QR o substituto; recibos nunca se alteram. | O-09 | M | E2 | APD-11 (art. 28.º); `ALT-05-13` | RN-10.3, RN-09 | US-DOC-01, US-DOC-03 | MOD-PED-DOC, MOD-PUB-QR | — | `documentos_oficiais_emitidos` | 🟡 PC-E1 · `DEC-002` |
| **RF-C19-12** | Marcar um registo como `BLOQUEADO`, retirando-o das listas operacionais. | O-09 | S | E3 | APD-11 (art. 28.º) | RN-10 | US-APD-05 | MOD-GOV-09 | — | `alunos` | definido |
| **RF-C19-13** | Motor de conservação: políticas por categoria, proposta mensal de lote a eliminar ou anonimizar, aprovação pela Direção e relatório, sem reproduzir os dados eliminados. | O-09 | M | E4 (antes do fim do 1.º ano) | APD-11 (art. 11.º) | RN-10 | US-APD-06 | MOD-GOV-09 | — | `politicas_conservacao`, `execucoes_conservacao` | 🟡 DoR-E4 · prazos a validar com jurista |
| **RF-C19-14** | Anonimizar os candidatos não admitidos, mantendo os campos estatísticos. | O-09 | M | E5 | APD-11 (PC-02) | RN-01.2 | US-ADM-04 | MOD-PED-ADM | — | `candidaturas_10a` | definido |
| **RF-C19-15** | Publicar uma versão minimizada da pauta de admissão (n.º, nome, resultado), separada da versão integral. | O-09 | M | E5 | APD-11 (arts. 6.º, 11.º) | RN-01.2 | US-ADM-04 | MOD-PED-ADM | DOF-02 | `candidaturas_10a` | 🟡 DoR-E5 · `Q-APD-07` |
| **RF-C19-16** | No portal QR, mostrar só o necessário e nunca n.º de processo, BI, filiação, notas por disciplina nem nomes de funcionários. | O-09 | M | E2 | APD-11 (arts. 6.º, 11.º) | RN-10.3 | US-DOC-03 | MOD-PUB-QR | — | `documentos_oficiais_emitidos` | definido |
| **RF-C19-17** | No portal QR, apresentar o aviso de privacidade, registar cada consulta (IP truncado) e impedir a indexação. | O-09 | M | E2 | APD-11 (arts. 25.º, 30.º) | RN-10.3 | US-DOC-03 | MOD-PUB-QR | — | `consultas_portal_verificacao` | definido |
| **RF-C19-18** | Depois do prazo PC-19, responder no portal QR, para documentos sem Livro/Folha/Termo, só com a data de emissão e o contacto da Secretaria. | O-09 | S | E4 | APD-11 (art. 11.º) | RN-10.3 | US-DOC-03 | MOD-PUB-QR | — | `documentos_oficiais_emitidos` | definido |
| **RF-C19-19** | Registar cada exportação ou impressão com dados pessoais e identificar no ficheiro quem o gerou. | O-09 | M | E1 | APD-11 (arts. 30.º, 31.º) | RN-10, RN-17.11 | US-PNL-11, US-DOC-05 | MOD-GOV-05 | — | `audit_logs` | definido |
| **RF-C19-20** | Registar cada leitura de dados de saúde e de comprovativos socioeconómicos. | O-09 | M | E2 | APD-11 (art. 31.º) | RN-10, RN-11.12 | US-APD-04 | MOD-GOV-09 | — | `audit_logs` | definido |
| **RF-C19-21** | Tratar a deliberação anual e o semáforo financeiro como **propostas** até confirmação humana; desbloqueio pontual do semáforo pelo `SUB_ADM` com motivo. | O-09 | M | E1 (semáforo) / E4 (deliberação) | APD-11 (art. 29.º) | RN-02, RN-08 | US-PED-06, US-DOC-01 | MOD-DOC-CON, MOD-PED-DOC | — | `resultados_anuais_disciplina`, `conta_corrente_propinas` | definido |
| **RF-C19-22** | Registar as comunicações a destinatários externos (MED/GEPE, AGT, empresas de estágio, outras escolas, Diocese): o quê, a quem, quando, com que base. | O-09 | M | E1 | APD-11 (arts. 26.º, 28.º) | RN-10 | US-DOC-05 | MOD-GOV-09 | — | `comunicacoes_destinatarios` | definido |
| **RF-C19-23** | Registar incidentes de segurança e gerar a minuta de comunicação à APD (Circular n.º 2/2024). | O-09 | M | E1 | APD-11 (art. 30.º) | RN-10 | US-APD-02 | MOD-GOV-09 | — | `incidentes_seguranca` | definido |
| **RF-C19-24** | Exigir a aceitação do termo de sigilo no primeiro acesso e em cada nova versão. | O-09 | M | E1 | APD-11 (art. 32.º); `ALT-05-17` | RN-16.2 | US-CTA-02 | MOD-SEG-02 | — | `usuarios_sistema` | definido |
| **RF-C19-25** | Não classificar nenhum encarregado como suspeito: `INVALIDADO_POR_FRAUDE` qualifica só o documento bancário, visível a `SUB_ADM` e `DIR_GERAL`. | O-09 | M | E1 | APD-11 (art. 15.º); `ALT-05-16` | RN-09 | US-TES-04 | MOD-TES-EST | — | `borderos_bancarios` | 🟡 DoR-E1 · `Q-APD-17` |
| **RF-C19-26** | Apagar no dispositivo as operações confirmadas pelo servidor e a lista de alunos quando a alocação termina; ordenar a limpeza remota. | O-09 | M | E2 | APD-11 (arts. 30.º, 31.º); `ALT-05-20` | RN-10.4, RN-16.15 | US-CTA-09 | MOD-SEG-03 | — | `operacoes_sincronizacao`, `dispositivos_autorizados` | definido |
| **RF-C19-27** | Incluir nos documentos para terceiros (carta de estágio, guia de transferência) só os dados necessários. | O-09 | M | E2 *(guia de transferência)* / E4 *(carta de estágio)* — `DEC-013` | APD-11 (arts. 6.º, 22.º) | RN-10 | US-13C-01, US-DOC-01 | MOD-DOC-13C, MOD-PED-DOC | DOF-08, DOF-09 | `documentos_oficiais_emitidos` | 🟡 DoR-E4 · `Q-APD-18` |
| **RF-C19-28** | Guardar a finalidade de cada fotografia; exportá-la para divulgação exige o consentimento CON-03. | O-09 | M | E1 | APD-11 (art. 9.º); `ALT-05-02` | RN-11.11 | US-PIN-08 | MOD-PIN-05 | DOF-13 | `alunos`, `consentimentos` | definido |
| **RF-C19-29** | Tornar facultativo o "problema de saúde" da matrícula, com consentimento CON-07, validade de um ano e alerta de emergência resumido ao DT e ao Coordenador de Turno; nunca impresso. | O-09 | M | E1 | APD-11 (arts. 14.º, 31.º); `A-12`; `ALT-05-22` | RN-11.8, RN-11.12 | US-PIN-09 | MOD-PED-MAT | DOF-03 | `informacao_saude_matricula` | definido |
| **RF-C19-30** | Imprimir na declaração de estudante só os campos do efeito escolhido, segundo a tabela "efeito → campos" aprovada pela Direção. | O-09 | M | E2 | APD-11; `A-11` | RN-10.5 | US-DOC-01 | MOD-PED-DOC | DOF-09 | `requerimentos_declaracao` | 🟡 DoR-E2 · `Q-APD-30` |
| **RF-C19-31** | Registar no requerimento o requerente e a sua legitimidade e entregar a declaração só a quem a tem. | O-09 | M | E2 | APD-11 (arts. 22.º, 26.º); `A-11`; `ALT-05-25` | RN-10.6 | US-DOC-01 | MOD-PED-DOC | DOF-09 | `requerimentos_declaracao` | definido |
| **RF-C19-32** | Recolher a ocupação ou local de trabalho do pai só se a Direção confirmar uma finalidade (campo facultativo, CON-08, nunca impresso); sem finalidade, o campo não existe. | O-09 | C | E1 | APD-11; `A-12`; `ALT-05-23` | RN-11.8 | US-PIN-09 | MOD-PED-MAT | — | `alunos` | 🟡 PC-E1 · `Q-APD-29` |
| **RF-C19-33** | Se a avaliação de desempenho entrar no SGE: visível só ao avaliado, ao avaliador e a quem homologa, com concordância e observação do avaliado. | O-09 | C | a definir (`Q-036`) | APD-11; `A-15`; `ALT-05-24` | — | US-APD-07 | MOD-GER-RH | — | `avaliacoes_desempenho` *(tabela condicional, não criada no DOC-05 — `ALT-05-24`)* | 🟡 condicional · `Q-036` |

### C20 — Recursos e património
**Fora do âmbito** (`DEC-008`): sem RF. Ver §3.1.

---

## 3. Fora do Âmbito e Candidatos

### 3.1 Capacidades e funções fora do âmbito (`DEC-008` e decisões ligadas)

Não têm RF. Só entram por pedido de alteração registado no [[12 - Registo de Decisoes e Questoes em Aberto|REG-12]] (VIS-06 §5.3).

| # | Fora do âmbito | Capacidade | Decisão | Como continua |
| :---: | :--- | :---: | :--- | :--- |
| F-01 | Processamento salarial | C11 | `DEC-008` | Fora do SGE; o SGE exporta o mapa de efetividade (`RF-C11-04`; `Q-010`) |
| F-02 | Biblioteca, inventário e património, gestão de laboratórios | **C20** | `DEC-008` | Fora do SGE (`Q-019`) |
| F-03 | Cantina | — | `DEC-008` | Fora do SGE |
| F-04 | Transporte escolar | — | `DEC-008` | Fora do SGE |
| F-05 | Contabilidade geral | C10 | `DEC-008` | O SGE fornece a Conta Corrente, a Tesouraria e o fecho de caixa |
| F-06 | Geração automática de horários | C04 | `DEC-004`, `DEC-008` | Horário feito à mão e registado ou importado (`RF-C04-07`, `RF-C04-14`) |
| F-07 | Ensino a distância e conteúdos pedagógicos | — | `DEC-008` | Fora do SGE |
| F-08 | Compras e stocks | — | `DEC-008` | Fora do SGE |
| F-09 | Várias escolas com dados separados | C01 | `DEC-001` | Instalação única com parâmetros institucionais (`RF-C01-07`) |
| F-10 | Contas e portal para encarregados e alunos antes da E5 | C12, C14 | `DEC-003` | Balcão; portal na E5 (`RF-C12-08`, `RF-C12-09`, `RF-C14-15`) |
| F-11 | Referências Multicaixa / gateway | C10 | `DEC-005` | Borderô manual e conciliação por extrato; `RF-C10-26` fica `W` |
| F-12 | Alojamento só na nuvem ou só local | C18 | `DEC-006` | Servidor local + réplica na nuvem |

### 3.2 Candidatos (por decidir — sem RF até à decisão)

| ID | Candidato | Origem | Decisão pendente | Se for aceite |
| :---: | :--- | :--- | :--- | :--- |
| **CAND-01** | **Expediente geral e correspondência:** registo de ofícios de entrada e saída, `Ofício N.º [seq]/IPCAG.SG/ano`, hoje feito à mão pela Secretaria Geral. Não está no mapa C01–C20. | `R-25` (G-06); INT-V2 §5 | **`Q-039`** (nova capacidade C21? em que entrega?) | Capacidade `C21` com RF `RF-C21-nn`, numeração na fonte única (`series_numeracao_documental`), cargo `CHEFE_SEC_GER` |
| CAND-02 | Avaliação de desempenho anual do pessoal (10 indicadores, homologação pelo Gabinete Provincial) | `A-15` | `Q-036` | RF na C11 + `RF-C19-33` |
| CAND-03 | Edital do concurso de admissão | `Q-022` | `Q-022` | RF na C02 e novo DOF |
| CAND-04 | Inscrição no concurso por portal | `Q-LEG-12` | `Q-LEG-12`; `DEC-003` | RF na C02 (E5) |
| CAND-05 | Canal WhatsApp Business (nunca grupos de turma) | CAP-C12 | `Q-C12-02` | RF na C12 |
| CAND-06 | Estado `ARQUIVADO` do processo do aluno | CAP-C16 (`RN-18.15.3`) | depende da C19 (conservação) | RF na C16 (`Could`) |

---

## 4. Resumo

**224 RF** em 19 capacidades (C01–C19): 222 na linha de base, mais o `RF-C10-26` (fora da linha de base, `DEC-005`) e o `RF-C19-33` (condicional, `Q-036`); C20 fora; 1 candidato a capacidade nova (`CAND-01`, `Q-039`). Um RF com duas entregas (ex.: `RF-C14-14` "E1 / E4") conta na primeira.

### 4.1 Por capacidade

| Capacidade | RF | M | S | C | W | E1 | E2 | E3 | E4 | E5 | Pendente / outra |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| C01 Estrutura académica | 7 | 7 | — | — | — | 7 | — | — | — | — | — |
| C02 Admissão | 7 | 6 | — | 1 | — | — | — | — | — | 7 | — |
| C03 Matrícula e processo | 15 | 13 | 1 | 1 | — | 14 | — | — | 1 | — | — |
| C04 Horários | 14 | 11 | 3 | — | — | — | 14 | — | — | — | — |
| C05 Assiduidade | 5 | 5 | — | — | — | — | 5 | — | — | — | — |
| C06 Avaliação e pautas | 8 | 8 | — | — | — | — | 7 | 1 | — | — | — |
| C07 Conselho, transição, exames | 7 | 7 | — | — | — | — | — | 1 | 6 | — | — |
| C08 13ª Classe | 7 | 7 | — | — | — | — | — | — | 7 | — | — |
| C09 Emissão documental | 12 | 11 | 1 | — | — | 2 | 5 | 1 | 4 | — | — |
| C10 Tesouraria | 26 | 14 | 6 | 5 | 1 | 12 | 13 | — | — | — | 1 fora (`DEC-005`) |
| C11 Recursos humanos | 4 | 3 | 1 | — | — | 1 | 3 | — | — | — | — |
| C12 Comunicação | 9 | 7 | 2 | — | — | — | — | — | — | 2 | 7 pendentes (`Q-037`) |
| C13 Disciplina | 8 | 6 | 2 | — | — | — | 1 | 2 | — | 5 | — |
| C14 Contas e acesso | 16 | 13 | 3 | — | — | 14 | 1 | — | — | 1 | — |
| C15 Relatórios e indicadores | 12 | 9 | 2 | 1 | — | — | 1 | 9 | 2 | — | — |
| C16 Passagem de ano | 11 | 8 | 3 | — | — | — | — | — | 11 | — | — |
| C17 Migração | 16 | 13 | 3 | — | — | 13 | 1 | — | 2 | — | — |
| C18 Operação | 7 | 4 | 2 | 1 | — | 3 | 4 | — | — | — | — |
| C19 Proteção de dados | 33 | 28 | 3 | 2 | — | 16 | 11 | 1 | 2 | 2 | 1 a definir (`Q-036`) |
| **Total** | **224** | **180** | **32** | **11** | **1** | **82** | **66** | **15** | **35** | **17** | **9** |

### 4.2 Por entrega e prioridade

| Entrega | M | S | C | W | Total |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **E1** — Arrancar o ano | 72 | 6 | 4 | — | **82** |
| **E2** — I Trimestre | 50 | 12 | 4 | — | **66** |
| **E3** — Fecho de trimestre | 12 | 3 | — | — | **15** |
| **E4** — Fecho do ano | 28 | 6 | 1 | — | **35** |
| **E5** — Próximo ciclo | 12 | 4 | 1 | — | **17** |
| Pendente (`Q-037`: 7) | 6 | 1 | — | — | **7** |
| A definir (`Q-036`) | — | — | 1 | — | **1** |
| Fora da linha de base (`DEC-005`) | — | — | — | 1 | **1** |
| **Total** | **180** | **32** | **11** | **1** | **224** |

> [!warning] Peso da E1
> A E1 concentra 82 RF (72 `Must`), porque junta a estrutura académica, a matrícula, a tesouraria, as contas, a migração e a base da proteção de dados. Se o prazo de 2027/2028 apertar, os candidatos a sair da E1 são os 10 `Should`/`Could` e, dentro dos `Must`, os que dependem da `DEC-002` (`RF-C10-06`, `RF-C10-07`). Se a `Q-037` e a `Q-038` forem aceites, a E3 ganha até 10 RF.

### 4.3 Por estado (`DEC-009`)

| Estado | RF | Ponto de controlo |
| :--- | :---: | :--- |
| `definido` | 136 | — |
| `🟡 PC-E1` | 22 | Homologação das decisões e `DEC-002` — antes da E1 |
| `🟡 PC-E2` | 17 | Recálculo de pautas — antes da E2 |
| `🟡 PC-E3` | 9 | Regulamento interno — antes da E3 |
| `🟡 DoR-E1` … `DoR-E5` | 38 (E1 9, E2 11, E3 2, E4 11, E5 5) | Questão respondida antes da entrega do RF |
| `🟡 condicional` | 1 | `RF-C19-33` (`Q-036`) |
| fora da linha de base | 1 | `RF-C10-26` (`DEC-005`) |
| **Total 🟡** | **87** | |

### 4.4 Cobertura (detalhe na [[Matriz de Rastreabilidade]])
- **0** objetivos sem RF; **0** capacidades dentro do âmbito sem RF; **0** das 130 US sem RF.
- **8 RF sem US:** `RF-C01-07`, `RF-C03-15`, `RF-C09-11`, `RF-C10-10`, `RF-C10-24`, `RF-C10-25`, `RF-C13-02`, `RF-C15-01` *(os 16 RF de C17 foram cobertos por `US-MIG-01` a `US-MIG-07` — Issue #13; os 7 RF de C18 são aceites pelas metas do RNF-08 e procedimentos do OPS-09 conforme `DEC-014` — Issue #14; os 9 RF de C19 foram cobertos por `US-APD-01` a `US-APD-07` — Issue #15)*.
- **22 RF sem módulo** no DOC-04 (consola de migração e operação).
- ~~**68 tabelas** citadas ainda não estão no DOC-05 (v1.2 em 2026-11-03); a C15 tem tabelas na nota de capacidade mas não no mapa INT-V2 §2.4.~~ **Fechado em 2026-11-05:** o DOC-05 `2.0-rc1` tem as 116 tabelas e a C15 está no Grupo 6; só `avaliacoes_desempenho` fica condicional (`Q-036`).

---

## 5. Histórico de Alterações

| Versão | Data | Alteração |
| :---: | :---: | :--- |
| 2.0-rc1 | 2026-11-03 | Criação na integração v2.0 (`DEC-009`, INT-V2 §4): 224 RF para C01–C19 a partir das notas de capacidade, da APD-11 §7.1 (`RF-C19-nn`), da MIG-10 §11 (`RF-C17-nn`), da OPS-09, do DESC-L1 (A1–A16), do DESC-RESP (R1–R31), da LEG-VER §5 (`COR-LEG`) e do REG-12; prioridade MoSCoW e entrega propostas para a Fase E; estado segundo os pontos de controlo da `DEC-009`; fora do âmbito e candidatos (`CAND-01` expediente geral — `Q-039`); resumo; [[Matriz de Rastreabilidade]]. |
| 2.0-rc1 | 2026-11-05 | Correções da verificação [[00.4 - Relatorio de Verificacao v2.0-rc1\|VER-01]]: `RF-P-APD`/`RNF-P-APD` → IDs finais (#1); coluna Tabelas atualizada e `consentimentos` (#2); §4.4 e fontes atualizadas (#10) |
| 2.0-rc1 | 2026-11-05 | Decisão [[12 - Registo de Decisoes e Questoes em Aberto#DEC-013 — Entregas e prioridades\|DEC-013]]: regras de alinhamento (§0); `RF-C19-05`/`-10` na E1; `RF-C19-27` e `RF-C13-02` com duas entregas; núcleo da C13 na E2/E3; `RF-C05-03` sem `US-COM-08`; `RF-C19-02` liga a `US-PIN-09`; regra 🟡 da `DEC-002` aplicada a `RF-C10-08`, `-17`, `-20` e `RF-C19-11`; §4 recalculado |
| 2.0-rc2 | 2026-11-08 | Cobertura de C17: preenchida a coluna US para `RF-C17-01` a `RF-C17-16` com o novo Épico 16 (`US-MIG-01` a `US-MIG-07`, DOC-03) — Issue #13. |
| 2.0-rc2 | 2026-11-08 | Aceitação de C18: associados os 7 RF de C18 aos respetivos requisitos de qualidade RNF-08 e procedimentos OPS-09 conforme `DEC-014` (Issue #14). Lacuna `L-RF-02` fechada. |
| 2.0-rc2 | 2026-11-08 | Cobertura de C19: preenchida a coluna US para os 9 RF pendentes de C19 (`RF-C19-01`, `-04`, `-08`, `-09`, `-12`, `-13`, `-20`, `-23`, `-33`) com o novo Épico 17 (`US-APD-01` a `US-APD-07`, DOC-03) — Issue #15. Lacuna `L-RF-03` fechada. |
