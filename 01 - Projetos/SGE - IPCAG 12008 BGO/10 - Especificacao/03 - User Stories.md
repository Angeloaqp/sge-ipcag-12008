---
title: "03 - User Story Mapping, Épicos e Critérios de Aceitação (BDD)"
aliases:
  - "03-user-stories"
  - "DOC-03"
  - "User Stories SGE"
created: 2026-10-31
updated: 2026-11-08
status: ativo
version: "2.0-rc2"
doc_id: "DOC-03"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
figma_board: "https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd"
tags:
  - sge
  - ipcag-12008
  - user-stories
  - bdd
  - requisitos
  - epicos
---
# Documento 03: User Story Mapping, Épicos, Histórias de Utilizador e Critérios de Aceitação (BDD)

> [!abstract] Navegação & Rastreabilidade no Vault
> - **Painel Principal:** [[Inicio|Início do Vault]] | **Índice do Projeto:** [[00 - MOC SGE IPCAG 12008 BGO|MOC — SGE IPCAG N.º 12008 / BGO]]
> - **Sequência Arquitetural:** [[01 - Dominio e Regras]] $\rightarrow$ [[02 - Fluxos de Trabalho]] $\rightarrow$ **03 - User Stories** $\rightarrow$ [[04 - Telas e Documentos]] $\rightarrow$ [[05 - Modelagem de Dados]]
> - **Integração v2.0:** [[00.2 - Mapa de Integracao v2.0|Mapa de Integração (INT-V2)]] · [[12 - Registo de Decisoes e Questoes em Aberto|REG-12]] (`DEC-009`) · [[06 - Visao e Ambito|VIS-06]] §5 · [[00.1 - Plano de Engenharia de Requisitos|PLN-00]] §6 e §8
> - **Quadros Visuais no Figma:** 🎨 [Quadro Dedicado DOC-03 no FigJam](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd) \| 🌐 [Quadro Geral Unificado](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0) \| 📋 [[Quadros de Arquitetura no Figma\|Ver Todos os Links]] — *os quadros continuam na v1.2 e só são atualizados depois do congelamento (INT-V2 §5)*
> - **Áreas e Recursos:** [[Arquitetura de Software e DDD]] \| [[Governacao Escolar Ensino Tecnico MED]] \| [[Quadro Legal MED AGT e APD Angola]] \| [[Modelo de User Story BDD]] \| [[Verificacao das Referencias Legais]]

**Projeto:** Sistema de Gestão Escolar (SGE) — Ensino Secundário Técnico-Profissional (II Ciclo)  
**Instituição Alvo:** Instituto Politécnico Católico de Administração e Gestão (IPCAG) N.º 12008 / BGO – *"Nossa Senhora do Rosário"* (número da instituição impresso como parâmetro por tipo de documento — `Q-027`)  
**Referências Base:** [[01 - Dominio e Regras|01 - Domínio e Regras]] (`RN-01` a `RN-10` e famílias `RN-11` a `RN-18`, papéis RBAC com títulos configuráveis, máquinas de estado) e [[02 - Fluxos de Trabalho|02 - Fluxos de Trabalho]] (`Fluxo 01` a `Fluxo 08` e fluxos das capacidades novas)

> [!info] Convenções da v2.0 usadas nas histórias
> - 🟡 **Provisória** — regra ou valor parametrizável, ainda por validar pela escola (`DEC-009`). Pontos de controlo: homologação → **E1**; recálculo de pautas → **E2**; regulamento interno → **E3**. Cada 🟡 cita a questão que o bloqueia.
> - **Avaliação:** nomenclatura canónica `MTP`, `PP`, `PT`, `PG`, `M1`–`M3`, `CF`, `CA`; `MAC`/`NPP`/`NPT` são só rótulos alternativos de impressão (INT-V2 §3.3).
> - **Papéis e títulos:** os perfis RBAC (`DIR_GERAL`, `SUB_PED`, `DIR_TURMA`, …) são **papéis no sistema**; o título impresso é configurável (ex.: *Coordenadora Geral da Comissão de Gestão* para `DIR_GERAL`, *Coordenador para a Área Pedagógica* para `SUB_PED`, *Coordenador de Turma* para `DIR_TURMA` — `US-CTA-15`).
> - **Documentos fiscais:** Fatura, Fatura-Recibo, Recibo, Nota de Crédito e Recibo de Estorno (DP n.º 71/25, DE n.º 683/25), emitidos pelo software certificado pela AGT através do adaptador; o SGE emite o recibo escolar interno (`DEC-002` (b), decidida a 2026-11-09, homologação pendente).
> - **Termos impressos:** "Período" = Turno; "Cadeira" = Disciplina.
> - **Prioridade e entrega:** cada história tem uma prioridade **MoSCoW proposta** e a entrega **E1–E5** (VIS-06 §5.1; PLN-00 §6). A classificação final é feita na Fase E e fica no catálogo `07` (PLN-00 §3, fase E).
> - **Operação do Sistema (C18):** os 7 requisitos da capacidade C18 (backups, replicação, recuperação, monitorização, atualizações, suporte, formação) são atributos de qualidade e infraestrutura aceites pelas metas do [[08 - Requisitos Nao Funcionais|RNF-08]] e procedimentos de [[09 - Integracoes, Infraestrutura e Operacao|OPS-09]] conforme a [[12 - Registo de Decisoes e Questoes em Aberto#DEC-014 — Critérios de aceitação da operação (C18)|DEC-014]] (lacuna `L-RF-02` fechada), não gerando US funcionais no DOC-03.

---

## Visão Geral do User Story Mapping (Especificação v2.0)

> [!tip] 🎨 Quadro de User Story Mapping no FigJam
> O quadro mostra ainda os 7 épicos e as 32 histórias da v1.2: [Abrir Quadro DOC-03 no FigJam](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd) ou [Ver Secção 03 no Ficheiro Geral](https://www.figma.com/board/OneLIwLlc2kuM1koaIeXG0). Os épicos 08 a 15 só existem nesta nota até à atualização dos quadros.

**Total:** 17 épicos e 130 histórias de utilizador (32 da v1.2, corrigidas, 84 novas das capacidades `C03`, `C04`, `C10`, `C12`, `C13`, `C14`, `C15` e `C16`, 7 de `C17` e 7 de `C19` — `DEC-010`, `DEC-014`, Issues #13 e #15).

| Código do Épico | Nome do Épico / Domínio Funcional | Capacidade | Perfis RBAC Principais | Histórias de Utilizador (`US`) | Regras de Negócio Cobertas | Entrega | MoSCoW |
| :---: | :--- | :---: | :--- | :---: | :---: | :---: | :---: |
| **`EP-GOV`** | **Épico 01:** Governação, Configuração do Ano Letivo, Áreas de Formação, Matrizes Curriculares e Auditoria de Exceção | C01 | `DIR_GERAL`, `SUB_PED`, `SUB_ADM` | `US-GOV-01` a `US-GOV-04` (4 US) | `RN-01`, `RN-02`, `RN-03`, `RN-06`, `RN-10`, `RN-18` | **E1** (`US-GOV-04`: E3) | Must |
| **`EP-ADM`** | **Épico 02:** Concurso de Admissão à 10ª Classe e Gestão de Anonimato (DE n.º 361/26) | C02 | `OP_PED`, `CHEFE_SEC_PED`, `OP_TES`, `SUB_PED`, `DIR_GERAL` | `US-ADM-01` a `US-ADM-04` (4 US) | `RN-01`, `RN-08`, `RN-09`, `RN-10` | **E5** (concurso 2027/2028 corre fora do SGE com importação na E1 via C17 — `DEC-018`) | Must |
| **`EP-MAT`** | **Épico 03:** Matrículas, Confirmação Automática, Chamada Congelada e Transcrição de Histórico Externo | C03 | `OP_PED`, `CHEFE_SEC_PED`, `SUB_PED`, `OP_TES` | `US-MAT-01` a `US-MAT-04` (4 US) | `RN-02`, `RN-05`, `RN-06`, `RN-07`, `RN-08`, `RN-11`, `RN-18` | **E1** | Must |
| **`EP-PED`** | **Épico 04:** Gestão Pedagógica Trimestral, Mini-Pauta *Offline-First*, Faltas por Tipo, 2.ª Chamada, `DISP`, Substituição Docente e Conselho de Notas (`CF`/`PG`/`CA`) | C05, C06, C07 | `COORD_DISC`, `PROF`, `DIR_TURMA`, `SUB_PED`, `DIR_GERAL` | `US-PED-01` a `US-PED-06` (6 US) | `RN-01`, `RN-02`, `RN-03`, `RN-04`, `RN-05`, `RN-10`, `RN-12`, `RN-15` | **E2** (`US-PED-06`: E3 trimestral / E4 anual) | Must |
| **`EP-DEF-13`** | **Épico 05:** Cadeiras em Atraso (Exame Extraordinário) e Regime da 13ª Classe (Projecto Tecnológico, Estágio, PAP e `MFC`) | C07, C08 | `OP_PED`, `CHEFE_SEC_PED`, `COORD_CURSO`, `PROF`, `SUB_PED`, `DIR_GERAL` | `US-DEF-01` a `US-13C-02` (4 US) | `RN-01`, `RN-02`, `RN-06`, `RN-08`, `RN-10`, `RN-13` | **E4** | Must |
| **`EP-TES`** | **Épico 06:** Tesouraria Anti-Fraude (Borderô por Saldo e Crédito do Aluno), Motor de Bolsas, Documentos Fiscais e Notas de Crédito (DP n.º 71/25) e Fecho de Caixa por Turno | C10 | `SUB_ADM`, `DIR_GERAL`, `OP_TES`, `CHEFE_SEC_GER` | `US-TES-01` a `US-TES-05` (5 US) | `RN-07`, `RN-08`, `RN-09`, `RN-10`, `RN-13` | **E1** | Must |
| **`EP-DOC-AUD`** | **Épico 07:** Emissão Documental (Requerimento, Declarações, Certificado e Pedido do Diploma), Semáforo Financeiro, Registo de Arquivo, QR Code, RH e Estatísticas | C09, C11, C15 | `OP_PED`, `CHEFE_SEC_PED`, `CHEFE_SEC_GER`, `COORD_TURNO`, `DIR_GERAL` | `US-DOC-01` a `US-DOC-05` (5 US) | `RN-05`, `RN-08`, `RN-10`, `RN-11`, `RN-12`, `RN-13`, `RN-17` | **E2** (declarações, QR), **E3** (boletins), **E4** (certificados, GEPE); `US-DOC-04`: E1/E2 | Must |
| **`EP-PIN`** | **Épico 08:** Processo Individual do Aluno, Documentos, Encarregado e Cartão de Estudante | C03 | `OP_PED`, `CHEFE_SEC_PED`, `SUB_PED`, `DIR_TURMA` | `US-PIN-01` a `US-PIN-09` (9 US) | `RN-07`, `RN-08`, `RN-10`, `RN-11` | **E1** (`US-PIN-05`: E4) | Must (`US-PIN-08`: Should) |
| **`EP-HOR`** | **Épico 09:** Horários, Distribuição de Serviço Docente e Livro de Sumários | C04 | `SUB_PED`, `COORD_CURSO`, `COORD_TURNO`, `PROF` | `US-HOR-01` a `US-HOR-11` (11 US) | `RN-03`, `RN-04`, `RN-12` | **E2** | Must (`US-HOR-08`, `-10`: Should) |
| **`EP-COB`** | **Épico 10:** Cobrança de Dívidas, Acordos de Pagamento, Relatórios Financeiros e Conciliação Bancária | C10 | `SUB_ADM`, `OP_TES`, `CHEFE_SEC_GER`, `DIR_GERAL` | `US-COB-01` a `US-COB-15` (15 US) | `RN-08`, `RN-09`, `RN-13` | **E2** (`US-COB-05`, `-14`: E1); `US-COB-15` fora das E1–E5 (`DEC-005`) | Must / Should / Could; `US-COB-15`: Won't |
| **`EP-COM`** | **Épico 11:** Comunicação com Encarregados e Alunos (Avisos, Convocatórias, SMS e Portal) | C12 | `SUB_PED`, `SUB_ADM`, `DIR_TURMA`, `COORD_TURNO`, `OP_PED`, Encarregado, Aluno | `US-COM-01` a `US-COM-08` (8 US) | `RN-03`, `RN-08`, `RN-14` | **E3** (`US-COM-01` a `06` — `DEC-015`); **E5** (`US-COM-07`, `-08` — `DEC-003`) | Must / Should |
| **`EP-DIS`** | **Épico 12:** Disciplina e Comportamento | C13 | `PROF`, `COORD_TURNO`, `DIR_TURMA`, `SUB_PED`, `DIR_GERAL` | `US-DIS-01` a `US-DIS-06` (6 US) | `RN-03`, `RN-15` | **E2/E3** núcleo (`US-DIS-01` na E2, `US-DIS-04` na E3 — `DEC-013`); resto na **E5** | Must / Should |
| **`EP-CTA`** | **Épico 13:** Gestão de Contas e Acesso (Ciclo de Vida, MFA, PIN Local, Títulos dos Cargos) | C14 | `CHEFE_SEC_GER`, `DIR_GERAL`, `SUB_PED`, `SUB_ADM`, `ADMIN_TEC` | `US-CTA-01` a `US-CTA-15` (15 US) | `RN-04`, `RN-10`, `RN-16` | **E1** (`US-CTA-09`: E2; `US-CTA-14`: E5) | Must / Should |
| **`EP-PNL`** | **Épico 14:** Painéis de Gestão da Direção, Alertas e Estatísticas Impressas | C15 | `DIR_GERAL`, `SUB_PED`, `SUB_ADM`, `COORD_CURSO`, `COORD_DISC`, `COORD_TURNO`, `DIR_TURMA` | `US-PNL-01` a `US-PNL-12` (12 US) | `RN-02`, `RN-03`, `RN-17` | **E3** (`US-PNL-08`: E2; `US-PNL-11`: E4) | Must / Should / Could |
| **`EP-PAS`** | **Épico 15:** Encerramento do Ano Letivo e Passagem de Ano | C16 | `SUB_PED`, `DIR_GERAL`, `CHEFE_SEC_PED`, `OP_PED`, `SUB_ADM` | `US-PAS-01` a `US-PAS-08` (8 US) | `RN-02`, `RN-07`, `RN-10`, `RN-18` | **E4** | Must (`US-PAS-08`: Should) |
| **`EP-MIG`** | **Épico 16:** Migração de Dados, Cargas Históricas, Digitação Assistida e Reconciliação | C17 | `ADMIN_TEC`, Conta Técnica (`RN-16.21`), `OP_PED`, `OP_TES`, `CHEFE_SEC_PED`, `CHEFE_SEC_GER`, `SUB_PED`, `SUB_ADM`, `DIR_GERAL` | `US-MIG-01` a `US-MIG-07` (7 US) | `RN-01`, `RN-02`, `RN-05`, `RN-06`, `RN-09`, `RN-10`, `RN-16.21` | **E1** (`US-MIG-06`: E2; `US-MIG-07`: E4) | Must |
| **`EP-APD`** | **Épico 17:** Governação da Proteção de Dados, Gestão de Direitos e Políticas de Privacidade | C19 | `DIR_GERAL`, Ponto de Contacto APD, `SUB_PED`, `SUB_ADM`, `CHEFE_SEC_PED` | `US-APD-01` a `US-APD-07` (7 US) | `RN-10`, `RN-11.12` | **E1** (`US-APD-03`/`-04`: E2; `US-APD-05`: E3; `US-APD-06`: E4; `US-APD-07`: Fora — `DEC-016`) | Must (`US-APD-05`: Should; `US-APD-07`: Won't) |

> [!note] Decisões de entrega integradas
> - **`Q-037` — Central de avisos na E3:** **decidido na `DEC-015`** (2026-11-09): a central de avisos (`US-COM-01` a `US-COM-06`) entra na **E3** sem abrir dados à internet (canal impresso garantido e SMS complementar sob teto); o portal (`US-COM-07`, `US-COM-08`) fica na **E5** (`DEC-003`). O [[06 - Visao e Ambito|VIS-06]] foi atualizado.
> - **`Q-038` — Núcleo da C13 na E2/E3:** **decidido na `DEC-013`** (2026-11-05): tipos de falta (`US-DIS-01`) na E2 e comportamento trimestral (`US-DIS-04`) na E3; ocorrências, medidas e processos ficam na E5. O [[06 - Visao e Ambito|VIS-06]] foi atualizado.

---

## ÉPICO 01 (`EP-GOV`): Governação, Configuração do Ano Letivo, Áreas de Formação, Matrizes Curriculares e Auditoria de Exceção

---

### `US-GOV-01`: Configurar e Homologar Ano Letivo, Calendário dos 3 Trimestres e Parâmetros Institucionais
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** e **Director Geral (`DIR_GERAL`)**, *quero* **configurar e homologar os parâmetros institucionais de instalação única (designação, número de escola 12008/8009, NIF, cabeçalhos, rodapés e rótulos oficiais) e criar o Ano Letivo parametrizando as janelas dos 3 trimestres, prova global e exames**, *para* **garantir a padronização oficial de todos os documentos emitidos (`modelos_documento`) e assegurar que as operações escolares respeitam o calendário fixado pelo MED (2025/2026: DE n.º 686/25 — `COR-LEG-07`)**.
- **Rastreabilidade:** `RF-C01-07`, `RF-C09-07` (cabeçalho/rodapé e assinaturas) | `RN-01`, `RN-05`, `RN-10.6`, `RN-10.7`, `RN-18.1` | `DEC-001` | `MOD-GOV-01` | `parametros_instituicao`, `modelos_documento` | `Fluxo 01` e `Fluxo 04` | `US-PAS-01`, `US-PAS-05`, `US-CTA-15`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Utilizador autenticado com perfil `SUB_PED` ou `DIR_GERAL` (cria/edita parâmetros) — homologação exclusiva do `DIR_GERAL`; inexistência de outro Ano Letivo com o mesmo código (ex.: `2026/2027`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Criação e Homologação do Ano Letivo com o calendário real):**
    - **Dado** que o `SUB_PED` preenche o código `2026/2027`, data de início `01/09/2026`, data de fim `31/07/2027` e os intervalos sem sobreposição do I Trimestre (setembro a dezembro), do II Trimestre (janeiro a março/abril), do III Trimestre com a Prova Global (maio–junho), dos Exames Extraordinários (maio) e dos Exames de Recurso (julho) — calendário descrito pela escola ([[Sintese das Respostas da Fase B|DESC-RESP]] §3),
    - **Quando** submete a configuração e o `DIR_GERAL` aciona a homologação,
    - **Então** o Ano Letivo é criado com os 3 trimestres no estado `Planeado`, permitindo abrir apenas o `I Trimestre` inicialmente.
  - **Cenário 2 (Bloqueio — Tentativa de Abrir o II ou III Trimestre sem Fechar o Anterior):**
    - **Dado** que o `I Trimestre` ainda se encontra no estado `Janela Letiva Aberta` ou `Epoca de Conselhos`,
    - **Quando** o `SUB_PED` tenta alterar o estado do `II Trimestre` para `Janela Letiva Aberta`,
    - **Então** o sistema bloqueia a operação com erro `HTTP 422 Unprocessable Entity`: *"Não é permitido abrir o II Trimestre enquanto o I Trimestre não estiver no estado Encerrado Oficialmente"* (DOC-01 §3.1, Nível 1).
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um utilizador com perfil `CHEFE_SEC_PED`, `OP_PED` ou `PROF`,
    - **Quando** tenta criar ou alterar datas de trimestres,
    - **Então** a API rejeita a requisição com `HTTP 403 Forbidden`.
  - **Cenário 4 (Sucesso — Parametrização do Quadro de Vagas e Limiares de Admissão por Curso/Período — `RN-01.2`, `COR-LEG-08`, `COR-LEG-11`):**
    - **Dado** que o `SUB_PED` configura o quadro de vagas da 10ª classe (`quadros_vagas_admissao`) para cada par `Curso Técnico + Turno` (impresso como **Período** Manhã/Tarde) no Ano Letivo criado,
    - **Quando** define `total_vagas_disponiveis` (ex.: `90` vagas), `nota_minima_por_prova` (**por omissão `10` valores em cada prova de seleção** — DP n.º 167/23, art. 52.º, n.º 1), `idade_minima_ingresso` (**15 anos completados no ano da matrícula** — DP n.º 167/23, art. 23.º) e, só se for indicada a norma, `idade_maxima_ingresso_regular` 🟡 (sem fonte legal encontrada — `Q-LEG-09`), e o `DIR_GERAL` homologa,
    - **Então** o sistema grava os parâmetros em `quadros_vagas_admissao` com `vagas_preenchidas = 0`, aplicando-os automaticamente na validação de inscrições e no apuramento do concurso de admissão.
  - **Cenário 5 (Bloqueio — Abrir o I Trimestre com o Ano Letivo Anterior por Encerrar — `RN-18.1`):**
    - **Dado** que o Ano Letivo `2026/2027` ainda está `Em Encerramento` (pendências no painel de encerramento — `US-PAS-01`),
    - **Quando** o `SUB_PED` tenta abrir o `I Trimestre` de `2027/2028`,
    - **Então** o sistema recusa com `HTTP 422`: *"O I Trimestre só abre depois de o Ano Letivo anterior estar Encerrado"*, e mostra as pendências do ano anterior.
  - **Cenário 6 (Sucesso — Parametrização Institucional, Números da Escola, Rótulos e Modelos de Documento — `RF-C01-07`, `RF-C09-07`, `RN-10.6`, `RN-10.7`, `DEC-001`):**
    - **Dado** que o `SUB_PED` acede à consola de parâmetros institucionais (`MOD-GOV-01`) e regista os parâmetros, que o `DIR_GERAL` homologa (DOC-01 §2.2, linha 1),
    - **Quando** regista em `parametros_instituicao`: designação oficial (*Instituto Politécnico Católico de Administração e Gestão (IPCAG) N.º 12008 / BGO*) e designação complementar (*"Nossa Senhora do Rosário"*), NIF institucional (🟡 a confirmar — `DSC-06-SUB-ADM`), número da instituição **por tipo de documento** (12008 / 8009 — 🟡 `Q-027`; regra em `RN-10.6`; `DEC-001`), cabeçalho oficial com a Insígnia da República de Angola e emblema escolar, rodapé com os códigos de procedimento (`IPCAG.SG-ACE` e `DEE-PEEP-001-ACE`), e os rótulos impressos padrão ("Período" para Turno, "Cadeira" para Disciplina — `INT-V2` §3.5),
    - **Então** todos os modelos de documentos (`modelos_documento`, `DOF-01` a `DOF-26`) herdam automaticamente essa identidade visual e de numeração, e nos blocos de assinatura exibem o título institucional configurado (`US-CTA-15`) e o nome do titular com atribuição ativa na data de emissão do documento (`RF-C09-07`).
- **Pós-condições e Efeitos Colaterais:** Registo criado/atualizado em `parametros_instituicao`, `modelos_documento`, `anos_letivos`, `trimestres_letivos` e `quadros_vagas_admissao`; eventos `PARAMETROS_INSTITUICAO_HOMOLOGADOS` e `ANO_LETIVO_HOMOLOGADO` registados em `audit_logs`.

---

### `US-GOV-02`: Configurar Áreas de Formação, Cursos Técnicos, Classes (10ª–13ª) e Matrizes Curriculares
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **configurar a Área de Formação, os Cursos Técnicos com a sua Especialidade e as respetivas Matrizes Curriculares da 10ª à 13ª classe (componentes, disciplinas nucleares, tempos letivos semanais, fonte oficial da matriz e pesos da `MFC`)**, *para* **assegurar o cumprimento automático das regras de retenção por faltas (`RN-03`), transição (`RN-02`) e cálculo da Média Final do Curso (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-02`, `RN-03`, `RN-06` | `Fluxo 01`, `Fluxo 03`, `Fluxo 04`, `Fluxo 06` | DESC-L1 A5, A6, A7 | `COR-LEG-13`, `COR-LEG-23`, `COR-LEG-28`, `COR-LEG-29`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Área de Formação **"Administração e Serviços"** e especialidade `ADM_GESTÃO` registadas; cursos reais do IPCAG N.º 12008 / BGO no catálogo: **Contabilidade e Gestão**, **Gestão de Recursos Humanos**, **Gestão Empresarial** e **Estatística e Planeamento** (DESC-L1 A5).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Definição da Matriz Curricular da 10ª Classe com as cargas reais):**
    - **Dado** que o `SUB_PED` seleciona o curso *Técnico de Contabilidade e Gestão* — `10ª Classe` e indica como fonte o decreto executivo de criação do curso e o plano curricular oficial recebido (`COR-LEG-29`),
    - **Quando** adiciona as disciplinas classificando cada uma na componente **Sócio-Ambiental-Cultural** (`COR-LEG-23`), **Científica** ou **Técnica, Tecnológica e Prática**, com as cargas reais (*Língua Portuguesa* `3`, *Educação Física* `2`, *Matemática* `4`, *Informática de Gestão* `2` tempos/semana), define `is_nuclear = TRUE` para as disciplinas nucleares, `permite_dispensa_medica = TRUE` para *Educação Física* e indica o fator de faltas 🟡 (parâmetro do Ano Letivo sem fonte publicada — `COR-LEG-13`, `Q-LEG-04`),
    - **Então** o sistema calcula e armazena o `limite_max_faltas_injustificadas` de cada disciplina (ex.: fator `3` × `4` tempos = `12` faltas em *Matemática*) e ativa a matriz após homologação do `DIR_GERAL`.
  - **Cenário 2 (Sucesso — Configuração do Regime da 12ª e da 13ª Classe com Projecto Tecnológico — `COR-LEG-16`, `COR-LEG-28`):**
    - **Dado** que o `SUB_PED` configura a 12ª e a 13ª Classe do curso,
    - **Quando** regista a disciplina **Projecto Tecnológico** (`2` tempos na 12ª, `8` tempos na 13ª), o **Estágio Curricular Supervisionado** (`20` tempos na 13ª) e a **PAP** como prova final de defesa do relatório de estágio, com os pesos da `MFC` 🟡 (por confirmar — `Q-030`, `Q-LEG-07`; ponto de controlo **E2**),
    - **Então** o sistema mantém a avaliação do Projecto Tecnológico como disciplina e habilita o módulo de Estágio e PAP para a 13ª classe, sem Mini-Pautas das disciplinas que a 13ª não tem.
  - **Cenário 3 (Bloqueio — Alteração de Matriz com Notas Já Lançadas):**
    - **Dado** que uma Matriz Curricular já possui turmas com avaliações registadas no Ano Letivo corrente,
    - **Quando** o `SUB_PED` tenta remover uma disciplina ou alterar o flag `is_nuclear`,
    - **Então** o sistema bloqueia a edição direta (`HTTP 409 Conflict`), exigindo a criação de uma nova versão de matriz para o próximo Ano Letivo.
  - **Cenário 4 (Bloqueio — Matriz da 12ª com Língua Portuguesa — DESC-L1 A7):**
    - **Dado** que nos planos oficiais a Língua Portuguesa só existe na 10ª e na 11ª Classe,
    - **Quando** o `SUB_PED` configura a regra de veto "LP + nuclear" na matriz da 12ª Classe,
    - **Então** o sistema avisa que o veto não se aplica a uma classe sem Língua Portuguesa e não o ativa (`RN-02`, `Q-031`).
- **Pós-condições e Efeitos Colaterais:** Tabelas `areas_formacao`, `cursos_tecnicos`, `matrizes_curriculares` e `matriz_disciplinas` populadas e versionadas (nomes finais no [[05 - Modelagem de Dados|DOC-05]]).

---

### `US-GOV-03`: Configurar e Abrir Turmas por Turno (Manhã/Tarde) nas 12 Salas e Laboratórios
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** (a quem cabe a formação de turmas — `COR-LEG-22`), com o apoio do **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **criar as Turmas de cada Curso e Classe associando-as a um Turno (impresso como "Período": Manhã ou Tarde), a uma das 12 salas de aula físicas (sala fixa por turma) e a um Director de Turma (`DIR_TURMA`; título impresso configurável, ex.: "Coordenador de Turma")**, *para* **organizar a capacidade de +1.120 alunos sem conflitos de ocupação de salas**.
- **Rastreabilidade:** `RN-04`, `RN-05` | `Fluxo 01` e `Fluxo 02` | `US-CTA-03`, `US-PAS-03` | DESC-RESP R6, R22 | `COR-LEG-22`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Ano Letivo e Matrizes Curriculares criados; cadastro das 12 salas e laboratórios disponível.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Criação de Turma e Geração Automática de Mini-Pautas):**
    - **Dado** que o `CHEFE_SEC_PED` cria a turma `CG11A-M` (Contabilidade e Gestão, 11ª Classe, Turno Manhã, Sala 04, lotação máxima `45` alunos) e nomeia o docente titular como `DIR_TURMA` (o sistema cria a atribuição de cargo `DIR_TURMA` com escopo nessa turma — `US-CTA-03`),
    - **Quando** grava o registo,
    - **Então** o sistema instancia automaticamente os cabeçalhos de **Mini-Pauta** para todas as disciplinas da Matriz Curricular da 11ª Classe daquele curso, prontos para receber alocações de professores.
  - **Cenário 2 (Bloqueio — Dupla Ocupação da Mesma Sala no Mesmo Turno):**
    - **Dado** que a `Sala 04` já está atribuída à turma `CG11A-M` no `Turno da Manhã` do Ano Letivo `2026/2027`,
    - **Quando** o utilizador tenta atribuir a mesma `Sala 04` a outra turma no `Turno da Manhã`,
    - **Então** o sistema rejeita com erro `HTTP 409 Conflict`: *"Conflito Físico: A Sala 04 já se encontra ocupada no Turno da Manhã pela turma CG11A-M"*.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `turmas` e em `turma_disciplinas` (Mini-Pautas base).

---

### `US-GOV-04`: Reabrir Temporariamente Pauta Homologada por Ordem da Direção com Auditoria Imutável
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`) ou Director Geral (`DIR_GERAL`)**, *quero* **reabrir temporariamente uma Mini-Pauta ou Pauta Geral que já se encontre no estado `Fechado / Homologado` mediante registo de despacho formal e prazo de expiração**, *para* **permitir a retificação excecional de erros materiais mantendo rastreabilidade absoluta exigida pela Lei n.º 22/11 (APD)**.
- **Rastreabilidade:** `RN-01`, `RN-10` | `Fluxo 04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (primeiras pautas homologadas no fim do I Trimestre)`.
- **Pré-condições:** Pauta no estado `Fechado / Homologado`; utilizador autenticado exclusivamente como `SUB_PED` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Reabertura com Despacho e Gravação de `old_value` / `new_value`):**
    - **Dado** que a Mini-Pauta de *Matemática* da turma `CG10A-M` (I Trimestre) está `Fechada / Homologada`,
    - **Quando** o `SUB_PED` seleciona *"Reabrir por Ordem da Direção"*, informa o `N.º do Despacho = DESP-PED-014/2026`, a justificativa detalhada (mínimo 30 caracteres), o aluno/disciplina alvo e o prazo de `4 horas`, e corrige a `PT` do aluno de `11` para `14` (inclusive avocando o lançamento caso o professor titular já tenha saído da escola — `RN-04.1`),
    - **Então** apenas aquela Mini-Pauta (`turma_disciplina_id`) muda para `Reaberto Temporariamente` (sem reabrir as restantes turmas da escola), recalcula `M1` e `CF` via `round_med`, grava em `audit_logs` um registo imutável contendo `usuario_id`, `ip_origem`, `despacho_num`, `justificativa`, `valor_antigo_jsonb: {"pt": 11, "m1": 12}` e `valor_novo_jsonb: {"pt": 14, "m1": 13}` (com `MTP = 12` e `PP = 13`), e ao clicar em *"Trancar"* (ou expirar as 4 horas) retorna ao estado `Fechado / Homologado` incrementando `versao_pauta`.
  - **Cenário 2 (Bloqueio — Tentativa de Reabertura sem Justificativa ou por Cargo Não Autorizado):**
    - **Dado** que um `CHEFE_SEC_PED`, `DIR_TURMA` ou `PROF` tenta reabrir ou editar uma pauta fechada (ou o `SUB_PED` omite o número do despacho),
    - **Então** o sistema bloqueia a operação (`HTTP 403 Forbidden` ou `HTTP 422 Unprocessable Entity`) e regista a tentativa negada no log de segurança.
- **Pós-condições e Efeitos Colaterais:** Pauta atualizada para nova versão (`versao_pauta + 1`), médias recalculadas e entrada permanente gravada em `audit_logs`.

---

## ÉPICO 02 (`EP-ADM`): Concurso de Admissão à 10ª Classe e Gestão de Anonimato (DE n.º 361/26)

---

### `US-ADM-01`: Inscrever Candidato ao Teste de Admissão da 10ª Classe e Emitir Guia de Emolumento
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **registar a inscrição de candidatos ao Teste de Seleção da 10ª classe validando o Bilhete de Identidade, a idade mínima e a conclusão da 9ª classe**, *para* **iniciar o processo seletivo nos termos do regulamento do teste de seleção para admissão (DE n.º 361/26, de 22/07/2026; antecessores DE n.º 136/24 e n.º 684/25 — `COR-LEG-07`)**.
- **Rastreabilidade:** `RN-01.2`, `RN-08`, `RN-09` | `Fluxo 01` | `COR-LEG-07`, `COR-LEG-10`, `COR-LEG-11`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E5`.
- **Pré-condições:** Concurso de Admissão do Ano Letivo aberto; tabela de emolumentos configurada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Inscrição de Candidato com 1ª e 2ª Opção de Curso/Período):**
    - **Dado** que o `OP_PED` insere o nome completo (como no BI), data de nascimento (com **15 anos completados no ano da matrícula**), género (`M`/`F`), número de BI/Cédula Pessoal único, a conclusão da 9ª classe, dados do Encarregado de Educação, a **1ª Opção de Curso Técnico/Período** e a **2ª Opção** (usada só na repescagem 🟡, prática interna sujeita a validação — `COR-LEG-10`, `Q-LEG-12`),
    - **Quando** confirma a inscrição,
    - **Então** o sistema cria a candidatura no estado `Inscrito`, imprime a Ficha de Inscrição (`DOF-01`) e emite a guia de pagamento da Taxa de Inscrição para liquidação na Tesouraria.
  - **Cenário 2 (Bloqueio — Candidato Duplicado no Mesmo Ano Letivo):**
    - **Dado** que já existe uma candidatura no Ano Letivo corrente com o mesmo número de BI,
    - **Quando** o `OP_PED` tenta submeter nova ficha com esse BI,
    - **Então** o sistema rejeita com erro `HTTP 409 Conflict`: *"O candidato portador do BI informado já possui inscrição registada neste concurso de admissão"*.
  - **Cenário 3 (Bloqueio — Idade Inferior ao Mínimo):**
    - **Dado** um candidato que só completa 15 anos no ano civil seguinte ao da matrícula,
    - **Quando** o `OP_PED` tenta confirmar a inscrição,
    - **Então** o sistema rejeita com `HTTP 422`: *"Idade mínima de ingresso na 10ª Classe: 15 anos completados no ano da matrícula (DP n.º 167/23, art. 23.º)"*. Não há validação de idade máxima enquanto não houver norma (`Q-LEG-09`).
- **Pós-condições e Efeitos Colaterais:** Registo criado na tabela `candidaturas_10a` (estado `INSCRITO`) e débito de emolumento gerado para pagamento no Caixa.

---

### `US-ADM-02`: Confirmar Pagamento de Inscrição, Gerar Código de Anonimato e Alocar nas 12 Salas
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **que o sistema gere automaticamente o Código de Anonimato e aloque o candidato numa das 12 salas de exame assim que a Tesouraria emitir o documento fiscal (Fatura-Recibo ou Recibo — DP n.º 71/25) da taxa de inscrição**, *para* **garantir a lisura e imparcialidade na correção das provas de seleção (DE n.º 361/26)**.
- **Rastreabilidade:** `RN-08`, `RN-09`, `RN-10` | `Fluxo 01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E5`.
- **Pré-condições:** Candidatura no estado `Inscrito`; documento fiscal da Taxa de Inscrição emitido pelo `OP_TES` (emissor conforme a `DEC-002`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transição Automática e Geração de Anonimato):**
    - **Dado** que o `OP_TES` emite a Fatura-Recibo da Taxa de Exame de Admissão para um candidato `Inscrito`,
    - **Quando** a transação financeira é confirmada,
    - **Então** o estado da candidatura muda automaticamente para `Apto para Exame (Taxa Paga)`, o sistema atribui um `codigo_anonimato` único aleatório (ex.: `IPCAG-26-491B`), aloca o candidato numa das 12 salas disponíveis e libera a impressão da **Lista de Chamada da Sala** e das **Etiquetas de Anonimato**.
  - **Cenário 2 (Bloqueio — Candidato Sem Pagamento Confirmado):**
    - **Dado** que uma candidatura permanece no estado `Inscrito` (sem recibo associado),
    - **Quando** o `CHEFE_SEC_PED` gera as listas de presença para o dia do exame,
    - **Então** o candidato não pago é estritamente excluído das listas de sala e não recebe `codigo_anonimato`.
- **Pós-condições e Efeitos Colaterais:** Candidatura em `Apto para Exame`; vínculo encriptado `candidatura_id <-> codigo_anonimato` guardado na base de dados.

---

### `US-ADM-03`: Lançar Notas de Exame de Admissão Cegamente pelo Código de Anonimato
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) ou Subdirector Pedagógico (`SUB_PED`)**, *quero* **digitar as notas das provas de seleção pesquisando exclusivamente pelo Código de Anonimato sem qualquer exibição do nome ou BI do candidato**, *para* **impedir favorecimentos ou fraudes durante o lançamento de notas do concurso**.
- **Rastreabilidade:** `RN-01`, `RN-10` | `Fluxo 01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E5`.
- **Pré-condições:** Provas de seleção realizadas; candidaturas no estado `Apto para Exame`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Lançamento Cego de Notas):**
    - **Dado** que o `CHEFE_SEC_PED` acede à grelha de correção anónima,
    - **Quando** pesquisa pelo código `IPCAG-26-491B` e insere `Nota_LP = 14` e `Nota_Mat = 15`,
    - **Então** o sistema apresenta apenas o `codigo_anonimato` (ocultando 100% dos dados pessoais), calcula a média da prova via `round_med((14 + 15) / 2) = 15` (com as duas secções acima do mínimo de 10 — `US-ADM-04`; 🟡 cálculo da nota final do teste único por secções — `Q-LEG-10`) e transita o registo para `Avaliado (Código Anonimato)`.
  - **Cenário 2 (Bloqueio — Nota Inválida Fora de 0 a 20):**
    - **Dado** que o operador tenta inserir `-1` ou `21` valores,
    - **Quando** submete o campo,
    - **Então** o sistema bloqueia o registo com erro de validação: *"A nota deve estar compreendida entre 0 e 20 valores"*.
- **Pós-condições e Efeitos Colaterais:** Notas associadas ao `codigo_anonimato` e candidatura no estado `Avaliado (Código Anonimato)`.

---

### `US-ADM-04`: Descodificar Anonimato, Apurar Admitidos com Mínimo por Prova e Desempate pela Menor Idade, e Publicar as Listas nos Prazos Legais
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`) em conjunto com o Director Geral (`DIR_GERAL`)**, *quero* **executar a descodificação oficial do anonimato e o apuramento automático dos candidatos `Admitidos` e `Não Admitidos` por Curso e Período, publicando as listas e tratando as reclamações nos prazos do regulamento**, *para* **respeitar o limite de vagas, o mínimo de 10 valores em cada prova e o critério legal de desempate**.
- **Rastreabilidade:** `RN-01.2`, `RN-10` | `Fluxo 01` | `COR-LEG-08`, `COR-LEG-09`, `COR-LEG-10`, `COR-LEG-12`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E5`.
- **Pré-condições:** 100% dos candidatos `Aptos para Exame` avaliados ou marcados como `Faltou ao Exame`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Descodificação, `MFA` e Apuramento com Mínimo de 10 em Cada Prova e Desempate pela Menor Idade):**
    - **Dado** que o curso *Contabilidade e Gestão — Manhã* possui `total_vagas_disponiveis = 90` e `nota_minima_por_prova = 10` em `quadros_vagas_admissao`, e todas as provas estão avaliadas,
    - **Quando** o `SUB_PED` e o `DIR_GERAL` confirmam a **Descodificação e Homologação da Pauta de Seleção**,
    - **Então** o sistema revela os nomes reais, calcula $MFA = \text{round\_med}((\text{Nota\_LP} + \text{Nota\_Mat\_Esp}) / 2)$ 🟡 (cálculo da nota final do teste único por secções a confirmar — `Q-LEG-10`), ordena por `MFA` decrescente e, em caso de empate na última vaga, dá prioridade ao **candidato mais novo** (DE n.º 361/26, art. 16.º, n.º 2, c)); outros critérios só se a Direção Provincial os validar 🟡 (`Q-LEG-11`). Classifica como **`ADMITIDO`** quem tem **10 ou mais em cada prova** e fica dentro das 90 vagas, como **`NÃO ADMITIDO (Fora das Vagas / Excedente)`** quem cumpre o mínimo mas fica depois da 90ª vaga, e como **`NÃO ADMITIDO (Nota Inferior ao Mínimo)`** quem tem menos de 10 numa prova, gerando a Lista de Selecionados (`DOF-02`) com QR Code.
  - **Cenário 2 (Exceção — Média Positiva com uma Prova Abaixo de 10):**
    - **Dado** um candidato com `Nota_LP = 9` e `Nota_Mat_Esp = 15` (`MFA = 12`),
    - **Quando** o apuramento é executado,
    - **Então** o candidato fica **`NÃO ADMITIDO (Nota Inferior a 10 numa Prova)`** (`NAO_ADMITIDO_NOTA_INFERIOR`), mesmo havendo vagas.
  - **Cenário 3 (Bloqueio — Tentativa de Descodificar com Provas Pendentes):**
    - **Dado** que ainda existem 3 códigos de anonimato sem nota lançada nem marcação de falta,
    - **Quando** o `SUB_PED` tenta executar a descodificação,
    - **Então** o sistema bloqueia a ação listando os códigos pendentes de lançamento.
  - **Cenário 4 (Sucesso — Prazos de Publicação, Reclamação e Lista Definitiva — `COR-LEG-12`):**
    - **Dado** que o teste se realizou a `10/08` às `08h00`,
    - **Quando** a Lista de Selecionados é publicada dentro das **72 h** seguintes ao teste e um candidato apresenta reclamação **até 24 h** depois da publicação,
    - **Então** o sistema regista a reclamação com data e hora, conta o prazo de decisão de **24 h**, e só publica a **lista definitiva** depois da homologação do Director (título configurado — `US-CTA-15`).
  - **Cenário 5 (Bloqueio — Reclamação Fora do Prazo):**
    - **Dado** que passaram mais de 24 h desde a publicação da Lista de Selecionados,
    - **Quando** o `OP_PED` tenta registar uma reclamação,
    - **Então** o sistema recusa com `HTTP 422`: *"Prazo de reclamação esgotado (24 h após a publicação)"*.
  - **Cenário 6 (Bloqueio — Admitir Abaixo do Mínimo com Vagas Sobrantes — `COR-LEG-08`):**
    - **Dado** que após a 1ª chamada o curso *Gestão Empresarial — Tarde* ficou com `65` de `90` vagas preenchidas,
    - **Quando** alguém tenta baixar o mínimo por prova para `9` ou `8` valores por despacho,
    - **Então** o sistema recusa: a redução do limiar e o estado `DespachoLimiar` deixam de existir (salvo exceção confirmada por escrito pela Direção Provincial — `Q-LEG-10`).
  - **Cenário 7 (Sucesso 🟡 — Repescagem da 2ª Opção, Prática Interna — `COR-LEG-10`):**
    - **Dado** as mesmas `25` vagas sobrantes e a repescagem ativa como parâmetro (prática interna sujeita a validação — `Q-LEG-12`),
    - **Quando** o `SUB_PED` e o `DIR_GERAL` acionam a **Repescagem de 2ª Opção**,
    - **Então** o sistema aloca, por ordem decrescente de `MFA`, os candidatos `NÃO ADMITIDO (Fora das Vagas / Excedente)` — todos com 10 ou mais em cada prova — que escolheram *Gestão Empresarial — Tarde* como 2ª Opção (estado `Admitido (2ª Opção — Repescagem)`), regista a operação em `audit_logs` e publica a adenda da lista.
- **Pós-condições e Efeitos Colaterais:** Candidaturas transitadas para `Admitido`, `Admitido (2ª Opção — Repescagem)`, `Não Admitido (Fora das Vagas / Excedente)` ou `Não Admitido (Nota Inferior ao Mínimo)`; reclamações e decisões registadas; `vagas_preenchidas` atualizado em `quadros_vagas_admissao`; homologação gravada em `audit_logs`.

---

## ÉPICO 03 (`EP-MAT`): Matrículas, Confirmação Automática, Chamada Congelada e Transcrição de Histórico Externo

---

### `US-MAT-01`: Converter Candidato Admitido em Aluno Vitalício (`N.º de Processo Individual`) e Matricular na 10ª Classe
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **converter um candidato `Admitido` num registo vitalício de `Aluno` com atribuição automática do `N.º de Processo Individual` único e do número anual do Boletim de Matrícula**, *para* **efetivar a sua matrícula na 10ª classe sem redigitação de dados**.
- **Rastreabilidade:** `RN-05`, `RN-07`, `RN-08`, `RN-11.2`, `RN-11.14` | `Fluxo 02` | `US-PIN-02`, `US-PIN-09` | `COR-LEG-15`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Candidato com estado `Admitido` no Ano Letivo corrente (ou importado pela migração na E1 via C17 — `DEC-018`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Conversão, N.º de Processo Vitalício e Boletim Numerado):**
    - **Dado** que o candidato `Admitido` comparece para matrícula e entrega os documentos, registados e conferidos no processo individual (`US-PIN-02`),
    - **Quando** o `OP_PED` seleciona a turma da 10ª classe (dentro da lotação de `40–45` alunos) e aciona *"Converter em Matrícula"*,
    - **Então** o sistema cria a entidade `Aluno` com um `num_processo` sequencial vitalício (ex.: `PROC-2026-00412`), atribui o Boletim de Matrícula com o número anual (ex.: `N.º 0137/2026-2027` — `US-PIN-09`), gera a lista de documentos do processo (`US-PIN-01`), cria a `Matrícula` no estado `Pendente (Aguardando Pagamento Inicial)`, atualiza a candidatura para `Convertido em Matrícula` e, assim que o pagamento da Taxa de Matrícula + propina de setembro (ou a Bolsa 100%) é confirmado pelo documento fiscal da Tesouraria, muda a matrícula para `Ativa` e gera as 10 prestações mensais (setembro a junho) na Conta Corrente.
  - **Cenário 2 (Bloqueio — Candidato Não Admitido):**
    - **Dado** um candidato com estado `Não Admitido` ou `Inscrito`,
    - **Quando** o `OP_PED` tenta convertê-lo em matrícula,
    - **Então** o botão encontra-se desativado e a API retorna `HTTP 422 Unprocessable Entity`: *"Apenas candidatos com estado ADMITIDO podem ser convertidos em matrícula da 10ª classe"*.
  - **Cenário 3 (Exceção 🟡 — Matrícula Incompleta Anulada aos 60 Dias — `COR-LEG-15`):**
    - **Dado** uma matrícula que continua `Pendente (Aguardando Pagamento Inicial)` 60 dias depois do início do ano letivo (prazo proposto, parâmetro a validar — `Q-LEG-05`, `Q-C16-01`),
    - **Quando** o prazo expira,
    - **Então** a matrícula passa a `Anulada / Desistente` pela transição `expirarPrazoConfirmacao` e o aluno fica `Interrompido` (`RN-18.14`).
- **Pós-condições e Efeitos Colaterais:** Registo vitalício criado em `alunos`; matrícula criada em `matriculas_anuais` com o número do boletim; documentos do processo gerados em `documentos_processo_aluno`; plano financeiro gerado em `conta_corrente_propinas`.

---

### `US-MAT-02`: Confirmar Automaticamente a Matrícula dos Alunos Internos (11ª, 12ª e 13ª Classes) a partir da Proposta de Passagem
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **que a confirmação de matrícula anual dos alunos internos parta de uma proposta pré-gerada pela passagem de ano, conforme a deliberação final do ano anterior, preservando o `N.º de Processo Individual`**, *para* **que a confirmação seja automática e da responsabilidade da escola, como a lei prevê, e o aluno fique na classe certa (transição limpa, com cadeiras em atraso ou repetência)**.
- **Rastreabilidade:** `RN-02`, `RN-05`, `RN-08`, `RN-18.5`, `RN-18.6`, `RN-11.14`, `RN-13.8` | `Fluxo 02` (Cenário B) | `US-PAS-02`, `US-PAS-06`, `US-PIN-09` | `COR-LEG-14`, `COR-LEG-15`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Proposta de confirmação no estado **`Apta a Confirmar`** (`US-PAS-02`); Pauta Geral do ano anterior `Fechado / Homologado`; modo de confirmação do Ano Letivo (`BALCAO` ou `AUTOMATICA`) 🟡 parametrizado (`Q-LEG-05`; ponto de controlo **E1**).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Confirmação Automática na Classe Seguinte com Preservação de Processo):**
    - **Dado** que o aluno `PROC-2025-00108` obteve na 10ª classe a deliberação `Transita com Deficiência` com 2 cadeiras em atraso, e o Ano Letivo está no modo `AUTOMATICA`,
    - **Quando** a passagem definitiva é homologada,
    - **Então** o sistema converte a proposta numa matrícula `Pendente` na `11ª Classe` do mesmo curso, mantém `num_processo = PROC-2025-00108`, atribui o número anual do Boletim de Confirmação e pré-preenche a classe, turma e sala do ano anterior e as 2 cadeiras em atraso (DESC-L1 A12), sem deslocação do encarregado.
  - **Cenário 2 (Bloqueio 🟡 — Dívida do Ano Anterior, se a Escola a Puder Reter — `Q-LEG-05`):**
    - **Dado** que o bloqueio por dívida está **ligado** como parâmetro e o aluno tem propinas `Em Atraso (com Multa)` do ano anterior sem acordo de pagamento que liberte o semáforo (`RN-13.8`),
    - **Quando** o `OP_PED` tenta converter a proposta,
    - **Então** o sistema recusa com `HTTP 403 — Pendência Financeira`; com o parâmetro **desligado**, a confirmação prossegue e a dívida continua a bloquear os documentos (`RN-08`).
  - **Cenário 3 (Bloqueio — 13ª Classe com Cadeira em Atraso):**
    - **Dado** um aluno que pretende confirmar matrícula na `13ª Classe` com $\ge 1$ Cadeira em Atraso não eliminada,
    - **Quando** a proposta é gerada,
    - **Então** o sistema não a deixa `Apta a Confirmar` (`HTTP 422` por deficiência curricular pendente — `RN-02`).
  - **Cenário 4 (Exceção — Reprovação por Faltas Injustificadas — `COR-LEG-14`):**
    - **Dado** um aluno retido por faltas injustificadas no II Ciclo,
    - **Quando** a proposta é gerada,
    - **Então** o aluno perde o direito à confirmação automática: só confirma com a justificação aceite (confirmação em **5 dias úteis** após a justificação) ou por despacho de reingresso (`Q-LEG-04`).
  - **Cenário 5 (Exceção — Prazo Expirado e Confirmação Tardia):**
    - **Dado** uma matrícula `Pendente` que não ficou completa 60 dias depois do início do ano letivo 🟡 (`COR-LEG-15`, `Q-C16-01`),
    - **Quando** o prazo expira,
    - **Então** a matrícula passa a `Anulada / Desistente`; uma confirmação tardia só é possível se houver vaga e com autorização do `CHEFE_SEC_PED` (`RN-18.6.5`).
- **Pós-condições e Efeitos Colaterais:** Nova matrícula anual vinculada ao mesmo `aluno_id` e `num_processo`; proposta `Convertida em Matrícula`.

---

### `US-MAT-03`: Registar e Homologar Transcrição de Histórico Externo de Alunos Transferidos de Entrada
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **transcrever e vincular ao Processo Individual do aluno as classificações finais (`CA`; `MFD` nos modelos antigos) da 10ª, 11ª ou 12ª classe trazidas através de Guia de Transferência/Certificado de outra escola**, *para* **garantir que o histórico curricular fique completo e viabilize o cálculo exato da Média Final do Curso (`MFC`) na 13ª classe (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-06`, `RN-10` | `Fluxo 02` e `Fluxo 06`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Matrícula por transferência de entrada na 11ª, 12ª ou 13ª classe; Guia de Transferência Oficial e Certificado Parcial digitalizados.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transcrição e Homologação pelo Subdirector Pedagógico):**
    - **Dado** que um aluno ingressa por transferência externa na `12ª Classe` do curso de *Gestão de Recursos Humanos*,
    - **Quando** o `CHEFE_SEC_PED` informa a escola de origem, número da Guia de Transferência, anexa o PDF comprovativo e preenche as notas finais (classificação final de `10` a `20` — `CA`, ou `MFD` no modelo da escola de origem — ou `DISP`) de todas as disciplinas da Matriz Curricular da `10ª Classe` e da `11ª Classe` (ou as médias trimestrais parciais `M1`/`M2` em caso de transferência no decurso do ano — `RN-06.1`), e o `SUB_PED` homologa o registo,
    - **Então** as notas transcritas passam a integrar a vista `vw_curriculo_consolidado_aluno` do aluno para cálculo de $MA_{10}$ e $MA_{11}$ na futura `MFC`.
  - **Cenário 2 (Bloqueio — Tentativa de Fechar 12ª/13ª Classe com Transcrição Externa Pendente):**
    - **Dado** um aluno admitido na 11ª ou 12ª classe por transferência externa cuja transcrição da 10ª classe ainda não foi preenchida ou homologada pelo `SUB_PED`,
    - **Quando** o sistema valida a aptidão do aluno para a `13ª Classe` ou para emissão do Certificado,
    - **Então** o sistema bloqueia a progressão exibindo a lista exata das disciplinas da 10ª/11ª classe cujas notas de origem estão em falta.
- **Pós-condições e Efeitos Colaterais:** Registos criados em `historico_externo_transcricoes` (uma linha por disciplina e classe equivalente); homologação gravada em `audit_logs`.

---

### `US-MAT-04`: Gerir N.º de Ordem na Turma, Congelar Lista de Chamada pós-I Trimestre e Processar Entradas Tardias/Saídas
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) ou Sistema Automático**, *quero* **ordenar alfabeticamente, pelo nome completo como consta no BI, os alunos da turma (`1..N`; 40–45 alunos por turma) no início do ano e congelar perpetuamente o `N.º de Ordem na Turma` após o fecho do I Trimestre**, *para* **garantir que alunos transferidos/desistentes não alterem os números de chamada dos colegas seguintes e que matrículas tardias entrem exclusivamente no fim da lista (`N + 1`) (`RN-05`)**.
- **Rastreabilidade:** `RN-05` | `Fluxo 02`, `Fluxo 04` e `Fluxo 08` | DESC-RESP R6.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Turma ativa no Ano Letivo corrente.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Ordenação Alfabética Antes do Congelamento e Trancamento no Fecho do I Trimestre):**
    - **Dado** que uma turma possui 40 alunos matriculados antes do fecho do I Trimestre,
    - **Quando** o `I Trimestre` da turma é homologado (ou o `CHEFE_SEC_PED` aciona *"Congelar Lista de Chamada"*),
    - **Então** os alunos ficam numerados de `1` a `40` por ordem alfabética do nome completo do BI e a flag `lista_chamada_congelada` passa a `TRUE`, bloqueando qualquer renumeração dos números `1` a `40`.
  - **Cenário 2 (Sucesso — Aluno Transferido ou Anulado Pós-Congelamento Mantém a Linha Fixa):**
    - **Dado** que a lista da turma está congelada (`1` a `40`) e o aluno `N.º 15` pede Transferência Externa ou Anulação de Matrícula no II Trimestre,
    - **Quando** a transferência/anulação é homologada,
    - **Então** o aluno `N.º 15` permanece na linha `15` da Mini-Pauta e da Pauta Geral com estado `TRANSFERIDO` (ou `ANULADO`), e o aluno `N.º 16` **continua sendo o `N.º 16`** até ao fim do ano letivo.
  - **Cenário 3 (Sucesso — Matrícula Tardia / Transferência de Entrada Pós-Congelamento Vai para `N + 1`):**
    - **Dado** que a lista da turma está congelada (`1` a `40`) e um novo aluno chamado *"Abel António"* (letra A) ingressa na turma por transferência no início do II Trimestre,
    - **Quando** a sua matrícula é ativada na turma,
    - **Então** o sistema atribui-lhe obrigatoriamente o **`N.º de Ordem = 41`** (`max(num_ordem_turma) + 1`), posicionando-o no fim da pauta sem deslocar nenhum dos 40 alunos anteriores.
  - **Cenário 4 (Bloqueio — Renumerar Depois do Congelamento):**
    - **Dado** que a lista da turma está congelada (`1` a `41`),
    - **Quando** o `CHEFE_SEC_PED` tenta reordenar a lista ou alterar o `N.º de Ordem` de um aluno,
    - **Então** o sistema recusa com `HTTP 409`: *"A lista de chamada está congelada: o N.º de Ordem não pode ser alterado"* (`RN-05`).
- **Pós-condições e Efeitos Colaterais:** Coluna `num_ordem_turma` imutável para todos os registos existentes após `lista_chamada_congelada = TRUE`.

---

## ÉPICO 04 (`EP-PED`): Gestão Pedagógica Trimestral, Mini-Pauta Offline-First, Faltas por Tipo, 2.ª Chamada, Dispensas (`DISP`), Substituição Docente e Conselho de Notas (`CF`/`PG`/`CA`)

---

### `US-PED-01`: Registar a Dosificação Trimestral e as Provas Unificadas (`PT` e `PG`) com Variantes A, B e de 2.ª Chamada
- **História:** *Como* **Coordenador de Disciplina (`COORD_DISC`)**, *quero* **registar o plano de dosificação trimestral e elaborar a Prova Trimestral (`PT`) e a Prova Global (`PG`) unificadas para todas as turmas de uma mesma Classe/Disciplina, com variante A (Manhã), variante B (Tarde) e uma variante de 2.ª chamada**, *para* **padronizar o ensino e a avaliação como a escola já faz (DESC-RESP §1)**.
- **Rastreabilidade:** `RN-01` (sub-regra nova de 2.ª chamada — numeração no [[01 - Dominio e Regras|DOC-01]]) | `Fluxo 03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Utilizador autenticado como `COORD_DISC` vinculado à disciplina; trimestre `Aberto / Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Publicação da Dosificação e das Variantes da `PT`):**
    - **Dado** que o `COORD_DISC` de *Contabilidade Financeira* seleciona a `11ª Classe` — `I Trimestre`,
    - **Quando** submete as unidades temáticas semanais e anexa a matriz e os critérios da `PT` nas variantes A (Manhã), B (Tarde) e de 2.ª chamada, e o Coordenador para a Área Pedagógica (papel `SUB_PED`) dá o visto,
    - **Então** todos os professores (`PROF`) alocados a *Contabilidade Financeira* na 11ª classe visualizam a dosificação no seu painel e ficam habilitados a lançar a coluna `PT` na data calendarizada.
  - **Cenário 2 (Exceção 🟡 — III Trimestre sem `PT`):**
    - **Dado** o `III Trimestre`,
    - **Quando** o `COORD_DISC` prepara as provas,
    - **Então** o sistema só aceita a **Prova Global (`PG`)**, também com variantes A, B e de 2.ª chamada: o III Trimestre não tem `PT` (DESC-L1 A1; ponto de controlo **E2** — `Q-025`).
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um `PROF` sem o cargo `COORD_DISC` dessa disciplina,
    - **Quando** tenta publicar a dosificação ou as variantes da prova,
    - **Então** a API rejeita com `HTTP 403 Forbidden`.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `dosificacoes_trimestrais` com as variantes das provas, com visto do `SUB_PED`.

---

### `US-PED-02`: Registar Faltas por Tempo Letivo e por Tipo, Justificar com Formulário Numerado e Aplicar a Retenção Automática por Excesso de Faltas
- **História:** *Como* **Professor (`PROF`)**, **Director de Turma (`DIR_TURMA`)** e **Coordenador para a Área Pedagógica (papel `SUB_PED`)**, *queremos* **que o professor registe as faltas em cada tempo letivo da aula prevista no horário, distinguindo faltas por não comparência e por indisciplina, e que a justificação seja um formulário numerado aprovado pelo Director de Turma e pelo Coordenador para a Área Pedagógica, abatida automaticamente em todas as disciplinas afetadas**, *para* **cumprir a regra de assiduidade (`RN-03`) sem obrigar o aluno a mostrar a justificação a cada professor**.
- **Rastreabilidade:** `RN-03`, `RN-12.13`, `RN-15.1` | `Fluxo 03` | `US-HOR-06`, `US-DIS-01`, `US-COM-02`, `US-PNL-08` | DESC-L1 A8; DESC-RESP R1, R3 | `COR-LEG-13`, `COR-LEG-14`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Turma e trimestre `Abertos / Em Curso`; **aula `PREVISTA` do horário publicado** (`US-HOR-05`); limite de faltas 🟡 parametrizado no Ano Letivo (fator por tempos semanais, por trimestre ou anual — sem fonte publicada, `COR-LEG-13`, `Q-LEG-04`; ponto de controlo **E2**).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Tempo Duplo Conta 2 Faltas e Faltas Parciais por Tempo):**
    - **Dado** um bloco de 2 tempos de *Matemática* (4 tempos semanais, limite de `12` faltas injustificadas com fator `3`) na `CG10A-T`,
    - **Quando** o `PROF` marca o aluno `N.º 08` como ausente nos dois tempos e o aluno `N.º 21` só no 2.º tempo,
    - **Então** o aluno `N.º 08` fica com **2 faltas** por não comparência e o `N.º 21` com **1 falta** (DESC-RESP R1; `RN-12.13`).
  - **Cenário 2 (Sucesso — Justificação Numerada Abate em Todas as Disciplinas):**
    - **Dado** que o aluno `N.º 08` faltou a um dia inteiro (*Matemática* 2 tempos, *Língua Portuguesa* 1, *Educação Física* 1) e o encarregado entrega o formulário de justificação com atestado,
    - **Quando** o `DIR_TURMA` regista o formulário (`N.º __/IPCAG/ano`, intervalo de dias, motivo, anexos) e o Coordenador para a Área Pedagógica o aprova,
    - **Então** as **4 faltas** passam a `Justificadas` nas 3 disciplinas afetadas, sem ação de cada professor, e são abatidas dos contadores de `Faltas Injustificadas`.
  - **Cenário 3 (Sucesso — Disparo Automático de Retenção por Faltas `RF`):**
    - **Dado** que o limite de faltas injustificadas da disciplina é `12` e o aluno já acumula `12`,
    - **Quando** o `PROF` regista a `13ª` falta injustificada,
    - **Então** o sistema altera imediatamente a situação do aluno naquela disciplina para **`Retido por Faltas (RF)`**, bloqueia a aprovação por frequência, impede o acesso ao Exame de Recurso nessa disciplina e marca a perda do direito à confirmação automática de matrícula, salvo justificação (`COR-LEG-14`, `US-MAT-02`).
  - **Cenário 4 (Bloqueio RBAC — Justificação sem as Duas Aprovações):**
    - **Dado** um utilizador `PROF` que não é o `DIR_TURMA` da turma (ou uma justificação aprovada só pelo `DIR_TURMA`),
    - **Quando** tenta alterar o estado de uma falta para `Justificada`,
    - **Então** o sistema nega a operação com `HTTP 403 Forbidden`: *"A justificação de faltas exige o Director de Turma e o Coordenador para a Área Pedagógica"* 🟡 (circuito descrito pela escola, a confirmar — `Q-032`).
  - **Cenário 5 (Bloqueio — Falta por Indisciplina):**
    - **Dado** uma falta com `tipo_falta = INDISCIPLINA` (`US-DIS-01`),
    - **Quando** é incluída num formulário de justificação,
    - **Então** o sistema recusa justificá-la 🟡 (`RN-15.1.3`, `Q-C13-03`).
  - **Cenário 6 (Bloqueio — Falta numa Aula Não Lecionada):**
    - **Dado** uma aula registada como `Não Lecionada` (`US-HOR-07`),
    - **Quando** o `PROF` tenta marcar faltas nesse tempo,
    - **Então** o sistema recusa: só há faltas em aulas lecionadas (`RN-12.13`).
- **Pós-condições e Efeitos Colaterais:** Contadores de faltas justificadas, injustificadas e por indisciplina atualizados na Mini-Pauta; `retido_por_faltas` atualizado em tempo real; aviso `FALTAS_50`/`FALTAS_80` (`US-COM-02`) e alerta precoce (`US-PNL-08`) quando os limiares são atravessados.

---

### `US-PED-03`: Conceder e Homologar Dispensa Médica (`DISP`) com Ajuste Neutro no Denominador da Média
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **homologar o estado `Dispensado (DISP)` por junta/atestado médico em disciplinas elegíveis (como Educação Física)**, *para* **que o aluno fique isento de avaliação prática sem sofrer reprovação nem redução da sua média geral (`RN-01`)**.
- **Rastreabilidade:** `RN-01`, `RN-06` | `Fluxo 03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Disciplina marcada na Matriz Curricular com `permite_dispensa_medica = TRUE`; Atestado Médico carregado pelo `OP_PED` e conferido pelo `CHEFE_SEC_PED` (matriz D4a).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Homologação de `DISP` e Recálculo do Denominador):**
    - **Dado** que um aluno da 10ª classe possui `10` disciplinas na matriz curricular e apresenta Atestado Médico válido para *Educação Física*,
    - **Quando** o `SUB_PED` homologa a Dispensa Médica,
    - **Então** as células de `MTP`, `PP`, `PT`, `M1`–`M3`, `CF`, `PG` e `CA` de *Educação Física* para esse aluno ficam bloqueadas exibindo `'DISP'`, a disciplina é considerada regularizada e a Média Anual da 10ª classe desse aluno passa a dividir o somatório das notas por **`9` disciplinas** (em vez de `10`).
  - **Cenário 2 (Bloqueio — Tentativa de Dispensar Disciplina Nuclear ou Científica):**
    - **Dado** uma disciplina com `permite_dispensa_medica = FALSE` (ex.: *Língua Portuguesa*, *Matemática* ou *Contabilidade Financeira*),
    - **Quando** o operador tenta registar uma Dispensa Médica `DISP`,
    - **Então** o sistema bloqueia a operação (`HTTP 422 Unprocessable Entity`): *"Esta disciplina é de avaliação obrigatória pelo MED e não admite regime de Dispensa Médica (DISP)"*.
- **Pós-condições e Efeitos Colaterais:** Estado da disciplina do aluno marcado como `DISP`; registo de homologação gravado em `audit_logs`.

---

### `US-PED-04`: Lançar as Notas (`MTP`, `PP`, `PT`) na Mini-Pauta com Persistência *Offline-First*, 2.ª Chamada e Arredondamento MED
- **História:** *Como* **Professor (`PROF`)**, *quero* **lançar as notas parcelares (`MTP`, `PP`, `PT` — impressas também como `MAC`, `NPP`, `NPT` no modelo da escola) na Mini-Pauta da minha turma, mesmo sem internet (*Offline-First*), com cálculo automático das médias trimestrais pela regra de arredondamento do MED (`>= 0,5` para cima)**, *para* **cumprir os prazos de lançamento sem perder trabalho durante falhas de energia ou internet no Panguila (`RN-01`, `RN-10`)**.
- **Rastreabilidade:** `RN-01` (sub-regra nova de 2.ª chamada), `RN-04`, `RN-10`, `RN-16.15` | `Fluxo 03` | `US-CTA-09` | DESC-L1 A1, A2 | `COR-LEG-26`, `COR-LEG-27`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Professor com alocação ativa na `turma_disciplina_id`; trimestre no estado `Aberto / Em Curso`; fórmulas 🟡 parametrizadas (modelo provisório do [[00.2 - Mapa de Integracao v2.0|INT-V2]] §3.3; ponto de controlo **E2** — recálculo de pautas, `Q-025`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Cálculo Automático de `M1` com Regra `round_med`):**
    - **Dado** que o `PROF` digita no I Trimestre para o aluno `N.º 01` as notas `MTP = 13`, `PP = 14` e `PT = 14` (média exata $= 41 / 3 = 13,666...$), e para o aluno `N.º 02` `MTP = 9`, `PP = 10` e `PT = 9,5` (média exata $= 28,5 / 3 = 9,50$),
    - **Quando** o motor calcula $M_1 = \text{round\_med}((MTP + PP + PT) / 3)$,
    - **Então** o sistema exibe e grava **`M1 = 14`** para o aluno `N.º 01` e **`M1 = 10`** para o aluno `N.º 02`.
  - **Cenário 2 (Sucesso 🟡 — III Trimestre sem `PT`):**
    - **Dado** o `III Trimestre`,
    - **Quando** o `PROF` abre a Mini-Pauta,
    - **Então** só tem as colunas `MTP` e `PP` para formar `M3` (fórmula exata por confirmar — `Q-025`), seguidas de `CF` e da `PG` (`US-PED-06`).
  - **Cenário 3 (Exceção — Prova de 2.ª Chamada Pendente):**
    - **Dado** que o aluno `N.º 17` faltou à `PT` por motivo justificado e validado pelo `DIR_TURMA` e pelo `SUB_PED`,
    - **Quando** o `PROF` marca a célula como *2.ª chamada*,
    - **Então** a célula fica `PENDENTE (2.ª chamada)`, a `M1` do aluno não é calculada até à nota da prova de 2.ª chamada, e a Mini-Pauta não pode ser submetida ao Conselho de Notas enquanto houver células pendentes.
  - **Cenário 4 (Sucesso — Persistência *Offline-First* e Sincronização Automática):**
    - **Dado** que a ligação à internet cai enquanto o `PROF` preenche as notas de `42` alunos na Mini-Pauta (turmas reais de 40–45 alunos),
    - **Quando** o `PROF` clica em *"Guardar Rascunho Local"* (desbloqueio com PIN local — `US-CTA-09`),
    - **Então** os dados ficam persistidos localmente no `IndexedDB` cifrado com o indicador `Pendente de Sincronização (42 registos)` e, assim que a rede LAN/Internet regressa, são sincronizados automaticamente em lote idempotente com o servidor, gravando `lancado_por_usuario_id`.
  - **Cenário 5 (Bloqueio — Professor Tenta Aceder a Mini-Pauta de Outra Turma/Disciplina):**
    - **Dado** que o `PROF` não possui vínculo ativo em `alocacoes_docentes` para a turma `CG12B-T`,
    - **Quando** tenta ler ou editar a Mini-Pauta dessa turma,
    - **Então** o servidor retorna `HTTP 403 Forbidden`.
- **Pós-condições e Efeitos Colaterais:** Registos gravados em `avaliacoes_trimestrais` vinculados a `(matricula_id, turma_disciplina_id, trimestre)`; os rótulos impressos (`MTP`/`PP`/`PT` ou `MAC`/`NPP`/`NPT`) são parâmetro do modelo de documento.

---

### `US-PED-05`: Executar Substituição Docente a Meio do Ano Letivo Mantendo a Mini-Pauta Intacta
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **substituir um professor titular por outro professor a meio do ano letivo numa disciplina/turma sem que nenhuma nota ou falta já lançada se perca**, *para* **garantir continuidade pedagógica total através do desacoplamento estrutural entre Professor e Notas (`RN-04`)**.
- **Rastreabilidade:** `RN-04`, `RN-10`, `RN-12.14.4` | `Fluxo 03` | `US-HOR-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** `Professor A` alocado à `turma_disciplina_id` com notas já lançadas no I Trimestre e/ou parcialmente no II Trimestre; `Professor B` registado e ativo no RH.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transição de Titularidade sem Perda de Dados):**
    - **Dado** que o `Professor A` lançou todas as notas do I Trimestre e o `MTP` do II Trimestre na turma `GRH11A-M`,
    - **Quando** o `SUB_PED` encerra a alocação do `Professor A` (`data_fim = hoje`, `motivo = Licença Médica`) e cria nova alocação para o `Professor B` (`data_inicio = hoje`) na mesma `turma_disciplina_id`,
    - **Então** o `Professor A` perde imediatamente permissão de escrita na Mini-Pauta, o `Professor B` passa a ver a mesma Mini-Pauta com 100% das notas do I Trimestre e o `MTP` do II Trimestre intactos (preservando nos metadados que aqueles campos foram originalmente lançados pelo `Professor A`), podendo lançar `PP` e `PT` normalmente.
  - **Cenário 2 (Bloqueio — Substituto com Choque de Horário):**
    - **Dado** que o `Professor B` já tem, no horário publicado, uma aula noutra turma num dos tempos desta disciplina na `GRH11A-M`,
    - **Quando** o `SUB_PED` tenta criar a alocação do `Professor B`,
    - **Então** o sistema bloqueia e mostra o choque de professor (dia, tempo e turma), sugerindo alterar o horário com nova versão (`RN-12.14.4`, `US-HOR-09`).
- **Pós-condições e Efeitos Colaterais:** Atualização em `alocacoes_docentes`; evento `SUBSTITUICAO_DOCENTE` registado em `audit_logs`.

---

### `US-PED-06`: Fechar o Conselho de Notas, Calcular `CF`, `PG` e `CA`, Exame de Recurso e Deliberar a Transição
- **História:** *Como* **Director de Turma (`DIR_TURMA`)** e **Subdirector Pedagógico (`SUB_PED`)**, *queremos* **consolidar a Pauta Geral da turma no Conselho de Notas, calcular a Classificação de Frequência (`CF`) e a Classificação Anual (`CA`) com a Prova Global (`PG`), apurar quem vai a Exame de Recurso, confirmar o comportamento e executar o motor de deliberação anual**, *para* **determinar quem aprova, quem transita com deficiência e quem fica retido, com o veto de Língua Portuguesa + disciplina nuclear só onde se aplica (10ª e 11ª)**.
- **Rastreabilidade:** `RN-01`, `RN-02`, `RN-03`, `RN-05`, `RN-15.7`, `RN-17.14` | `Fluxo 04` | `US-DIS-04`, `US-PNL-10`, `US-PNL-12` | DESC-L1 A1, A7, A10; DESC-RESP §1 | `COR-LEG-13`, `COR-LEG-26`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (conselho trimestral) / `E4` (deliberação anual, recurso)`.
- **Pré-condições:** Mini-Pautas da turma sem células em branco e **sem provas de 2.ª chamada pendentes** 🟡 (E2 — `RN-01.3`); **nenhum conflito de sincronização pendente na turma** (`IND-13` — `US-PNL-10`); no fim do ano, `PG` lançada. Fórmulas, limiares e número máximo de deficiências 🟡 parametrizados (ponto de controlo **E2** — `Q-025`, `Q-031`, `Q-LEG-03`, `Q-LEG-06`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — `CF`, `PG` e `CA`):**
    - **Dado** um aluno com $M_1 = 8$, $M_2 = 9$ e $M_3 = 9$ ($CF = \text{round\_med}(26/3) = \text{round\_med}(8,67) = 9$ valores) que obtém `PG = 12` valores,
    - **Quando** o sistema calcula a classificação anual,
    - **Então** aplica $CA = \text{round\_med}(CF \times 0,6 + PG \times 0,4) = \text{round\_med}(5,4 + 4,8) = \text{round\_med}(10,2) = \mathbf{10\text{ valores}}$ e o aluno fica **Aprovado** na disciplina (`CA ≥ 10`).
  - **Cenário 2 (Sucesso 🟡 — Acesso ao Exame de Recurso):**
    - **Dado** um aluno com `CF = 8` e `PG = 6` ($CA = \text{round\_med}(4,8 + 2,4) = 7$),
    - **Quando** o conselho fecha a Pauta Geral,
    - **Então** o aluno fica **admitido ao Exame de Recurso** (julho) por ter `CA < 10` e `CF ≥ 7`; a classificação depois do recurso usa a fórmula parametrizada do Ano Letivo, por confirmar (`Q-025`, `Q-LEG-03`). O antigo cálculo `40% MFD + 60% Exame` deixa de ser o valor por omissão.
  - **Cenário 3 (Exceção — Sem Acesso ao Recurso):**
    - **Dado** um aluno com `CF = 6` e `CA = 6`,
    - **Quando** o conselho fecha a Pauta Geral,
    - **Então** o aluno não é admitido ao Exame de Recurso nessa disciplina (`CF < 7`).
  - **Cenário 4 (Sucesso — Transição com Deficiência na 10ª e 11ª Classes):**
    - **Dado** um aluno da `10ª Classe` que no final do ano (depois do recurso) ficou com **2 disciplinas** com `8` valores (*Matemática* e uma disciplina nuclear do curso), mas **aprovou a Língua Portuguesa**,
    - **Quando** o motor executa a deliberação anual,
    - **Então** o aluno recebe **`Transita com Deficiência`** para a 11ª classe (até `2` disciplinas com `7–9` — parâmetro) e as 2 disciplinas são gravadas em `cadeiras_em_atraso`.
  - **Cenário 5 (Bloqueio / Veto — Língua Portuguesa E uma Disciplina Nuclear na 10ª ou 11ª):**
    - **Dado** um aluno da `10ª` ou `11ª Classe` que reprovou só a **2 disciplinas** (ambas com `8`), sendo uma **Língua Portuguesa** e a outra uma **disciplina nuclear do curso** (`is_nuclear = TRUE`),
    - **Quando** o motor executa a deliberação anual,
    - **Então** aplica o veto (`RN-02`) e atribui **`Não Transita (Retido por LP + Nuclear)`**.
  - **Cenário 6 (Bloqueio — 12ª Classe: Aprova a Todas e 0 Cadeiras em Atraso):**
    - **Dado** um aluno da `12ª Classe` (que já não tem Língua Portuguesa — DESC-L1 A7) com $\ge 1$ disciplina com `CA < 10` depois do recurso, **ou** com uma cadeira em atraso da 10ª/11ª por eliminar,
    - **Quando** o motor executa a deliberação anual,
    - **Então** o aluno fica **`Não Transita (Retido)`** na 12ª Classe e não passa à 13ª (`Q-031`).
  - **Cenário 7 (Bloqueio — Conselho com 2.ª Chamada ou Sincronização Pendente):**
    - **Dado** uma prova de 2.ª chamada por lançar ou um conflito de sincronização por decidir na turma,
    - **Quando** o `DIR_TURMA` tenta passar a turma a `Em Conselho de Notas`,
    - **Então** o sistema bloqueia e lista as células e os conflitos pendentes.
  - **Cenário 8 (Sucesso — Comportamento e Estatísticas na Pauta Geral):**
    - **Dado** as propostas de comportamento do `DIR_TURMA` (`US-DIS-04`),
    - **Quando** o conselho as confirma e o `SUB_PED` e o `DIR_GERAL` homologam a Pauta Geral,
    - **Então** o comportamento fica fechado e a Pauta Geral (`DOF-05`) imprime as estatísticas reais — positivas e negativas por disciplina, transitam, transitam com deficiência, desistentes e não transitam, por género (`US-PNL-12`).
- **Pós-condições e Efeitos Colaterais:** Pauta Geral trancada em `Fechado / Homologado`; deliberações anuais gravadas; no I Trimestre dispara `lista_chamada_congelada = TRUE`; no III Trimestre alimenta `cadeiras_em_atraso`, as propostas de passagem (`US-PAS-02`) e os mapas do GEPE.

---

## ÉPICO 05 (`EP-DEF-13`): Cadeiras em Atraso (Exame Extraordinário) e Regime da 13ª Classe (Projecto Tecnológico, Estágio, PAP e `MFC`)

---

### `US-DEF-01`: Inscrever Aluno em Exame Extraordinário para Eliminação de Cadeiras em Atraso (10ª e 11ª Classes)
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **inscrever alunos da 11ª ou 12ª classe na época de Exame Extraordinário para eliminarem as suas disciplinas no estado `Transitado com Deficiência`**, *para* **que regularizem a sua situação curricular antes da conclusão da 12ª classe (`RN-02`)**.
- **Rastreabilidade:** `RN-02`, `RN-08`, `RN-13.8` | `Fluxo 05` | DESC-RESP §1.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Época de Exame Extraordinário aberta pelo `SUB_PED`; aluno com registo pendente em `cadeiras_em_atraso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Inscrição após Validação do Semáforo Financeiro):**
    - **Dado** que o aluno possui a disciplina *Matemática (10ª Classe)* no estado `Transitado com Deficiência`, está com as propinas em dia (ou com acordo de pagamento que liberte o semáforo — `RN-13.8`) e pagou a taxa do Exame Extraordinário por disciplina para a época de maio (🟡 paga à escola ou por RUPE — `Q-034`),
    - **Quando** o `OP_PED` vincula o recibo à inscrição de exame extraordinário,
    - **Então** o estado da cadeira em atraso muda para `Inscrito em Exame Extraordinário` e o aluno é incluído na pauta da banca examinadora.
  - **Cenário 2 (Bloqueio — Propinas em Atraso ou Emolumento Não Pago):**
    - **Dado** que o aluno possui propina vencida na Conta Corrente ou não pagou a taxa por disciplina em atraso,
    - **Quando** o `OP_PED` tenta confirmar a inscrição no Exame Extraordinário,
    - **Então** o Semáforo Financeiro bloqueia a ação com `HTTP 403 Forbidden - Pendência Financeira`.
- **Pós-condições e Efeitos Colaterais:** Registo em `cadeiras_em_atraso` atualizado para `Inscrito em Exame Extraordinário` e vinculado ao `recibo_item_id`.

---

### `US-DEF-02`: Lançar Nota de Exame Extraordinário com Registo de Livro/Folha/Termo e Extinguir Deficiência
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) e Subdirector Pedagógico (`SUB_PED`)**, *quero* **registar a nota do Exame Extraordinário exigindo obrigatoriamente o `Livro, Folha e Termo` do exame, extinguindo a deficiência se a nota for `>= 10` valores ou mantendo o bloqueio de acesso à 13ª classe se for `< 10`**, *para* **assegurar conformidade legal estrita com o MED (`RN-02`, `RN-10`)**.
- **Rastreabilidade:** `RN-02`, `RN-06`, `RN-10` | `Fluxo 05`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Aluno no estado `Inscrito em Exame Extraordinário`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Aprovação `>= 10` e Eliminação da Deficiência):**
    - **Dado** que o aluno obteve nota `12` valores no Exame Extraordinário de *Matemática (10ª Classe)*,
    - **Quando** o `CHEFE_SEC_PED` lança a nota `12`, preenche no livro de Termos de Exame (livro próprio — DESC-RESP R17) `Livro n.º 04, Folha n.º 18, Termo n.º 092` e o `SUB_PED` homologa,
    - **Então** a cadeira em atraso transita para **`Deficiência Eliminada`**, a nota `12` substitui a nota reprobatória anterior no cálculo de $MA_{10}$, e a pendência deixa de bloquear o aluno.
  - **Cenário 2 (Bloqueio Crítico — Tentativa de Fechar 12ª Classe / Ingressar na 13ª com Deficiência Não Eliminada):**
    - **Dado** um aluno da 12ª classe que aprovou a todas as disciplinas da 12ª classe, mas obteve nota `8` (`< 10`) no Exame Extraordinário de uma cadeira em atraso da 10ª ou 11ª classe,
    - **Quando** o sistema avalia a conclusão da 12ª classe ou tenta abrir o processo da `13ª Classe`,
    - **Então** a cadeira em atraso retorna a `Transitado com Deficiência` e o processo da 13ª classe fica **estritamente bloqueado** no estado `Bloqueado (Possui Cadeiras em Atraso da 10ª-12ª)`.
- **Pós-condições e Efeitos Colaterais:** Atualização em `cadeiras_em_atraso` e `exames_extraordinarios` (registo no Livro de Termos de Exame); recálculo automático da média anual da classe de origem.

---

### `US-13C-01`: Validar Aptidão para a 13ª Classe e Alocar o Estágio, o Tutor, o Supervisor e o Orientador do Projecto Tecnológico
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`)** (ou o Coordenador GIVA, se a escola o tiver — `COR-LEG-22`), *quero* **alocar para cada aluno apto da 13ª classe a Empresa Parceira, o Supervisor na empresa e o Tutor Interno do Estágio Curricular, e o Professor Orientador do Projecto Tecnológico**, *para* **gerir o regime da 13ª classe (Projecto Tecnológico, Estágio e PAP) nos termos do DP n.º 167/23, art. 31.º–33.º**.
- **Rastreabilidade:** `RN-02`, `RN-06` | `Fluxo 06` | DESC-L1 A6; DESC-RESP R20, R21 | `COR-LEG-16`, `COR-LEG-28`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Aluno com matrícula ativa na 13ª classe, 100% das disciplinas da 10ª à 12ª aprovadas (incluindo transcrição externa homologada, se transferido) e `0` Cadeiras em Atraso; lista de empresas parceiras registada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Alocação do Estágio e do Projecto Tecnológico):**
    - **Dado** que o aluno se encontra no estado `Apto para 13ª Classe` e já iniciou o Projecto Tecnológico na 12ª (`2` tempos semanais),
    - **Quando** o `COORD_CURSO` associa a empresa parceira, o nome e contacto do Supervisor na empresa, o docente Tutor Interno, o tema do Projecto Tecnológico e o docente Orientador,
    - **Então** o processo da 13ª classe muda para **`Em Estágio / Projecto Tecnológico`** (estado do DOC-01 §3.5; lista 13 do DOC-05: `EM_ESTAGIO_E_PROJECTO_TECNOLOGICO`; a PAP é a defesa do relatório de estágio) (Estágio de `20` tempos e Projecto Tecnológico de `8` tempos semanais) e o sistema habilita a emissão da **Carta de Apresentação de Estágio** (`DOF-08A`).
  - **Cenário 2 (Bloqueio — Aluno com Histórico Externo da 10ª/11ª Incompleto):**
    - **Dado** um aluno transferido de outra escola na 11ª ou 12ª classe cuja `Transcrição de Histórico Externo` não tem todas as disciplinas da matriz preenchidas e homologadas,
    - **Quando** tenta avançar no processo da 13ª classe,
    - **Então** o sistema bloqueia a transição exibindo o alerta `Histórico Curricular Incompleto (RN-06)`.
- **Pós-condições e Efeitos Colaterais:** Registo atualizado em `processos_13_classe` no estado `Em Estágio / Projecto Tecnológico`.

---

### `US-13C-02`: Homologar a Nota de Estágio, Constituir o Júri da PAP com Membros Externos, Registar a Ata e Calcular a `MFC`
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`)** e **Subdirector Pedagógico (`SUB_PED`)**, *queremos* **registar as notas do Estágio e do Projecto Tecnológico, constituir o Júri da PAP (defesa do relatório de estágio) com professores e representantes dos trabalhadores e dos empregadores, emitir a Ata de Defesa e calcular a Média Final do Curso (`MFC`)**, *para* **habilitar o Certificado (emitido pela escola) e o pedido do Diploma (emitido pelo Ministério) sem erros de cálculo (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-06`, `RN-08`, `RN-10` | `Fluxo 06` | DESC-RESP R20, R21 | `COR-LEG-16`, `COR-LEG-17`, `COR-LEG-28`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Processo da 13ª classe em `Apto para Defesa` (transição `prepararDefesaPublica` a partir de `Em Estágio / Projecto Tecnológico` — DOC-01 §3.5); **estágio concluído com parecer positivo do orientador**, `0` cadeiras em atraso, propinas em dia e Emolumento de Defesa da PAP pago (R20); pesos da `MFC` 🟡 parametrizados na matriz do curso (Média do Plano Curricular, Estágio, Projecto Tecnológico, PAP — `Q-030`, `Q-LEG-07`; ponto de controlo **E2**).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Júri com Membros Externos, Defesa e Cálculo da `MFC`):**
    - **Dado** que o aluno tem `Nota_Estagio = 15` e a nota do Projecto Tecnológico `14` homologadas, o Semáforo Financeiro verde e o Júri constituído por professores e por representantes dos trabalhadores e dos empregadores (empresa parceira),
    - **Quando** o aluno defende o relatório de estágio obtendo `Nota_PAP = 16`, e o `COORD_CURSO`, o `SUB_PED` e o `DIR_GERAL` (assinatura da Coordenadora Geral — título configurado) homologam a Ata de Defesa,
    - **Então** o sistema calcula:
      1. $MA_{10}$, $MA_{11}$ e $MA_{12}$ (excluindo `DISP` do denominador e integrando transcrições externas e exames extraordinários);
      2. $MPC = \text{round\_med}((MA_{10} + MA_{11} + MA_{12}) / 3)$;
      3. a **`MFC`** com os pesos homologados na matriz do curso, encerrada por `round_med` — sem contar o estágio duas vezes (`COR-LEG-16`) —, transitando o processo para **`Defendido e Homologado`** e gerando o PDF da **Ata de Defesa da PAP** (`DOF-08B`).
  - **Cenário 2 (Bloqueio — Pré-requisito da Defesa em Falta):**
    - **Dado** que o aluno não tem a nota de estágio homologada (🟡 um eventual mínimo é parâmetro, não fixado no DOC-01 — `RN-06.3`), **ou** não tem o parecer positivo do orientador, **ou** tem propina vencida / taxa de defesa por pagar,
    - **Quando** o `COORD_CURSO` tenta passar o aluno a `Apto para Defesa` e agendar o júri,
    - **Então** o sistema bloqueia a operação (`HTTP 403` / `HTTP 422`) indicando o requisito pendente.
  - **Cenário 3 (Bloqueio 🟡 — Pesos da `MFC` por Homologar):**
    - **Dado** que os pesos da `MFC` do curso ainda não foram homologados (`Q-030`),
    - **Quando** a Ata de Defesa é homologada,
    - **Então** o sistema grava as notas, não calcula a `MFC` e mostra *"Pesos da MFC por homologar na matriz do curso"*.
  - **Cenário 4 (Bloqueio — Júri só com Docentes):**
    - **Dado** um júri constituído só por docentes da escola,
    - **Quando** o `COORD_CURSO` tenta agendar a defesa,
    - **Então** o sistema avisa que o júri exige representantes dos trabalhadores e dos empregadores (DP n.º 167/23, art. 33.º; composição exata a confirmar — `Q-LEG-07`) e não deixa agendar.
- **Pós-condições e Efeitos Colaterais:** Ata de defesa gerada e registada no livro de Atas da PAP; `MFC` gravada de forma imutável no processo do aluno; estado `Defendido e Homologado`.

---

## ÉPICO 06 (`EP-TES`): Tesouraria Anti-Fraude (Borderô por Saldo e Crédito do Aluno), Motor de Bolsas, Documentos Fiscais e Notas de Crédito (DP n.º 71/25) e Fecho de Caixa por Turno

---

### `US-TES-01`: Parametrizar Tabelas de Propinas, Multas por Mora e Emolumentos em Kwanzas (`AOA`)
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **configurar para cada Ano Letivo os valores das 10 prestações de propina por Curso/Classe, o dia de vencimento, a regra de multa por mora e a tabela de emolumentos em Kwanzas (`AOA`), indicando os que se pagam por RUPE ao Estado**, *para* **padronizar toda a cobrança da Tesouraria sem valores arbitrários**.
- **Rastreabilidade:** `RN-07`, `RN-08`, `RN-09`, `RN-13.3` | `Fluxo 01` e `Fluxo 07` | DESC-RESP R9, R15.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Utilizador autenticado como `SUB_ADM` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Configuração e Homologação da Tabela Anual em `AOA`):**
    - **Dado** que o `SUB_ADM` define a propina mensal em `15.000,00 Kz` (valor ilustrativo; **10 prestações de setembro a junho**, setembro pago na matrícula), vencimento ao dia `10` de cada mês (a escola usa o dia 10 ou 15), a multa por mora em `parametros_cobranca` (`RN-13.3`) e os emolumentos (Taxa de Admissão, Matrícula, Declaração, Exame Extraordinário por disciplina, Defesa da PAP, Certificado, Cartão de Estudante), marcando 🟡 os que se pagam por **RUPE** ao Estado (`Q-034`),
    - **Quando** o `DIR_GERAL` homologa a tabela,
    - **Então** os valores ficam ativos e trancados para todas as operações de Conta Corrente daquele Ano Letivo; os emolumentos RUPE não geram documento da Tesouraria do IPCAG.
  - **Cenário 2 (Bloqueio — Alterar uma Tabela Homologada):**
    - **Dado** a tabela de `2026/2027` homologada,
    - **Quando** o `SUB_ADM` tenta mudar o valor da propina,
    - **Então** o sistema recusa a edição direta e exige uma nova versão homologada, aplicada só às prestações vincendas (`RN-07.2`).
- **Pós-condições e Efeitos Colaterais:** Registos criados em `tabelas_precos_emolumentos` (propinas e rubricas de emolumento do ano) e `parametros_cobranca`.

---

### `US-TES-02`: Conceder e Homologar Bolsas de Estudo (50%/100%), Isenções Diocesanas e Descontos de Irmãos
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`) e Director Geral (`DIR_GERAL`)**, *quero* **associar bolsas de estudo (`50%`, `100%`, quotas sociais da Diocese de Caxito, descontos de irmãos ou filhos de funcionários) à matrícula do aluno**, *para* **que o sistema abata automaticamente o benefício na geração das propinas mensais (`RN-07`)**.
- **Rastreabilidade:** `RN-07`, `RN-08`, `RN-10` | `RF-C10-25` | `Fluxo 02` | `US-PIN-07`, `US-PAS-04`, `US-COB-09` | `MOD-TES-TAB`, `beneficios_bolsas_matricula`, `comunicacoes_destinatarios` | OPS-09 `INT-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1` (`Cenário 4`: E2).
- **Pré-condições:** Matrícula do aluno criada; documento comprovativo da bolsa/parentesco registado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Aplicação de Bolsa de 50% ou Desconto Familiar):**
    - **Dado** que a propina base é `15.000,00 Kz` e o `DIR_GERAL` homologa uma `BOLSA_50` para o aluno,
    - **Quando** o motor gera as prestações mensais na Conta Corrente,
    - **Então** cada prestação armazena `valor_bruto = 15.000,00 Kz`, `valor_desconto = 7.500,00 Kz` e `valor_liquido_a_pagar = 7.500,00 Kz` no estado `A Vencer`.
  - **Cenário 2 (Sucesso — Bolseiro Integral 100% com Semáforo Financeiro Sempre Verde):**
    - **Dado** um aluno órfão assistido pela Diocese de Caxito com `BOLSA_100` homologada,
    - **Quando** as prestações mensais são geradas,
    - **Então** nascem automaticamente no estado **`Isenta (Bolseiro 100%)`** (`valor_liquido = 0,00 Kz`), mantendo o Semáforo Financeiro de propinas permanentemente verde, e o aluno entra na lista nominal de bolseiros diocesanos enviada à Diocese.
  - **Cenário 3 (Exceção — Bolsa Revogada a Meio do Ano):**
    - **Dado** uma `BOLSA_50` revogada por despacho a partir de Fevereiro,
    - **Quando** o `DIR_GERAL` homologa a revogação,
    - **Então** só as prestações `A Vencer` de Fevereiro a Junho voltam a `15.000,00 Kz`; os documentos fiscais já emitidos de Setembro a Janeiro não mudam (`RN-07.2`).
  - **Cenário 4 (Sucesso — Exportação de Mapas de Bolsas e Isenções para a Diocese de Caxito — `RF-C10-25`, `RN-07`, `OPS-09` `INT-09`):**
    - **Dado** o encerramento do período de concessão de bolsas ou a prestação periódica de contas à Diocese de Caxito,
    - **Quando** o `SUB_ADM` acede ao `MOD-TES-TAB` e comanda a emissão do relatório de bolseiros diocesanos,
    - **Então** o sistema gera o mapa consolidado de bolsas e isenções e a lista nominal de bolseiros (com identificação, curso, classe, percentagem de bolsa e impacto financeiro suportado), registando o envio em `comunicacoes_destinatarios` (`US-DOC-05`, `RF-C19-22`) com salvaguarda das regras de privacidade.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `beneficios_bolsas_matricula`; exportação em `comunicacoes_destinatarios`; evento `CONCESSAO_BOLSA` gravado em `audit_logs`.

---

### `US-TES-03`: Registar Borderô/Talão Bancário `UNIQUE`, Liquidar Propinas de Irmãos ou de Vários Meses e Guardar o Excedente como Crédito do Aluno
- **História:** *Como* **Operador de Caixa / Tesouraria (`OP_TES`)**, *quero* **registar comprovativos bancários (`Borderô / Talão / Multicaixa Express`) validando a unicidade do número de operação e controlando o `valor_total_talao` vs. `saldo_utilizado`**, *para* **permitir que um Encarregado pague vários meses ou os 2 ou mais irmãos com um único talão verdadeiro, guardar o excedente como crédito do aluno e bloquear o talão quando o saldo chega a `0,00 Kz` (`RN-09`)**.
- **Rastreabilidade:** `RN-08`, `RN-09.1`, `RN-09` (sub-regra nova de crédito do aluno — numeração no [[01 - Dominio e Regras|DOC-01]]), `RN-09.5`, `RN-10`, `RN-13.11`, `RN-13.16` | `RF-C10-10`, `RF-C10-24` | `Fluxo 07` | DESC-RESP R10, R14, R15 | `COR-LEG-02`, `COR-LEG-04`, `COR-LEG-06`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Sessão de caixa do turno aberta pelo `OP_TES`; aluno(s) com propinas ou emolumentos a pagar. O documento fiscal é **Fatura-Recibo** ou **Recibo** (DP n.º 71/25), emitido pelo software certificado através do adaptador, com numeração por tipo e ano civil nas séries da AGT (`DEC-002` (b)); o SGE emite o recibo escolar de quitação. Os números abaixo são ilustrativos (`Q-004`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Pagamento de 2 Irmãos com um Único Talão Bancário Verdadeiro):**
    - **Dado** que o Encarregado apresenta um talão do banco `BAI` com número de operação `OP-2026-778899` no valor total de **`30.000,00 Kz`** para a propina de Outubro dos dois filhos (`Irmão 1 = 15.000,00 Kz` e `Irmão 2 = 15.000,00 Kz`),
    - **Quando** o `OP_TES` regista o borderô `OP-2026-778899` (`valor_total_talao = 30.000,00 Kz`) e emite o **documento 1** para o `Irmão 1` alocando `15.000,00 Kz`,
    - **Então** o borderô fica **`Parcialmente Utilizado`** com `saldo_utilizado = 15.000,00 Kz` e `saldo_disponivel = 15.000,00 Kz`;
    - **E quando** a seguir o `OP_TES` abre a conta do `Irmão 2`, informa o mesmo código e emite o **documento 2** alocando os restantes `15.000,00 Kz`,
    - **Então** o sistema emite o segundo documento e o borderô passa a **`Esgotado / Trancado`** (`saldo_utilizado = 30.000,00 Kz`, `saldo_disponivel = 0,00 Kz`).
  - **Cenário 2 (Bloqueio Anti-Fraude — Reutilizar um Borderô Esgotado):**
    - **Dado** que o borderô `OP-2026-778899` já está `Esgotado / Trancado`,
    - **Quando** alguém o tenta usar para a propina ou um emolumento de um 3º aluno (ou de outro mês),
    - **Então** o sistema bloqueia com `HTTP 409 Conflict — ALERTA ANTI-FRAUDE`: *"Este comprovativo bancário (OP-2026-778899) já foi 100% consumido nos documentos RC 2026/00105 e RC 2026/00106 (formato ilustrativo — `Q-004`). Saldo disponível: 0,00 Kz"*, e grava a tentativa em `audit_logs`.
  - **Cenário 3 (Bloqueio — Talão com Valor a Menos Não Quita a Prestação):**
    - **Dado** um borderô com `saldo_disponivel = 10.000,00 Kz`,
    - **Quando** o `OP_TES` tenta liquidar uma prestação de `15.000,00 Kz` só com esse borderô,
    - **Então** o sistema impede a emissão com `HTTP 422`: *"O valor a liquidar (15.000,00 Kz) excede o saldo disponível neste borderô (10.000,00 Kz)"* — não há pagamento parcial de uma prestação (DESC-RESP R10).
  - **Cenário 4 (Sucesso 🟡 — Excedente Fica como Crédito do Aluno):**
    - **Dado** um talão de `20.000,00 Kz` para a propina de Outubro de `15.000,00 Kz`,
    - **Quando** o `OP_TES` emite o documento de `15.000,00 Kz`,
    - **Então** os `5.000,00 Kz` excedentes ficam como **crédito do aluno** (saldo do borderô ligado ao aluno e ao encarregado), visível na Conta Corrente e proposto no pagamento da prestação seguinte.
  - **Cenário 5 (Bloqueio — Borderô em Investigação):**
    - **Dado** um borderô marcado `NAO_ENCONTRADO` na conciliação bancária (`US-COB-12`),
    - **Quando** o `OP_TES` tenta usar o seu saldo,
    - **Então** o sistema recusa até a investigação terminar (`RN-13.16`).
  - **Cenário 6 (Contingência do Adaptador Fiscal — o Balcão Não Bloqueia — `RF-C10-10`, `RN-09.5`, `DEC-002` (b)):**
    - **Dado** que, durante o atendimento na Tesouraria (`MOD-TES-CXA`), a ligação ao software certificado falha (sem internet, software indisponível ou erro do adaptador),
    - **Quando** o `OP_TES` liquida a propina ou o emolumento,
    - **Então** o sistema emite o **recibo escolar provisório** (quitação académica, sem aspeto de fatura — DP n.º 71/25, art. 4.º, n.º 9), regista o documento em `recibos_oficiais` com `estado_emissao_fiscal = PENDENTE_EMISSAO` e põe o pedido `EMITIR` em `fila_emissao_fiscal`, sem bloquear o atendimento;
    - **E quando** o canal volta, o adaptador envia os pedidos em fila, grava `fatura_externa_numero` e `fatura_externa_hash` e passa o documento a `EMITIDO`; uma rejeição passa-o a `REJEITADO_AGT` e alerta o `SUB_ADM`;
    - **E** os pedidos ainda por confirmar aparecem no fecho de caixa do turno. A contingência fiscal junto da AGT (emissão "em contingência", comunicação posterior, bloqueio após 60 dias) é do software certificado, não do SGE.
  - **Cenário 7 (Sucesso 🟡 — Registo de Emolumento Liquidado por RUPE — `RF-C10-24`, `RN-08`, `RN-13.11`, `Q-034`):**
    - **Dado** o pedido de um ato ou documento escolar cujo pagamento deva ser recolhido a favor do Tesouro Nacional via RUPE (Referência Única de Pagamento ao Estado),
    - **Quando** o encarregado apresenta a prova de liquidação da RUPE e o `OP_TES` valida o comprovativo e insere a referência no sistema,
    - **Então** o sistema liquida o emolumento associado para libertar o serviço na Secretaria Pedagógica, regista o comprovativo sem gerar documento de faturação comercial ou receita própria do IPCAG, e discrimina esta receita estadual nos mapas de conferência e fecho de caixa (`US-TES-05`).
- **Pós-condições e Efeitos Colaterais:** Documento(s) fiscal(is) emitido(s) em `AOA`; propinas atualizadas para `Paga`; `borderos_bancarios` e `itens_recibo` atualizados atomicamente (`SELECT ... FOR UPDATE`).

---

### `US-TES-04`: Emitir Nota de Crédito ou Declarar Fraude de Borderô sem `DELETE`/`UPDATE` nos Documentos Fiscais (DP n.º 71/25)
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **corrigir erros de faturação ou invalidar talões fraudulentos exclusivamente através de uma Nota de Crédito (`NC`) sequencial com a menção "anulação" ou "rectificação" e a referência ao documento original**, *para* **cumprir a proibição de apagar ou editar documentos fiscais emitidos (DP n.º 71/25, de 20 de Março, que revogou o DP n.º 292/18 — `COR-LEG-01`, `COR-LEG-03`) (`RN-09`)**.
- **Rastreabilidade:** `RN-08`, `RN-09`, `RN-10`, `RN-13.16`, `RN-13.20` | `Fluxo 07` | `US-COB-12` | `COR-LEG-01`, `COR-LEG-02`, `COR-LEG-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Documento fiscal emitido pelo software certificado e registado em `recibos_oficiais` (`DEC-002` (b)); a Nota de Crédito ou o Recibo de Estorno é pedido ao software certificado pela fila (`ANULAR_NC`/`ANULAR_RE`); utilizador autenticado como `SUB_ADM` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Bloqueio Absoluto de `DELETE` / `UPDATE` nos Documentos Fiscais):**
    - **Dado** qualquer Fatura, Fatura-Recibo ou Recibo emitido,
    - **Quando** qualquer utilizador (ou instrução SQL direta da aplicação) tenta executar `DELETE` ou `UPDATE` de valores sobre a linha do documento,
    - **Então** a *trigger* `trg_prevent_recibo_mutation` do PostgreSQL aborta a transação com exceção de violação de imutabilidade fiscal.
  - **Cenário 2 (Sucesso — Nota de Crédito por Erro Operacional):**
    - **Dado** que o documento `FR 2026/00150` foi emitido por engano no aluno errado,
    - **Quando** o `SUB_ADM` aprova a **Nota de Crédito `NC 2026/00012`** (número ilustrativo — `Q-004`) com a menção "anulação", a referência ao `FR 2026/00150` e a justificação,
    - **Então** o documento original mantém-se registado com a referência à `NC 2026/00012`, a propina do aluno volta a `A Vencer` (ou `Em Atraso com Multa`) e o valor volta ao `saldo_disponivel` do borderô para ser aplicado no aluno correto.
  - **Cenário 3 (Sucesso 🟡 — Invalidação de Borderô Falso em Cascata):**
    - **Dado** que a conciliação bancária (`US-COB-12`) deteta que um borderô usado em 2 documentos era falsificado,
    - **Quando** o `SUB_ADM` aciona *"Declarar Borderô Invalidado por Fraude"*,
    - **Então** o borderô passa permanentemente a **`Invalidado por Fraude`**, o sistema emite Notas de Crédito para todos os documentos ligados (ou a anulação do recibo, se o contabilista o confirmar — `Q-LEG-16`), reabre as dívidas com multa nas Contas Correntes dos alunos (**Semáforo Financeiro Vermelho**) e grava o alerta de fraude em `audit_logs`.
- **Pós-condições e Efeitos Colaterais:** Registo em `notas_estorno` (nome da tabela a rever no [[05 - Modelagem de Dados|DOC-05]]) com o tipo `NC`; reabertura automática de débitos na Conta Corrente; trilha gravada em `audit_logs`.

---

### `US-TES-05`: Executar e Homologar o Fecho de Caixa Diário por Turno Segregado por Canal de Pagamento
- **História:** *Como* **Operador de Tesouraria (`OP_TES`)**, **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)** e **Subdirector Administrativo (`SUB_ADM`)**, *queremos* **emitir no final de cada turno (Manhã e Tarde) o Mapa de Fecho de Caixa separado por canal (`TPA`, `Depósito / Transferência Bancária`, `Multicaixa Express` e, quando aplicável, `RUPE`), conferido pela Secretaria Geral e homologado pelo `SUB_ADM`**, *para* **conferência física dos talões, assinatura e trancamento diário (`RN-09.2`)**.
- **Rastreabilidade:** `RN-09.2`, `RN-10`, `RN-13.18` | `Fluxo 07` | `US-COB-14` | DESC-RESP R13 | `DOF-11C`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Sessão de caixa do turno aberta com movimentos no dia.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Emissão, Conferência e Homologação do Mapa de Fecho de Caixa por Turno):**
    - **Dado** que o `OP_TES` concluiu o atendimento do `Turno da Manhã`,
    - **Quando** aciona *"Fechar Caixa do Turno"*,
    - **Então** o sistema consolida todos os documentos fiscais e Notas de Crédito do turno, apresenta os subtotais de **`TPA`**, **`Depósito / Transferência`**, **`Multicaixa Express`** e **`RUPE`** (se houver), gera o `DOF-11C` com campos de assinatura (títulos configurados) para o `OP_TES`, a conferência do `CHEFE_SEC_GER` e a homologação do `SUB_ADM`, e depois da homologação impede qualquer lançamento retroativo naquela sessão.
  - **Cenário 2 (Exceção — Nota de Crédito Depois do Fecho):**
    - **Dado** uma sessão de caixa de ontem `Fechado e Homologado`,
    - **Quando** hoje se emite uma Nota de Crédito sobre um documento dessa sessão,
    - **Então** a Nota de Crédito conta na sessão aberta hoje e o mapa de ontem não muda (`RN-09.2`).
  - **Cenário 3 (Exceção — Operador Ausente no Fim do Turno):**
    - **Dado** uma sessão aberta cujo operador não está presente no fim do turno,
    - **Quando** o `SUB_ADM` precisa de fechar o caixa,
    - **Então** segue o fecho administrativo com conferência por outra pessoa (`US-COB-14`, `RN-13.18`); a mesma pessoa não fecha e homologa.
- **Pós-condições e Efeitos Colaterais:** Sessão de caixa trancada no estado `Fechado e Homologado`.

---

## ÉPICO 07 (`EP-DOC-AUD`): Emissão Documental (Requerimento, Declarações, Certificado e Pedido do Diploma), Semáforo Financeiro, Registo de Arquivo, QR Code, RH e Estatísticas

---

### `US-DOC-01`: Pedir e Emitir Declarações, Boletins e Guias de Transferência por Requerimento Numerado, no Prazo Legal e com Semáforo Financeiro
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **registar o pedido por requerimento numerado com talão destacável, saber logo no balcão se o aluno tem dívida, e emitir a declaração numerada dentro do prazo legal**, *para* **substituir o circuito em papel (requerimento → recibo de pedido → declaração) sem emitir documentos a alunos com dívidas vencidas (`RN-08`)**.
- **Rastreabilidade:** `RN-05`, `RN-08`, `RN-10`, `RN-11.14`, `RN-13.8`, `RN-14.5` | `Fluxo 08` | `US-COB-03`, `US-PIN-08`, `US-COM-01` | DESC-L1 A11, A13; DESC-RESP R12, R16 | `COR-LEG-20`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2` (requerimento, declarações, guia) / `E3` (boletins)`.
- **Pré-condições:** Aluno registado; pauta do trimestre/ano homologada (boletins e declarações com notas); séries anuais por tipo de documento em `series_numeracao_documental` (`N.º ___/IPCAG N.º <n.º> BGO/<ano>`, com o número da instituição como parâmetro por tipo de documento — `Q-027`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Requerimento, Talão e Declaração no Prazo):**
    - **Dado** que o encarregado pede uma Declaração de Estudante para efeitos de bolsa,
    - **Quando** o `OP_PED` regista o requerimento (dirigido à Coordenadora Geral da Comissão de Gestão — título configurado) e entrega o talão destacável com o mesmo número,
    - **Então** o sistema atribui o número do requerimento, conta o prazo de **5 dias úteis** (`COR-LEG-20`; hoje leva 3–5 dias, mais de uma semana em época alta), emite a declaração numerada (`DOF-09A`) com os campos reais (filiação, estado civil, idade, naturalidade, BI e data de emissão, residência, classe, turma, sala, período, curso, efeito) e gera o aviso `DOCUMENTO_PRONTO` (`US-COM-01`).
  - **Cenário 2 (Bloqueio Automático pelo Semáforo Financeiro — `HTTP 403`):**
    - **Dado** um aluno com a propina do mês anterior `Em Atraso (com Multa)` sem acordo de pagamento que liberte o semáforo, **ou** sem o emolumento da declaração pago (se houver taxa para as declarações dos alunos 🟡 — `Q-034`),
    - **Quando** o `OP_PED` ou o `CHEFE_SEC_PED` tenta registar o requerimento ou emitir a declaração,
    - **Então** a função `fn_verificar_aptidao_financeira` bloqueia com `HTTP 403 Forbidden`: *"Emissão bloqueada pela Tesouraria: o aluno tem propinas em atraso e/ou emolumento do documento não liquidado"*, logo no balcão.
  - **Cenário 3 (Exceção — Boletim Retido por Dívida na Reunião):**
    - **Dado** a reunião de entrega dos boletins do I Trimestre (`DOF-06`) e um aluno com propinas em atraso,
    - **Quando** o `DIR_TURMA` imprime os boletins da turma,
    - **Então** o boletim desse aluno fica **retido** (marcado na lista da reunião, sem valores em dívida) e é entregue quando o semáforo ficar verde (DESC-RESP R12).
  - **Cenário 4 (Exceção — Prazo de 5 Dias Úteis a Esgotar):**
    - **Dado** um requerimento registado há 4 dias úteis sem declaração emitida,
    - **Quando** o `CHEFE_SEC_PED` abre a lista de pedidos,
    - **Então** o pedido aparece destacado como *"prazo esgota amanhã"* e conta no painel da Direção (pedidos pendentes há mais de 3 dias — DESC-RESP R28).
  - **Cenário 5 (Sucesso — Guia de Transferência de Saída):**
    - **Dado** que o aluno não tem dívida — incluindo dívida reescalonada num acordo de pagamento, que tem de ser zero (`RN-13.8.3`) — e pagou o emolumento da *Guia de Transferência*,
    - **Quando** o `CHEFE_SEC_PED` e o `SUB_PED` homologam a transferência externa de saída no II Trimestre,
    - **Então** o sistema emite a Guia de Transferência (`DOF-09C`) com QR Code, muda a matrícula para `Transferida (Externa)`, altera as propinas futuras (a vencer) para **`Cancelada`**, anula o cartão de estudante (`US-PIN-08`) e mantém a linha do aluno no seu `N.º de Ordem` original na pauta, com a marcação `TRANSFERIDO`.
- **Pós-condições e Efeitos Colaterais:** Requerimento e documento registados em `documentos_oficiais_emitidos` com o número anual; `item_recibo_id` consumido (uso único), quando há emolumento.

---

### `US-DOC-02`: Emitir o Certificado de Habilitações e Preparar o Pedido do Diploma, com Registo de Arquivo e QR da Plataforma Nacional de Certificação
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **emitir o Certificado de Habilitações (emitido pela escola) com registo único no livro de Certificados, e exportar os dados e o pedido do Diploma de Técnico Médio (emitido e assinado pelo Ministro da Educação)**, *para* **cumprir o regime de certificação (DP n.º 167/23, art. 54.º–55.º; DP n.º 227/25) e blindar o IPCAG contra falsificações (`RN-10`)**.
- **Rastreabilidade:** `RF-C09-11` | `RN-06`, `RN-08`, `RN-10`, `RN-10.2`, `RN-11.7`, `RN-13.8.3` | `Fluxo 06` e `Fluxo 08` | `US-PIN-05`, `US-CTA-15` | `MOD-PED-DOC` | `DOF-10` | DESC-L1 A14; DESC-RESP R17, R18 | `COR-LEG-18`, `COR-LEG-19` | OPS-09 `INT-10`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Processo da 13ª classe `Defendido e Homologado` com `MFC` calculada; Semáforo Financeiro verde (0 propinas em atraso, dívida reescalonada igual a zero 🟡 `Q-C10-03`, emolumento do Certificado pago); sem pendência documental bloqueante (`US-PIN-05`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Certificado com Registo de Arquivo e QR):**
    - **Dado** um finalista da 13ª classe com `MFC = 15` valores e emolumento pago,
    - **Quando** o `CHEFE_SEC_PED` regista o Certificado no livro de Certificados (`Livro n.º 02`, número sequencial `178`; folha e termo 🟡 prática a confirmar — `COR-LEG-19`) e aciona a emissão,
    - **Então** o sistema valida que o registo é único, gera o código alfanumérico de verificação, imprime o cabeçalho real (*República de Angola / Governo da Província do Bengo / Gabinete Provincial da Educação* / IPCAG — `Q-035`), as notas curriculares, as notas do Estágio, do Projecto Tecnológico e da PAP, a `MFC`, a referência de arquivo, o **QR Code da Plataforma Nacional de Certificação** 🟡 (ou o QR próprio enquanto não houver integração — `Q-020`) e os blocos de assinatura com os títulos configurados e o carimbo ou selo branco.
  - **Cenário 2 (Sucesso — Pedido do Diploma ao Ministério):**
    - **Dado** o mesmo finalista com o Certificado emitido,
    - **Quando** o `CHEFE_SEC_PED` prepara o pedido do Diploma,
    - **Então** o SGE **não emite** o Diploma: exporta os dados e o pedido (com o nível do QNQ) para o Ministério da Educação 🟡 (`Q-021`) e o processo fica `Diploma Pedido`.
  - **Cenário 3 (Bloqueio — Registo de Arquivo em Falta ou Duplicado):**
    - **Dado** que o operador deixa em branco o número de registo ou indica um já atribuído a outro aluno,
    - **Quando** tenta emitir o Certificado,
    - **Então** o sistema rejeita com `HTTP 422` / `HTTP 409`: *"É obrigatório um registo único no livro de Certificados para emitir o Certificado"*.
  - **Cenário 4 (Bloqueio — Pendência Documental):**
    - **Dado** que o certificado da 9ª Classe do aluno está `Em Falta` com efeito `BLOQUEIA_CERTIFICACAO`,
    - **Quando** o `CHEFE_SEC_PED` tenta emitir o Certificado,
    - **Então** o sistema rejeita com `HTTP 422 — Pendência Documental` (`US-PIN-05`).
  - **Cenário 5 (Exceção 🟡 — Prazo de Registo na Plataforma Nacional):**
    - **Dado** que o ano letivo terminou há 25 dias e há certificados emitidos sem registo na Plataforma Nacional de Certificação,
    - **Quando** o `CHEFE_SEC_PED` abre a lista de certificados,
    - **Então** os por registar aparecem destacados: o registo tem de ser feito até 30 dias depois do fim do ano letivo (DP n.º 227/25, art. 13.º; integração a definir — `Q-020`).
- **Pós-condições e Efeitos Colaterais:** Processo da 13ª classe em `Certificado Emitido` (e `Diploma Pedido`); registo imutável em `documentos_oficiais_emitidos`.

---

### `US-DOC-03`: Consultar Autenticidade Pública de Documento Oficial via Leitura de QR Code / Hash Criptográfico
- **História:** *Como* **Entidade Externa (Inspector do MED, Universidade ou Empresa Empregadora)**, *quero* **ler o QR Code impresso em qualquer Declaração, Boletim, documento fiscal ou Certificado emitido pelo IPCAG N.º 12008 / BGO**, *para* **verificar instantaneamente se o documento e as notas apresentadas em papel são autênticos ou falsificados (`RN-10`)**.
- **Rastreabilidade:** `RN-10` | `Fluxo 08` | DESC-RESP R19 | `COR-LEG-19`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Documento emitido pelo SGE contendo `codigo_verificacao_hash` (ou emitido com QR Code da Plataforma Nacional de Certificação). Documentos físicos antigos emitidos antes do SGE sem código hash não são verificáveis no portal público (`DEC-025`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Documento Autêntico Confirmado):**
    - **Dado** um Certificado genuíno emitido pelo sistema,
    - **Quando** o validador lê o QR Code ou digita o código de verificação no portal público,
    - **Então** o sistema exibe os dados oficiais inalteráveis (`Estado: VÁLIDO`, Nome abreviado/completo conforme política APD, `N.º de Processo`, `Curso Técnico`, `Tipo de Documento`, `Média Final / MFC`, referência de arquivo e `Data de Emissão`), sem expor dados internos sensíveis. Os Certificados usam o QR da Plataforma Nacional de Certificação quando existir a integração 🟡 (`Q-020`); o QR próprio fica para os documentos sem QR nacional.
  - **Cenário 2 (Alerta — Código Inexistente ou Documento Anulado):**
    - **Dado** um QR Code forjado ou pertencente a um documento fiscal anulado por Nota de Crédito ou a um cartão de estudante anulado,
    - **Quando** o código é consultado,
    - **Então** o portal exibe destaque vermelho: **`DOCUMENTO INVÁLIDO, ANULADO OU NÃO RECONHECIDO PELO IPCAG N.º 12008 / BGO`**.
- **Pós-condições e Efeitos Colaterais:** Registo de consulta pública gravado no log de acessos de verificação.

---

### `US-DOC-04`: Gerir o Cadastro e a Assiduidade de Docentes e Funcionários e Exportar o Mapa de Efetividade
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)** e **Coordenador de Turno (`COORD_TURNO`)**, *queremos* **gerir o cadastro (com o N.º de Agente) e o registo da assiduidade dos professores, por tempo letivo, e dos funcionários administrativos**, *para* **exportar o mapa mensal de efetividade e faltas usado nos descontos (o processamento salarial fica fora do SGE — `DEC-008`)**.
- **Rastreabilidade:** `RN-12.14`, `RN-12.16` | `US-HOR-07`, `US-HOR-10` | Contexto `Secretaria Geral & RH` | DESC-L1 A15; DESC-RESP R24.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1` (cadastro) / `E2` (assiduidade e mapa de efetividade)`.
- **Pré-condições:** Utilizador autenticado como `CHEFE_SEC_GER`, `COORD_TURNO` ou `SUB_ADM`; horário publicado (`US-HOR-05`) para as faltas por tempo letivo.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Faltas Docentes por Tempo e Mapa Mensal de Efetividade):**
    - **Dado** o quadro de docentes e funcionários ativos nos turnos da Manhã e da Tarde, e as aulas registadas como `Não Lecionada` por falta do professor (`US-HOR-07`),
    - **Quando** o `COORD_TURNO` / `CHEFE_SEC_GER` regista as presenças, atrasos e faltas e o `SUB_ADM` valida o mapa mensal,
    - **Então** o sistema gera o Mapa Mensal de Efetividade Docente e Não-Docente (faltas dos professores contadas por tempo letivo) e exporta-o em Excel/CSV para quem processa os salários.
  - **Cenário 2 (Bloqueio RBAC — Professor Tenta Ver a Assiduidade dos Colegas):**
    - **Dado** um utilizador só com o papel `PROF`,
    - **Quando** tenta abrir o mapa de assiduidade do pessoal,
    - **Então** a API rejeita com `HTTP 403`; o professor vê só a sua própria assiduidade.
- **Pós-condições e Efeitos Colaterais:** Registos gravados em `assiduidade_funcionarios`. A avaliação de desempenho anual do pessoal não está incluída (`Q-036`).

---

### `US-DOC-05`: Exportar os Mapas Estatísticos para o Gabinete Provincial (GEPE/MED) e Auditar a Trilha Imutável (`audit_logs` — APD)
- **História:** *Como* **Director Geral (`DIR_GERAL`)** ou **Subdirector Pedagógico (`SUB_PED`)**, *quero* **exportar os mapas estatísticos (por Curso, Classe, Turma, Período, Género M/F, Faixa Etária e Aproveitamento) no modelo pedido pelo Gabinete Provincial e inspecionar a trilha imutável de auditoria (`audit_logs`)**, *para* **prestar contas ao Gabinete Provincial (início do ano, fim de cada trimestre e fim do ano, em papel assinado e em Excel) e auditar qualquer operação sensível (`RN-10`)**.
- **Rastreabilidade:** `RN-10`, `RN-17.4`, `RN-17.14`, `RN-16.18` | `Fluxo 04` e `Fluxo 08` | `US-PNL-12` | DESC-RESP §2 | `COR-LEG-25`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4` (mapas estatísticos) / `E1` (consulta de `audit_logs`)`.
- **Pré-condições:** Utilizador autenticado na Direção Executiva (`DIR_GERAL`, `SUB_PED`, `SUB_ADM`) ou `CHEFE_SEC_PED` (para os mapas); modelo do mapa 🟡 tirado do último mapa enviado e das instruções da Direção Provincial — não foi encontrado normativo publicado do GEPE (`COR-LEG-25`, `Q-LEG-15`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Geração dos Mapas Estatísticos):**
    - **Dado** um Ano Letivo e Trimestre (ou Final de Ano) com as Pautas Gerais homologadas,
    - **Quando** o `SUB_PED` ou o `CHEFE_SEC_PED` exporta o **Mapa Estatístico** (`DOF-12`),
    - **Então** o sistema consolida, com o **mesmo cálculo das estatísticas impressas na Pauta Geral** (`US-PNL-12`), os totais por `Curso Técnico`, `Classe (10ª–13ª)`, `Turma`, `Período (Manhã/Tarde)`, `Género`, `Faixas Etárias`, `Matriculados Inicialmente`, `Aprovados/Transitados`, `Transitados com Deficiência`, `Retidos por Notas`, `Retidos por Faltas`, `Transferidos (Entrada/Saída)` e `Desistentes/Anulados`, em PDF e Excel/CSV.
  - **Cenário 2 (Exceção — Pauta Geral por Homologar):**
    - **Dado** que uma das turmas ainda não tem a Pauta Geral homologada,
    - **Quando** o mapa é exportado,
    - **Então** o mapa sai marcado **PROVISÓRIO** e indica a turma em falta (`RN-17.4`).
  - **Cenário 3 (Sucesso — Consulta e Imutabilidade de `audit_logs`):**
    - **Dado** que o `DIR_GERAL` filtra a Auditoria por `Reabertura de Pauta`, `Nota de Crédito`, `Alerta de Fraude de Borderô` ou pela categoria `SEGURANCA_CONTAS`,
    - **Quando** visualiza os detalhes de um evento,
    - **Então** o sistema exibe o autor, o papel RBAC e a atribuição de cargo, o IP, o timestamp UTC, a justificação/despacho e o diff `valor_antigo_jsonb` vs. `valor_novo_jsonb`; qualquer `DELETE` ou `UPDATE` sobre `audit_logs` é bloqueado por *trigger* do PostgreSQL.
- **Pós-condições e Efeitos Colaterais:** Mapas estatísticos gerados com hash de integridade; conformidade com o Gabinete Provincial e com a Lei n.º 22/11 (APD).

---

## ÉPICO 08 (`EP-PIN`): Processo Individual do Aluno, Documentos, Encarregado e Cartão de Estudante

> [!abstract] Origem
> Histórias da [[C03 - Processo Individual do Aluno|CAP-C03]] §6, com os identificadores mantidos. As regras provisórias da nota (C03) passam à família `RN-11` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-13` (Cartão de Estudante) e `DOF-14` (Aviso de Pendências Documentais) (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Números dos exemplos
> Os campos dos boletins e o formato da numeração são **reais** (DESC-L1 A12, A13). Os restantes valores são ilustrativos e coerentes com DOC-01 a DOC-05 (`PROC-2026-00412`, turma `CG10A-T`, números de boletim). A lista de documentos, os prazos e o valor do emolumento do cartão vêm da Fase B.

---

### `US-PIN-01`: Parametrizar o Catálogo de Documentos do Processo Individual
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **definir que documentos são exigidos a cada tipo de ingresso e classe, com prazo, validade e efeito da falta**, *para* **que o sistema gere sozinho a lista de cada aluno sem depender da memória do balcão**.
- **Rastreabilidade:** `RN-11.2` | `MOD-PIN-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Ano Letivo em `Planeado` ou `Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Requisito por tipo de ingresso):**
    - **Dado** que o `CHEFE_SEC_PED` define, para `TRANSFERENCIA_ENTRADA`, a Guia de Transferência Oficial como obrigatória, com digitalização, efeito `BLOQUEIA_CERTIFICACAO` e prazo de entrega de `0` dias (no ato), e a `SUB_PED` homologa,
    - **Quando** se cria uma matrícula por transferência de entrada,
    - **Então** o sistema gera a linha *"Guia de Transferência Oficial — Em Falta"* no processo do aluno.
  - **Cenário 2 (Sucesso — Alteração sem efeito retroativo):**
    - **Dado** que já existem 300 matrículas iniciais da 10ª com o requisito "Atestado Médico",
    - **Quando** o catálogo deixa de exigir o atestado a meio do ano,
    - **Então** as 300 exigências já geradas mantêm-se e só as matrículas novas deixam de o exigir.
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um `OP_PED`,
    - **Quando** tenta alterar o catálogo,
    - **Então** a API rejeita com `HTTP 403`.
- **Pós-condições e Efeitos Colaterais:** `tipos_documento_processo` e `requisitos_documentais` homologados; evento `CATALOGO_DOCUMENTOS_HOMOLOGADO`.

---

### `US-PIN-02`: Registar a Entrega, a Conferência do Original e a Digitalização dos Documentos
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **marcar no balcão os documentos entregues, confirmar que vi o original e anexar a digitalização**, *para* **que o processo digital corresponda à pasta física e fique pesquisável**.
- **Rastreabilidade:** `RF-C03-15` | `RN-11.3`, `RN-11.4`, `RN-11.5`, `RN-11.13` | `US-MAT-01`, `MOD-PIN-02` | `documentos_processo_aluno`, `alunos` | 🟡 DoR-E1 · `Q-C03-14`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** matrícula criada; documentos gerados em `Em Falta`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Entrega com digitalização):**
    - **Dado** que o aluno `PROC-2026-00412` (10ª, `CG10A-T`) entrega o BI e o certificado da 9ª Classe,
    - **Quando** o `OP_PED` marca *"original conferido"*, digitaliza os dois em PDF de `1,2 MB` e grava,
    - **Então** os dois documentos passam a `Entregue`, cada ficheiro fica com o seu resumo SHA-256, o utilizador e a data, e o processo mostra *"2 de 4 documentos entregues"*.
  - **Cenário 2 (Bloqueio — Ficheiro não aceite):**
    - **Dado** um ficheiro `.docx` ou acima do tamanho máximo parametrizado,
    - **Quando** o `OP_PED` o tenta anexar,
    - **Então** o sistema rejeita com `HTTP 422`: *"Formato ou tamanho não aceite (PDF, JPEG ou PNG até ao limite definido)"*.
  - **Cenário 3 (Sucesso — Matrícula ativa com pendência):**
    - **Dado** que o atestado médico e as fotografias ficaram por entregar,
    - **Quando** a Tesouraria confirma o pagamento inicial,
    - **Então** a matrícula passa a `Ativa` normalmente (`RN-11.7.1`) e o processo mostra *"2 pendências — prazo de entrega: 30/09/2026"* (prazo de exemplo).
  - **Cenário 4 (Sucesso — Documentos da candidatura):**
    - **Dado** que o candidato entregou o certificado da 9ª Classe na inscrição ao Teste de Admissão,
    - **Quando** é convertido em aluno (Fluxo 02, Cenário A),
    - **Então** esse documento entra no processo já como `Entregue`, com a mesma digitalização.
  - **Cenário 5 (Sucesso — Devolução de Originais e Arquivo Histórico na Saída do Aluno — `RF-C03-15`, `RN-11.13`):**
    - **Dado** um aluno que concluiu o curso (`Concluído`) ou pediu transferência externa de saída (`Transferido`),
    - **Quando** o `OP_PED` ou `CHEFE_SEC_PED` procede à devolução física dos documentos originais depositados na matrícula (ex.: certificado da 9ª classe) ao encarregado ou aluno maior de idade,
    - **Então** o sistema regista em `documentos_processo_aluno` a data, hora e identidade do levantador (`devolvido_em`, `devolvido_a`), emite a respetiva guia/protocolo de entrega física e transfere o processo digital para `Arquivo Histórico`, preservando os ficheiros digitalizados e metadados de forma permanente.
- **Pós-condições e Efeitos Colaterais:** `documentos_processo_aluno`, `ficheiros_digitalizados` e estado do aluno em `alunos` gravados/atualizados.

---

### `US-PIN-03`: Validar, Rejeitar ou Dispensar Documentos do Processo
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)** e **Subdirector Pedagógico (`SUB_PED`)**, *queremos* **validar ou rejeitar os documentos entregues e, em casos excecionais, dispensar um documento obrigatório com despacho**, *para* **garantir que só documentos conformes sustentam a certificação**.
- **Rastreabilidade:** `RN-11.3` | `MOD-PIN-02`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** documento `Entregue` (validação/rejeição) ou `Em Falta`/`Rejeitado` (dispensa).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Rejeição por divergência):**
    - **Dado** que o BI digitalizado de `PROC-2026-00412` tem uma data de nascimento diferente da registada,
    - **Quando** o `CHEFE_SEC_PED` rejeita com o motivo `DADOS_DIVERGENTES`,
    - **Então** o documento passa a `Rejeitado`, volta a contar como pendência e o sistema sugere abrir um pedido de alteração de dados (`US-PIN-06`).
  - **Cenário 2 (Sucesso — Dispensa com despacho):**
    - **Dado** que o certificado da 9ª Classe de um aluno se perdeu e a escola de origem fechou,
    - **Quando** o `CHEFE_SEC_PED` propõe a dispensa e a `SUB_PED` a homologa com o despacho `DESP-PED-031/2026`,
    - **Então** o documento passa a `Dispensado` e grava-se `DOCUMENTO_PROCESSO_DISPENSADO` em `audit_logs`.
  - **Cenário 3 (Bloqueio — Dispensa por quem não pode):**
    - **Dado** um `CHEFE_SEC_PED`,
    - **Quando** tenta dispensar diretamente, sem homologação da `SUB_PED`,
    - **Então** o sistema guarda apenas a proposta; o estado não muda.
- **Pós-condições e Efeitos Colaterais:** estados atualizados; eventos em `audit_logs`.

---

### `US-PIN-04`: Consultar o Processo Individual e os Alertas de Documentos em Falta
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)** ou **Director de Turma (`DIR_TURMA`)**, *quero* **ver num só ecrã o processo do aluno ou a lista de pendências da turma**, *para* **pedir às famílias exatamente o que falta, antes de os prazos expirarem**.
- **Rastreabilidade:** `RN-11.1`, `RN-11.6`, `RN-11.12` | `MOD-PIN-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** aluno com processo.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Vista do processo):**
    - **Dado** o aluno `PROC-2026-00412`,
    - **Quando** o `OP_PED` abre o processo,
    - **Então** vê a identificação e a fotografia, o encarregado atual, a matrícula `2026/2027` (`CG10A-T`, `N.º de Ordem 17`, Boletim de Matrícula `N.º 0137/2026-2027`), o semáforo financeiro (sem valores), os documentos com estado, as cadeiras em atraso, os documentos emitidos e uma faixa *"Pendências: Atestado Médico, Fotografias — prazo 30/09/2026"*.
  - **Cenário 2 (Sucesso — Relatório da turma para o Director de Turma):**
    - **Dado** que `CG10A-T` tem 6 alunos com pendências,
    - **Quando** o `DIR_TURMA` abre o relatório da sua turma,
    - **Então** vê os 6 alunos, o nome de cada documento em falta e o prazo, **sem** acesso aos ficheiros.
  - **Cenário 3 (Bloqueio — Ficheiro sensível):**
    - **Dado** o `DIR_TURMA` de `CG10A-T`,
    - **Quando** tenta abrir a digitalização do BI de um aluno,
    - **Então** a API rejeita com `HTTP 403` e regista a tentativa.
  - **Cenário 4 (Sucesso — Caducidade):**
    - **Dado** que o BI de um aluno, validado, caduca a `15/03/2027`,
    - **Quando** se atinge a antecedência de aviso parametrizada,
    - **Então** o processo mostra *"BI caduca a 15/03/2027"*; nessa data o documento passa a `Caducado`.
- **Pós-condições e Efeitos Colaterais:** nenhuma alteração; acessos a ficheiros sensíveis em `audit_logs`.

---

### `US-PIN-05`: Impedir a Certificação com Pendência Documental Bloqueante
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **que o sistema me impeça de emitir o Certificado ou o Diploma a um aluno com documentos essenciais em falta**, *para* **não certificar um percurso escolar sem prova da habilitação de acesso e da identidade**.
- **Rastreabilidade:** `RN-11.7` | `US-DOC-02`, Fluxo 08, `MOD-PED-DOC`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4` (a emissão do `DOF-10` entra na E4; o catálogo com o efeito `BLOQUEIA_CERTIFICACAO` já existe desde a `E1`.
- **Pré-condições:** aluno apto para o `DOF-10` em termos académicos e financeiros.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Bloqueio — Certificado da 9ª em falta):**
    - **Dado** que o aluno `PROC-2023-00031` concluiu o curso, tem o semáforo financeiro verde e o emolumento pago, mas o certificado da 9ª Classe está `Em Falta` com efeito `BLOQUEIA_CERTIFICACAO`,
    - **Quando** o `CHEFE_SEC_PED` tenta emitir o `DOF-10`,
    - **Então** o sistema rejeita com `HTTP 422 — Pendência Documental: Certificado da 9ª Classe` e não atribui Livro/Folha/Termo.
  - **Cenário 2 (Sucesso — Pendência só de alerta):**
    - **Dado** que só as fotografias estão em falta (efeito `ALERTA`),
    - **Quando** o `CHEFE_SEC_PED` emite o `DOF-10`,
    - **Então** a emissão prossegue e o processo mantém o alerta.
- **Pós-condições e Efeitos Colaterais:** nenhuma emissão no Cenário 1; tentativa registada.

---

### `US-PIN-06`: Atualizar os Dados Pessoais do Aluno com Comprovativo e Auditoria
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)** com aprovação do **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **corrigir os dados pessoais do aluno com o comprovativo adequado**, *para* **que os documentos oficiais saiam com dados corretos e cada alteração fique provada (Lei n.º 22/11)**.
- **Rastreabilidade:** `RN-11.8` | `MOD-PIN-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** aluno registado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Contacto):**
    - **Dado** que o encarregado informa um novo telefone de emergência,
    - **Quando** o `OP_PED` grava,
    - **Então** o contacto é atualizado de imediato com registo em `audit_logs`.
  - **Cenário 2 (Sucesso — Passagem da cédula ao BI):**
    - **Dado** que o aluno tinha cédula pessoal e apresenta agora BI,
    - **Quando** o `OP_PED` cria o pedido com a digitalização do BI e o `CHEFE_SEC_PED` aprova,
    - **Então** o número do BI passa a ser o documento de identificação atual, o número da cédula fica no histórico e grava-se `ALTERACAO_DADOS_IDENTIFICACAO` com valor antigo e novo.
  - **Cenário 3 (Bloqueio — Alteração do nome sem comprovativo):**
    - **Dado** um pedido de correção do nome completo sem documento anexado,
    - **Quando** o `CHEFE_SEC_PED` o tenta aprovar,
    - **Então** o sistema rejeita com `HTTP 422`: *"Alteração de identificação civil exige comprovativo"*.
  - **Cenário 4 (Bloqueio — BI de outro aluno):**
    - **Dado** que o número de BI indicado já pertence a `PROC-2025-00215`,
    - **Quando** se tenta aprovar a alteração,
    - **Então** o sistema bloqueia com `HTTP 409` e cria um alerta de possível registo duplicado para a `SUB_PED`.
- **Pós-condições e Efeitos Colaterais:** `pedidos_alteracao_dados` decidido; `alunos` atualizado; documentos já emitidos inalterados.

---

### `US-PIN-07`: Mudar ou Atualizar o Encarregado de Educação
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **registar um novo encarregado de educação para um aluno, guardando o histórico**, *para* **saber em cada momento quem responde pelo aluno, sem estragar o histórico financeiro nem os descontos de irmãos**.
- **Rastreabilidade:** `RN-11.9`, `RN-07`, `RN-09` | `MOD-PIN-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** aluno com encarregado atual.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Novo encarregado com efeito no desconto de irmãos):**
    - **Dado** que `PROC-2026-00412` tinha como encarregado a pessoa X, com outro educando ativo e `DESCONTO_IRMAOS`, e a partir de `01/02/2027` passa a ter como encarregado a pessoa Y, sem outros educandos,
    - **Quando** o `CHEFE_SEC_PED` regista o novo vínculo com comprovativo,
    - **Então** o vínculo com X termina a `31/01/2027`, o de Y começa a `01/02/2027`, o desconto de irmãos deixa de se aplicar às prestações de *Fevereiro* a *Junho* (`A Vencer`), os recibos anteriores ficam inalterados e grava-se `MUDANCA_ENCARREGADO`.
  - **Cenário 2 (Sucesso — Encarregado já registado):**
    - **Dado** que o BI de Y já existe em `encarregados_educacao` (é encarregado de outro aluno),
    - **Quando** o `CHEFE_SEC_PED` pesquisa pelo BI,
    - **Então** o sistema reutiliza o registo existente (sem duplicar) e passa a sugerir o desconto de irmãos, se aplicável.
  - **Cenário 3 (Aviso — Alteração de contacto partilhado):**
    - **Dado** que o encarregado X tem 2 educandos,
    - **Quando** o `OP_PED` altera o telefone de X,
    - **Então** o sistema mostra *"Esta alteração aplica-se a 2 alunos: PROC-…, PROC-…"* antes de gravar.
  - **Cenário 4 (Bloqueio — Mudança sem comprovativo ou aluno sem encarregado):**
    - **Dado** um pedido de mudança de encarregado sem comprovativo anexado (documento a definir — `Q-C03-05`), **ou** um pedido que termina o vínculo atual sem indicar novo encarregado para um aluno que fez 18 anos,
    - **Quando** o `CHEFE_SEC_PED` tenta gravar,
    - **Então** o sistema rejeita com `HTTP 422` (*"Mudança de encarregado exige comprovativo"* / *"O aluno tem de ter um encarregado atual"* — `RN-11.9.2`, `RN-11.9.5`, `Q-C03-10`) e o vínculo atual mantém-se.
- **Pós-condições e Efeitos Colaterais:** `vinculos_encarregado_aluno` e `alunos.encarregado_educacao_id` atualizados.

---

### `US-PIN-08`: Emitir, Anular e Reemitir o Cartão de Estudante
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **emitir o cartão de estudante dos alunos com matrícula ativa, com fotografia e QR Code, e substituí-lo em caso de perda**, *para* **identificar o aluno dentro e fora da escola sem cartões falsificados ou de alunos que já saíram**.
- **Rastreabilidade:** `RN-11.10`, `RN-11.11`, `RN-08`, `RN-10` | Fluxo 02 (F5), `MOD-PIN-05`, `DOF-13`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E1`.
- **Pré-condições:** matrícula `Ativa`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — 1ª via):**
    - **Dado** que `PROC-2026-00412` tem a matrícula `Ativa` em `CG10A-T`, a fotografia `Validado` e o emolumento do cartão pago,
    - **Quando** o `OP_PED` emite o cartão,
    - **Então** o sistema gera o cartão `N.º 2026/00412` (exemplo de numeração), regista-o em `documentos_oficiais_emitidos` com o código de verificação, marca a linha de `itens_recibo` como `Consumido` e o cartão passa a `Emitido`.
  - **Cenário 2 (Bloqueio — Sem fotografia ou sem emolumento):**
    - **Dado** que a fotografia está `Em Falta` ou o emolumento não está pago (e não há isenção),
    - **Quando** o `OP_PED` tenta emitir,
    - **Então** o sistema rejeita com `HTTP 422` (*"Fotografia por validar"*) ou `HTTP 403` (*"Pendência Financeira — emolumento do cartão"*).
  - **Cenário 3 (Sucesso — 2ª via por perda):**
    - **Dado** que o aluno declara a perda do cartão,
    - **Quando** o `CHEFE_SEC_PED` anula o cartão com o motivo `PERDA` e o `OP_PED` emite a 2ª via (com o emolumento próprio, se existir),
    - **Então** o cartão antigo passa a `Anulado` e o seu QR Code mostra *"inválido"*; o novo fica `Emitido` com a indicação *"2ª via"*.
  - **Cenário 4 (Sucesso — Anulação por transferência):**
    - **Dado** que a matrícula de `PROC-2026-00412` passa a `Transferida (Externa)`,
    - **Quando** a transferência é homologada,
    - **Então** o cartão passa a `Anulado` automaticamente com o motivo `TRANSFERENCIA`.
- **Pós-condições e Efeitos Colaterais:** `cartoes_estudante` atualizado; eventos `CARTAO_EMITIDO` / `CARTAO_ANULADO` em `audit_logs`.

---

### `US-PIN-09`: Registar o Boletim de Matrícula ou de Confirmação com os Campos Reais e Numeração Anual
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **preencher no SGE o boletim de matrícula ou de confirmação com os mesmos campos do modelo da escola, recebendo o número anual e o comprovativo destacável**, *para* **substituir o boletim em papel sem perder nenhum campo nem a numeração que a escola já usa**.
- **Rastreabilidade:** `RN-11.8`, `RN-11.14` | DESC-L1 A12, A13 | `US-MAT-01`, `US-MAT-02`, `DOF-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Ano Letivo `2026/2027` com as séries de boletins configuradas.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Matrícula inicial):**
    - **Dado** que o último Boletim de Matrícula de `2026/2027` tem o `N.º 0136` *(ilustrativo)*,
    - **Quando** o `OP_PED` cria a matrícula de um candidato admitido à 10ª de Contabilidade e Gestão, período da Tarde, preenchendo os campos reais (identificação, n.º e data de emissão do BI, dois telefones do encarregado, residência e município, escola, classe, ano e resultado anteriores),
    - **Então** o sistema atribui o `Boletim de Matrícula N.º 0137/2026-2027`, imprime o boletim e o comprovativo destacável com o mesmo número e a menção "para efeito de reclamação", e o comprovativo não mostra o campo de saúde.
  - **Cenário 2 (Sucesso — Confirmação pré-preenchida):**
    - **Dado** que `PROC-2025-00108` frequentou a 10ª em `CG10A-T`, Sala 04, em `2025/2026` e tem 2 cadeiras em atraso,
    - **Quando** o `OP_PED` abre a confirmação para `2026/2027`,
    - **Então** a classe, turma, sala e curso anteriores e as 2 cadeiras em atraso aparecem preenchidos e só de leitura, e o boletim recebe o número seguinte da série **de confirmação** (se as séries forem separadas — `Q-C03-18`).
  - **Cenário 3 (Sucesso — Campo de saúde facultativo):**
    - **Dado** que o encarregado não quer declarar problemas de saúde,
    - **Quando** o `OP_PED` deixa o campo vazio,
    - **Então** a matrícula prossegue normalmente; se o campo for preenchido, só é gravado com o consentimento CON-07 e no compartimento de saúde (RF-C19-29).
  - **Cenário 4 (Bloqueio — Alterar ou reutilizar o número):**
    - **Dado** um boletim já numerado,
    - **Quando** um utilizador tenta alterar o número ou reutilizar o número de uma matrícula anulada,
    - **Então** o sistema rejeita com `HTTP 409` e regista `TENTATIVA_ALTERACAO_NUMERO_BOLETIM` em `audit_logs`.
- **Pós-condições e Efeitos Colaterais:** `matriculas_anuais` com o número do boletim; `series_numeracao_documental` atualizada; `DOF-03` com 2 vias.

---

## ÉPICO 09 (`EP-HOR`): Horários, Distribuição de Serviço Docente e Livro de Sumários

> [!abstract] Origem
> Histórias da [[C04 - Horarios e Distribuicao de Servico Docente|CAP-C04]] §6, com os identificadores mantidos. As regras provisórias da nota (C04) passam à família `RN-12` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-15` e `DOF-16` (horários e mapa de cumprimento — entrada na numeração oficial por decidir, `Q-C04-16`) (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Números dos exemplos
> As **cargas semanais das disciplinas são reais**: vêm do plano curricular de **Técnico de Contabilidade e Gestão** (DESC-L1 A5) — 10ª: Língua Portuguesa 3, Educação Física 2, Matemática 4, Informática de Gestão 2; 11ª: Contabilidade Financeira 4, Noções de Direito 3; 12ª: Contabilidade Analítica 6; total de 32 h na 10ª–12ª. Os códigos de turma (`CG10A-T`, `CG11A-M`…) seguem o padrão do DOC-04 (`MOD-GOV-03`); professores, datas, grelhas e fatores de faltas são **ilustrativos**. A grelha de tempos e o horário real substituem-nos na Fase B (plano §5.2; ainda em falta segundo o DESC-L1 §6).

---

### `US-HOR-01`: Parametrizar a Grelha de Tempos Letivos por Turno e o Calendário de Dias Não Letivos
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **definir os tempos letivos e os intervalos de cada turno, os dias letivos da semana e os dias sem aulas**, *para* **que horários, aulas previstas e faltas por tempo letivo tenham uma base temporal única e verificável**.
- **Rastreabilidade:** `RN-12.1`, `RN-12.2`, `RN-12.12`, `RN-03` | [[C04 - Horarios e Distribuicao de Servico Docente|CAP-C04]] §5.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Ano Letivo `2026/2027` homologado; utilizador `SUB_PED`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Grelha dentro da janela do turno):**
    - **Dado** que o `SUB_PED` define para o Turno da Manhã 7 tempos de 40 min e intervalos que somam 25 min, com o 1.º tempo às `07h30` e o fim do 7.º tempo às `12h35` *(valores ilustrativos — `Q-C04-01`)*,
    - **Quando** grava a grelha,
    - **Então** o sistema aceita-a (280 min de aulas + 25 min de intervalos = 305 min) e mostra a capacidade semanal: 5 dias × 7 tempos = `35` lugares, suficiente para as `32` horas curriculares da 10ª Classe de Contabilidade e Gestão.
  - **Cenário 2 (Bloqueio — Tempo fora da janela):**
    - **Dado** uma grelha da Tarde cujo último tempo termina às `18h10`,
    - **Quando** o `SUB_PED` tenta gravá-la,
    - **Então** o sistema rejeita com `HTTP 422`: *"O 6.º tempo termina às 18h10, depois do fim do Turno da Tarde (18h05)"*.
  - **Cenário 3 (Bloqueio — Matriz real maior do que a grelha):**
    - **Dado** que a matriz real da `11ª Classe` de *Contabilidade e Gestão* soma `32` horas curriculares semanais (DESC-L1 A5) e a grelha da Manhã tem 6 tempos de 45 min (`30` lugares por semana),
    - **Quando** o `SUB_PED` homologa a grelha,
    - **Então** o sistema mostra o aviso *"A turma CG11A-M precisa de 32 tempos e o turno só tem 30"* e marca as turmas desse curso e classe como **impossíveis de publicar** até à correção.
  - **Cenário 4 (Sucesso — Feriado depois da publicação):**
    - **Dado** um horário publicado e um dia registado como feriado depois da geração das aulas,
    - **Quando** o `SUB_PED` grava o dia não letivo,
    - **Então** todas as aulas `PREVISTA` desse dia passam a `CANCELADA` e não contam como aulas por dar.
  - **Cenário 5 (Bloqueio — 7 tempos de 45 min não cabem no turno):**
    - **Dado** uma grelha da Manhã com 7 tempos de 45 min a começar às `07h30`,
    - **Quando** o `SUB_PED` tenta gravá-la,
    - **Então** o sistema rejeita com `HTTP 422`: *"7 tempos de 45 min (315 min) excedem a janela do Turno da Manhã (305 min)"* — a situação que os planos reais tornam provável (`RN-12.1.4`).
- **Pós-condições e Efeitos Colaterais:** registos em `tempos_letivos_turno` e `dias_nao_letivos`; evento `GRELHA_TEMPOS_HOMOLOGADA` em `audit_logs`.

---

### `US-HOR-02`: Registar a Carga de Referência, as Habilitações, as Acumulações e as Indisponibilidades do Professor
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **registar no cadastro de cada professor a carga letiva de referência, as disciplinas para que está habilitado, as acumulações externas e as indisponibilidades**, *para* **que a distribuição de serviço e o horário respeitem a situação real de cada professor**.
- **Rastreabilidade:** `RN-12.4` a `RN-12.7` | `MOD-GER-RH`, `US-DOC-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** professor ativo em `funcionarios_docentes`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Acumulação externa autorizada gera indisponibilidades):**
    - **Dado** que o Professor A declara lecionar noutra escola às terças e quintas no Turno da Tarde (tempos 1 a 4) e o cargo autorizador (`Q-C04-05`) aprova com o despacho `DESP-DG-021/2026`,
    - **Quando** a `CHEFE_SEC_GER` grava a acumulação,
    - **Então** o sistema cria 2 indisponibilidades (terça e quinta, Tarde, tempos 1–4) ligadas à acumulação e grava o despacho em `audit_logs`.
  - **Cenário 2 (Bloqueio — Acumulação sem autorização):**
    - **Dado** uma acumulação externa no estado `DECLARADA`, ainda sem despacho,
    - **Quando** a `SUB_PED` tenta usá-la como justificação de indisponibilidade,
    - **Então** o sistema mostra a indisponibilidade apenas como aviso, sem efeito bloqueante, até à autorização.
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um utilizador `PROF`,
    - **Quando** tenta alterar a carga de referência do seu próprio cadastro,
    - **Então** a API rejeita com `HTTP 403 Forbidden`; o professor pode apenas ler os seus dados.
- **Pós-condições e Efeitos Colaterais:** registos em `funcionarios_docentes` (atributos novos), `habilitacoes_docentes`, `acumulacoes_docentes` e `indisponibilidades_docentes`.

---

### `US-HOR-03`: Propor e Homologar a Distribuição de Serviço Docente com Controlo de Carga
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`)** e **Subdirector Pedagógico (`SUB_PED`)**, *queremos* **propor e homologar os titulares de cada disciplina de cada turma, vendo a carga letiva resultante de cada professor**, *para* **arrancar o ano com uma distribuição completa, equilibrada e dentro dos limites aplicáveis**.
- **Rastreabilidade:** `RN-12.3` a `RN-12.6`, `RN-04` | Fluxo 03, `US-PED-05`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** turmas e Mini-Pautas criadas (`US-GOV-03`); plano `Em Elaboração`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Carga calculada e homologação):**
    - **Dado** que o Professor B é proposto como titular de *Contabilidade Financeira* (`4` h na 11ª) em `CG11A-M` e `CG11B-M`, de *Contabilidade Analítica* (`6` h na 12ª) em `CG12A-T` e é `DIR_TURMA` de `CG11A-M`,
    - **Quando** o `SUB_PED` abre o plano,
    - **Então** o sistema mostra `Carga = 4 + 4 + 6 = 14 tempos/semana`, a acumulação interna "Director de Turma (CG11A-M)" e a redução aplicável (se parametrizada), e permite homologar.
  - **Cenário 2 (Bloqueio — Limite excedido sem despacho):**
    - **Dado** que existe um limite parametrizado e a carga proposta do Professor C o excede,
    - **Quando** o `SUB_PED` tenta homologar o plano,
    - **Então** o sistema bloqueia com `HTTP 422`: *"Professor C excede o limite de carga letiva; ajuste a distribuição ou registe despacho de exceção"*; com o despacho registado, a homologação avança e grava `EXCECAO_CARGA_LETIVA` em `audit_logs`.
  - **Cenário 3 (Sucesso com alerta — Disciplina sem professor):**
    - **Dado** que *Matemática* (`4` h) de `CG10A-T` não tem professor proposto,
    - **Quando** o `SUB_PED` a marca como "Sem Docente Atribuído" e homologa,
    - **Então** o plano fica `Homologado` com o alerta permanente *"1 disciplina sem docente"* no painel da `SUB_PED`.
  - **Cenário 4 (Segurança RBAC — Coordenador fora do seu curso):**
    - **Dado** um `COORD_CURSO` de *Contabilidade e Gestão*,
    - **Quando** tenta propor um titular para uma turma de *Gestão de Recursos Humanos*,
    - **Então** a API rejeita com `HTTP 403 Forbidden`.
- **Pós-condições e Efeitos Colaterais:** `planos_distribuicao_servico` `Homologado`; `alocacoes_docentes` com `estado_alocacao = VIGENTE`; emissão do `DOF-15`.

---

### `US-HOR-04`: Registar Manualmente o Horário Semanal da Turma com Deteção de Choques em Tempo Real
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** (ou quem ele designar — `Q-C04-03`), *quero* **colocar cada disciplina da turma nos dias e tempos letivos do turno, escolhendo o espaço, e ver os choques no momento**, *para* **produzir um horário sem conflitos de professor, de espaço ou de turma**.
- **Rastreabilidade:** `RN-12.7` a `RN-12.10` | `MOD-HOR-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** distribuição homologada; grelha do turno homologada; versão do horário em `Rascunho`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Aula sem choques):**
    - **Dado** que *Informática de Gestão* (`2` h na 10ª) de `CG10A-T` exige laboratório e o `Lab. Informática 01` está livre à segunda-feira, tempos 3–4 da Tarde,
    - **Quando** o utilizador coloca ali um bloco de 2 tempos,
    - **Então** o sistema grava a aula e mostra *"Informática de Gestão: 2 de 2 tempos colocados"*.
  - **Cenário 2 (Bloqueio — Choque de professor):**
    - **Dado** que o Professor B já leciona em `CG11B-M` à quarta-feira, tempo 2,
    - **Quando** o utilizador coloca *Contabilidade Financeira* de `CG11A-M` (titular: Professor B) à quarta-feira, tempo 2,
    - **Então** a aula fica marcada a vermelho com *"Choque de Professor: Professor B já está em CG11B-M (quarta, tempo 2)"* e a versão não pode ser submetida.
  - **Cenário 3 (Bloqueio — Choque de espaço):**
    - **Dado** que o `Lab. Informática 01` já está ocupado por `CG11A-T` à segunda-feira, tempo 3 da Tarde,
    - **Quando** o utilizador tenta colocar ali `CG10A-T`,
    - **Então** o sistema indica *"Choque de Espaço: Lab. Informática 01 ocupado por CG11A-T (segunda, tempo 3)"* e sugere os laboratórios livres.
  - **Cenário 4 (Bloqueio — Indisponibilidade do professor):**
    - **Dado** que o Professor A tem indisponibilidade à terça-feira, Tarde, tempos 1–4 (acumulação externa autorizada),
    - **Quando** o utilizador coloca uma aula do Professor A nesse período,
    - **Então** o sistema indica o choque com a indisponibilidade; só a `SUB_PED` pode gravar uma exceção, com justificação registada em `audit_logs`.
- **Pós-condições e Efeitos Colaterais:** linhas em `aulas_horario` da versão em `Rascunho`.

---

### `US-HOR-05`: Validar a Completude e Publicar o Horário, Gerando as Aulas Previstas
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **publicar o horário de cada turma só quando estiver completo e sem choques, com data de vigência**, *para* **que professores, Directores de Turma e Coordenadores de Turno trabalhem sobre um horário oficial e para que o sistema saiba que aulas estavam previstas**.
- **Rastreabilidade:** `RN-12.8`, `RN-12.11` | `MOD-HOR-03`, `DOF-16`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** versão `Submetido`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Publicação e geração):**
    - **Dado** que o horário de `CG10A-T` tem as `32` horas curriculares da matriz colocadas, 0 choques e vigência a partir de `14/09/2026`,
    - **Quando** o `SUB_PED` publica,
    - **Então** a versão passa a `Publicado`, o sistema gera as aulas `PREVISTA` desde `14/09/2026` até ao fim do I Trimestre (excluindo os dias não letivos) e grava `HORARIO_PUBLICADO` em `audit_logs`.
  - **Cenário 2 (Bloqueio — Horário incompleto):**
    - **Dado** que *Educação Física* (`2` h na 10ª) de `CG10A-T` tem `1` de `2` tempos colocados,
    - **Quando** o `SUB_PED` tenta publicar,
    - **Então** o sistema rejeita com `HTTP 422`: *"Horário incompleto: Educação Física (1 de 2 tempos)"*.
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um `COORD_TURNO`,
    - **Quando** tenta publicar um horário,
    - **Então** a API rejeita com `HTTP 403 Forbidden` (pode propor alterações de espaço, mas não publicar).
- **Pós-condições e Efeitos Colaterais:** `horarios_turma` `Publicado`; `aulas_registadas` em `PREVISTA`; `DOF-16` disponível para impressão.

---

### `US-HOR-06`: Registar o Sumário e as Faltas por Tempo Letivo a partir do Horário (Offline-First)
- **História:** *Como* **Professor (`PROF`)**, *quero* **abrir a aula do dia já preenchida a partir do horário, escrever o sumário uma vez e marcar as faltas tempo a tempo, mesmo sem rede**, *para* **cumprir a regra de faltas proporcional aos tempos letivos (`RN-03`) sem digitar datas, disciplinas ou número de tempos**.
- **Rastreabilidade:** `RN-12.13`, `RN-12.17`, `RN-03`, `RN-05`, `RN-10` | `US-PED-02`, `MOD-DOC-FAL`, `MOD-HOR-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** aula `PREVISTA` de que o utilizador é professor efetivo; trimestre `Aberto / Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Bloco de 2 tempos com faltas parciais):**
    - **Dado** que a aula de *Língua Portuguesa* (`3` h na 10ª) de `CG10A-T` de `15/10/2026` ocupa os tempos 3 e 4, o aluno `N.º 08` faltou aos 2 tempos e o aluno `N.º 12` chegou só para o tempo 4,
    - **Quando** o `PROF` escreve o sumário, marca `N.º 08` nos tempos 3–4 e `N.º 12` só no tempo 3, e grava,
    - **Então** a aula passa a `Lecionada`, o aluno `N.º 08` soma `2` faltas injustificadas e o aluno `N.º 12` soma `1`, e o motor do `RN-03` recalcula o saldo face ao limite da disciplina (ex.: `12` faltas para `3` tempos semanais com fator `4` — **fator a validar**; o efeito do atraso depende da `Q-C04-13`).
  - **Cenário 2 (Sucesso — Sem faltas, sumário guardado):**
    - **Dado** que nenhum aluno faltou,
    - **Quando** o `PROF` regista apenas o sumário,
    - **Então** a aula fica `Lecionada` com o sumário guardado (o que o modelo atual, que guarda o sumário dentro de cada falta, não permite — [[C04 - Horarios e Distribuicao de Servico Docente|CAP-C04]] §8.3).
  - **Cenário 3 (Sucesso — Offline):**
    - **Dado** que não há rede, e o horário da semana e a lista da turma estão no `IndexedDB`,
    - **Quando** o `PROF` regista o sumário e as faltas,
    - **Então** a operação entra na fila de sincronização com `Chave de Idempotência` e é aplicada quando a rede regressa, se o trimestre continuar aberto (DOC-05 §1.2).
  - **Cenário 4 (Bloqueio — Aula que não é do professor ou data sem aula):**
    - **Dado** que o `PROF` não é o professor efetivo da aula de *Matemática* de `CG10A-T` de hoje, ou tenta criar uma aula num dia em que a disciplina não tem tempo no horário,
    - **Quando** tenta registar sumário ou faltas,
    - **Então** a API rejeita com `HTTP 403` (aula de outro professor) ou `HTTP 422` (*"Não há aula prevista; peça uma reposição ao Coordenador de Turno"*).
  - **Cenário 5 (Bloqueio — Faltas em aula não lecionada):**
    - **Dado** uma aula `Não Lecionada`,
    - **Quando** alguém tenta registar faltas nessa aula,
    - **Então** o sistema rejeita com `HTTP 409 Conflict`.
- **Pós-condições e Efeitos Colaterais:** `aulas_registadas` em `Lecionada`; linhas em `sumarios_e_faltas_alunos` ligadas à aula e aos tempos; contadores do `RN-03` atualizados.

---

### `US-HOR-07`: Designar Substituição Pontual ou Registar Aula Não Lecionada
- **História:** *Como* **Coordenador de Turno (`COORD_TURNO`)**, *quero* **registar a ausência de um professor numa aula e designar um substituto livre, ou marcar a aula como não lecionada**, *para* **que os alunos não fiquem sem registo, que o substituto possa fazer a chamada e que a aula perdida fique identificada para reposição**.
- **Rastreabilidade:** `RN-12.14`, `RN-04` | `MOD-HOR-05`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** aula `PREVISTA` no turno do `COORD_TURNO`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Substituto livre):**
    - **Dado** que o titular de *Noções de Direito* (`3` h na 11ª) de `CG11B-M` faltou à aula de `20/10/2026` (tempo 5) e o Professor D não tem aula nesse tempo,
    - **Quando** o `COORD_TURNO` designa o Professor D,
    - **Então** a aula guarda o titular e o efetivo (Professor D), o Professor D vê-a nas aulas do dia e pode registar sumário e faltas, e grava-se `SUBSTITUICAO_PONTUAL` em `audit_logs`.
  - **Cenário 2 (Bloqueio — Substituto com choque):**
    - **Dado** que o Professor E tem aula em `CG12A-M` no mesmo tempo,
    - **Quando** o `COORD_TURNO` o tenta designar,
    - **Então** o sistema rejeita com `HTTP 409`: *"Choque de Professor: Professor E está em CG12A-M (tempo 5)"*.
  - **Cenário 3 (Bloqueio — Substituto pontual sem acesso às notas):**
    - **Dado** que o Professor D é substituto pontual em `CG11B-M`,
    - **Quando** tenta abrir a Mini-Pauta de *Noções de Direito* para lançar notas,
    - **Então** a API rejeita com `HTTP 403` (o acesso às notas depende de `alocacoes_docentes` — `RN-04`).
  - **Cenário 4 (Sucesso — Sem substituto):**
    - **Dado** que não há professor livre,
    - **Quando** o `COORD_TURNO` regista a aula como não lecionada com motivo `FALTA_PROFESSOR`,
    - **Então** a aula passa a `Não Lecionada`, fica elegível para reposição e aparece à `CHEFE_SEC_GER` no controlo de ponto, sem efeito automático.
- **Pós-condições e Efeitos Colaterais:** `aulas_registadas` atualizada; evento em `audit_logs`.

---

### `US-HOR-08`: Agendar e Registar uma Aula de Reposição
- **História:** *Como* **Professor (`PROF`)** com aprovação do **Coordenador de Turno (`COORD_TURNO`)**, *quero* **marcar uma aula de reposição para uma aula não lecionada, num tempo e espaço livres**, *para* **cumprir o programa da disciplina e manter a contagem de faltas correta**.
- **Rastreabilidade:** `RN-12.15`, `RN-03` | `MOD-HOR-05`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Pré-condições:** aula original `Não Lecionada` no trimestre aberto.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** a aula `Não Lecionada` de *Noções de Direito* de `CG11B-M` de `20/10/2026`, e a turma, o titular e a sala própria livres a `24/10/2026`, tempo 6,
    - **Quando** o `PROF` pede a reposição e o `COORD_TURNO` autoriza,
    - **Então** é criada uma aula `PREVISTA` do tipo `REPOSICAO` ligada à original; quando o sumário é registado, a original passa a `Reposta` e as faltas contam para o `RN-03`.
  - **Cenário 2 (Bloqueio — Choque na data da reposição):**
    - **Dado** que a turma `CG11B-M` já tem *Matemática* a `24/10/2026`, tempo 6,
    - **Quando** se tenta autorizar a reposição,
    - **Então** o sistema rejeita com `HTTP 409` (choque de turma).
  - **Cenário 3 (Bloqueio — Fora do trimestre):**
    - **Dado** que a Mini-Pauta de *Noções de Direito* de `CG11B-M` já está `Submetida ao Director de Turma`,
    - **Quando** se tenta marcar uma reposição de uma aula do I Trimestre,
    - **Então** o sistema rejeita com `HTTP 422`: *"Reposições só dentro do trimestre da aula original e antes da submissão da Mini-Pauta"*.
- **Pós-condições e Efeitos Colaterais:** `aulas_registadas` com o tipo `REPOSICAO` e a ligação `aula_reposta_id`.

---

### `US-HOR-09`: Alterar o Horário a Meio do Trimestre com Nova Versão e Vigência
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **publicar uma nova versão do horário de uma turma a partir de uma data futura**, *para* **responder a substituições, mudanças de espaço ou de distribuição sem apagar o que já foi lecionado e registado**.
- **Rastreabilidade:** `RN-12.11`, `RN-12.14.4` | `MOD-HOR-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** versão `Publicado` vigente.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Nova versão futura):**
    - **Dado** que a versão 1 do horário de `CG11A-M` está vigente desde `14/09/2026` e já há 40 aulas `Lecionada`,
    - **Quando** o `SUB_PED` publica a versão 2 com vigência a partir de `02/11/2026` e o motivo *"Troca de laboratório"*,
    - **Então** a versão 1 recebe `data_fim_vigencia = 01/11/2026` e passa a `Substituído`, as aulas `PREVISTA` desde `02/11/2026` são regeneradas, as 40 aulas lecionadas ficam intactas e os professores e o `DIR_TURMA` recebem aviso.
  - **Cenário 2 (Bloqueio — Vigência retroativa):**
    - **Dado** que hoje é `05/11/2026`,
    - **Quando** o `SUB_PED` tenta publicar uma versão com vigência a partir de `01/11/2026`, havendo aulas lecionadas entre `01/11` e `04/11`,
    - **Então** o sistema rejeita com `HTTP 422`: *"Não é possível alterar o horário de datas com aulas já lecionadas"*.
  - **Cenário 3 (Bloqueio — Substituição prolongada que gera choque):**
    - **Dado** que o `SUB_PED` substitui o Professor A pelo Professor B em *Contabilidade Financeira* de `CG11A-M` (`RN-04`) e o Professor B leciona `CG11B-M` à quarta-feira, tempo 2, tal como `CG11A-M`,
    - **Quando** confirma a substituição,
    - **Então** o sistema bloqueia-a com `HTTP 409` e propõe criar, na mesma operação, uma nova versão do horário que elimine o choque.
- **Pós-condições e Efeitos Colaterais:** nova versão `Publicado`; versão anterior `Substituído`; evento `HORARIO_ALTERADO` em `audit_logs`.

---

### `US-HOR-10`: Consultar e Imprimir Horários e o Mapa de Cumprimento de Aulas
- **História:** *Como* **Director de Turma (`DIR_TURMA`)**, **Professor (`PROF`)** ou **Coordenador de Turno (`COORD_TURNO`)**, *quero* **ver e imprimir o horário da turma, do professor ou do espaço e a taxa de cumprimento das aulas**, *para* **acompanhar o funcionamento letivo e detetar disciplinas com aulas por dar**.
- **Rastreabilidade:** `RN-12.16` | `MOD-HOR-06`, `DOF-16`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Pré-condições:** horário publicado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Taxa de cumprimento):**
    - **Dado** que *Matemática* (`4` h, em aulas de 1 tempo) de `CG10A-T` tinha `48` aulas previstas em 12 semanas do I Trimestre, `2` canceladas por feriado, `40` lecionadas e `3` repostas,
    - **Quando** o `DIR_TURMA` consulta o mapa,
    - **Então** o sistema mostra a taxa $(40 + 3) / (48 - 2) = 43 / 46 \approx 93{,}5\%$ e as `3` aulas ainda não lecionadas nem repostas.
  - **Cenário 2 (Segurança RBAC — Âmbito):**
    - **Dado** um `PROF`,
    - **Quando** consulta o horário de um colega,
    - **Então** vê apenas os horários das turmas onde leciona e o seu próprio; o mapa de cumprimento de outros professores devolve `HTTP 403`.
- **Pós-condições e Efeitos Colaterais:** nenhuma alteração de dados; exportação em PDF (A4 paisagem).

---

### `US-HOR-11`: Importar o Horário Elaborado numa Folha de Cálculo
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **importar o horário de um turno feito numa folha de cálculo, com a mesma validação que o registo à mão**, *para* **não ter de voltar a digitar as aulas de todas as turmas quando o horário já foi elaborado fora do sistema** (`DEC-004`).
- **Rastreabilidade:** `RN-12.18`, `RN-12.8`, `RN-12.9` | `DEC-004` | `MOD-HOR-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** distribuição homologada; grelha homologada; folha de cálculo no modelo fornecido pelo SGE.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Importação em rascunho):**
    - **Dado** um ficheiro com as aulas das 12 turmas do Turno da Tarde, uma linha por aula (turma, dia, tempo inicial, n.º de tempos, disciplina, espaço), em que cada turma soma as `32` horas curriculares da sua matriz,
    - **Quando** o `SUB_PED` importa o ficheiro,
    - **Então** o sistema cria 12 versões em `Rascunho`, guarda o ficheiro de origem e mostra o relatório com as linhas aceites, `0` rejeitadas e `0` choques, sem publicar nenhuma versão.
  - **Cenário 2 (Rejeição parcial — Linhas inválidas e choques):**
    - **Dado** que a linha 57 indica a disciplina *Física* na turma `CG10A-T` (inexistente na matriz de Contabilidade e Gestão) e as linhas 80 e 143 põem o mesmo professor em duas turmas à terça-feira, tempo 2,
    - **Quando** o `SUB_PED` importa,
    - **Então** o relatório mostra a linha 57 rejeitada (*"A disciplina não pertence à matriz da turma"*) e o choque de professor entre as linhas 80 e 143; os rascunhos ficam com as aulas válidas e não podem ser submetidos enquanto houver choques ou disciplinas incompletas.
  - **Cenário 3 (Sucesso — Importar sobre um horário publicado):**
    - **Dado** que `CG10A-T` já tem uma versão `Publicado`,
    - **Quando** o `SUB_PED` importa um ficheiro com aulas dessa turma,
    - **Então** o sistema cria uma **nova versão em `Rascunho`** e pede a data de início de vigência e o motivo (`RN-12.11`); a versão publicada não é tocada.
- **Pós-condições e Efeitos Colaterais:** versões em `Rascunho` com origem `IMPORTADO` e ficheiro de origem; evento `HORARIO_IMPORTADO` em `audit_logs`.

> [!note] Geração automática retirada
> A "proposta automática de horário" da versão `0.1` da [[C04 - Horarios e Distribuicao de Servico Docente|CAP-C04]] foi retirada: está **fora do âmbito** por `DEC-004` e `DEC-008` (`F-06` da VIS-06).

---

## ÉPICO 10 (`EP-COB`): Cobrança de Dívidas, Acordos de Pagamento, Relatórios Financeiros e Conciliação Bancária

> [!abstract] Origem
> Histórias da [[C10 - Cobranca, Relatorios Financeiros e Conciliacao|CAP-C10]] §6, com os identificadores mantidos. As regras provisórias da nota (C10) passam à família `RN-13` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-17` a `DOF-20` (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Sobre os números dos exemplos
> A propina de `15.000,00 Kz`, o vencimento ao dia `10` e o talão de `30.000,00 Kz` são os valores de exemplo já usados na especificação (`US-TES-01`, `US-TES-03`). **A multa de `1.500,00 Kz` é fictícia**, usada só para mostrar o cálculo: a regra real vem da tabela em vigor (`Q-C10-01`). Todos estes valores serão substituídos pelos reais recolhidos na Fase B (PLN-00 §5.2).

---

### `US-COB-01`: Consultar a dívida e a sua antiguidade
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **ver a dívida exigível e reescalonada agrupada por antiguidade, curso, classe e turno**, *para* **decidir onde concentrar a cobrança**.
- **Rastreabilidade:** `RN-13.1`, `RN-13.2`, `RN-13.10` | `RN-08`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Escalões por prestação):**
    - **Dado** um aluno com as propinas de Outubro (limite `10/10/2026`), Novembro (`10/11/2026`) e Dezembro (`10/12/2026`) por pagar, cada uma com `15.000,00 Kz` e multa fictícia de `1.500,00 Kz`,
    - **Quando** o `SUB_ADM` consulta a antiguidade com data de referência `15/12/2026`,
    - **Então** o sistema mostra Outubro no escalão `61–90` (66 dias), Novembro em `31–60` (35 dias), Dezembro em `1–30` (5 dias), dívida exigível de `49.500,00 Kz` e classifica o aluno no escalão `61–90`.
  - **Cenário 2 (Exceção — Prestação cancelada e bolseiro integral):**
    - **Dado** um aluno transferido em `05/01/2027` com a propina de Dezembro em atraso e um colega com `BOLSA_100`,
    - **Quando** o `SUB_ADM` consulta a dívida em `20/01/2027`,
    - **Então** a propina de Dezembro do transferido aparece como dívida de ex-aluno (situação `Transferida`), as de Janeiro a Junho não aparecem (canceladas), e o bolseiro integral não tem dívida.
  - **Cenário 3 (Bloqueio — Professor tenta consultar):**
    - **Dado** um `DIR_TURMA` autenticado,
    - **Quando** pede a dívida dos alunos da sua turma,
    - **Então** a API devolve `HTTP 403` (`RN-13.6`).

---

### `US-COB-02`: Gerar e registar avisos de cobrança escalonados
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **gerar os avisos de cobrança devidos de cada nível e registar a sua entrega**, *para* **que cada encarregado seja avisado de forma uniforme e documentada**.
- **Rastreabilidade:** `RN-13.5`, `RN-13.6`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Lote do nível 2):**
    - **Dado** 3 encarregados com prestações com 30 ou mais dias de atraso e sem aviso de nível 2 para essas prestações,
    - **Quando** o `CHEFE_SEC_GER` gera o lote do nível 2,
    - **Então** o sistema produz 3 `DOF-17` (um por encarregado, com todos os educandos devedores), regista-os como `GERADO` em `avisos_cobranca` e, ao registar a entrega presencial, passa-os a `ENTREGUE` com data e nome de quem recebeu.
  - **Cenário 2 (Exceção — Pago antes da entrega):**
    - **Dado** um aviso `GERADO` às `09h00`,
    - **Quando** o encarregado paga às `10h30` antes de o aviso lhe ser entregue,
    - **Então** o aviso passa a `ANULADO` e não aparece na lista de entregas.
  - **Cenário 3 (Bloqueio — Aviso duplicado):**
    - **Dado** que já foi entregue o aviso de nível 1 da propina de Outubro,
    - **Quando** se gera outro lote do nível 1,
    - **Então** essa prestação não volta a entrar no lote.

---

### `US-COB-03`: Propor e homologar um acordo de pagamento
- **História:** *Como* **Operador de Tesouraria (`OP_TES`)** e **Subdirector Administrativo (`SUB_ADM`)**, *quero* **reescalonar prestações vencidas em parcelas com novas datas**, *para* **que a família regularize a dívida sem acumular mais multa e, se a Direção decidir, sem bloquear documentos de frequência**.
- **Rastreabilidade:** `RN-13.7`, `RN-13.8` | `RN-08` | DOC-01 §3.6.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** o aluno do `US-COB-01` com Outubro, Novembro e Dezembro em atraso (`49.500,00 Kz` com multa fictícia),
    - **Quando** o `OP_TES` regista um acordo com 3 parcelas (Outubro até `31/01/2027`, Novembro até `28/02/2027`, Dezembro até `31/03/2027`), `liberta_semaforo = Sim`, e o `SUB_ADM`, após reautenticação, o homologa com o `DOF-18` assinado anexado,
    - **Então** as 3 prestações passam a `Em Acordo de Pagamento`, a multa deixa de crescer, o Semáforo do aluno fica verde para declarações e boletins, e grava-se `ACORDO_HOMOLOGADO` em `audit_logs`.
  - **Cenário 2 (Exceção — Guia de Transferência com acordo ativo):**
    - **Dado** o acordo acima ativo,
    - **Quando** a Secretaria Pedagógica tenta emitir a Guia de Transferência (`DOF-09C`),
    - **Então** a emissão é bloqueada com `HTTP 403 — Pendência Financeira: dívida reescalonada de 49.500,00 Kz`.
  - **Cenário 3 (Bloqueio — Homologação pelo próprio requerente):**
    - **Dado** um acordo registado pelo `CHEFE_SEC_GER`,
    - **Quando** o mesmo utilizador tenta homologá-lo,
    - **Então** o sistema recusa com `HTTP 403`.
  - **Cenário 4 (Bloqueio — Prestação a vencer no acordo):**
    - **Dado** a propina de Janeiro ainda `A Vencer`,
    - **Quando** o `OP_TES` a tenta incluir numa parcela,
    - **Então** o sistema recusa com `HTTP 422 — SÓ PRESTAÇÕES EM ATRASO PODEM SER REESCALONADAS`.

---

### `US-COB-04`: Declarar automaticamente o incumprimento de um acordo
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **que o sistema declare incumprido um acordo cuja parcela não foi paga dentro da tolerância**, *para* **que o semáforo e a multa voltem a funcionar sem intervenção manual**.
- **Rastreabilidade:** `RN-13.9`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Incumprimento):**
    - **Dado** a parcela de Outubro com data `31/01/2027` por pagar e tolerância de 5 dias (proposta),
    - **Quando** o *job* corre em `06/02/2027`,
    - **Então** o acordo passa a `INCUMPRIDO`, as prestações ainda em acordo voltam a `Em Atraso (com Multa)`, o Semáforo fica vermelho e o `SUB_ADM` recebe um alerta.
  - **Cenário 2 (Exceção — Pagamento no último dia de tolerância):**
    - **Dado** a mesma parcela,
    - **Quando** o recibo é emitido em `05/02/2027`,
    - **Então** a parcela fica paga e o acordo continua `ATIVO`.

---

### `US-COB-05`: Perdoar a multa por mora com autorização
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **perdoar total ou parcialmente a multa de uma prestação ainda não paga, com despacho**, *para* **tratar casos sociais sem alterar o valor da propina nem os recibos**.
- **Rastreabilidade:** `RN-13.4`, `RN-13.20` | DOC-01 §3.6 (`liquidarPrincipalMaisMultaOuPerdaoAutorizado`).
- **Prioridade (proposta):** `Should` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** a propina de Outubro com `15.000,00 Kz` e multa fictícia de `1.500,00 Kz`,
    - **Quando** o `SUB_ADM` perdoa `1.500,00 Kz` com o despacho `DESP-SA-IPCAG-004/2026` e justificação,
    - **Então** o valor a pagar passa a `15.000,00 Kz`, a multa calculada continua registada, cria-se a linha em `ajustes_conta_corrente` e grava-se `PERDAO_MULTA`.
  - **Cenário 2 (Bloqueio — Prestação já paga):**
    - **Dado** uma prestação `Paga` com multa incluída no recibo,
    - **Quando** o `SUB_ADM` tenta perdoar a multa,
    - **Então** o sistema recusa com `HTTP 409 — MULTA JÁ LIQUIDADA: CORREÇÃO SÓ POR NOTA DE CRÉDITO (RN-09)`.
  - **Cenário 3 (Bloqueio — Perdão do principal):**
    - **Dado** a mesma prestação de Outubro,
    - **Quando** alguém tenta perdoar `16.500,00 Kz`,
    - **Então** o sistema recusa: o perdão não pode exceder a multa (`1.500,00 Kz`).

---

### `US-COB-06`: Emitir o extrato de conta corrente para o encarregado
- **História:** *Como* **Operador de Tesouraria (`OP_TES`)**, *quero* **imprimir o extrato da conta corrente de todos os educandos de um encarregado**, *para* **que a família veja o que pagou, o que deve e o que vence**.
- **Rastreabilidade:** `RN-13.1`, `RN-13.6`.
- **Prioridade (proposta):** `Could` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Dois irmãos):**
    - **Dado** um encarregado com 2 educandos que pagaram Setembro e Outubro com o talão `BFA-998877` (`30.000,00 Kz`),
    - **Quando** o `OP_TES` emite o `DOF-19`,
    - **Então** o extrato mostra, por educando, cada prestação com bruto, desconto, multa, perdão, valor pago, n.º do recibo e estado, e os totais pago, em dívida e a vencer.
  - **Cenário 2 (Exceção — Recibo anulado por Nota de Crédito):**
    - **Dado** um recibo anulado por Nota de Crédito,
    - **Quando** o extrato é emitido,
    - **Então** o recibo aparece com a referência da Nota de Crédito e a prestação no estado para onde voltou.

---

### `US-COB-07`: Relatório de receita mensal por canal, curso e turno
- **História:** *Como* **Director Geral (`DIR_GERAL`)**, *quero* **ver a receita de cada mês repartida por canal de pagamento, curso, classe, turno escolar e rubrica**, *para* **acompanhar a sustentabilidade da escola sem folhas de cálculo paralelas**.
- **Rastreabilidade:** `RN-13.11`, `RN-13.17` | `RN-09.2`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Nota de Crédito no mês seguinte não altera o mês fechado):**
    - **Dado** o recibo `RC 2026/00187` (formato ilustrativo — `Q-004`) de `15.000,00 Kz` emitido em `20/10/2026` (canal TPA) e estornado em `05/11/2026`,
    - **Quando** o `DIR_GERAL` gera a receita de Outubro e de Novembro,
    - **Então** Outubro inclui `+15.000,00 Kz` em TPA, Novembro inclui `−15.000,00 Kz` em TPA, e o relatório de Outubro gerado antes e depois da Nota de Crédito mostra os mesmos totais.
  - **Cenário 2 (Sucesso — Pagamento combinado de 2 canais):**
    - **Dado** um recibo de `15.000,00 Kz` pago com `5.000,00 Kz` de um borderô de depósito e `10.000,00 Kz` de um borderô Multicaixa Express,
    - **Quando** o relatório é gerado,
    - **Então** o canal `Transferência / Depósito` recebe `5.000,00 Kz` e o canal `Multicaixa Express` recebe `10.000,00 Kz`.
  - **Cenário 3 (Exceção — Diferença face ao fecho de caixa):**
    - **Dado** um dia cuja soma de recibos menos Notas de Crédito não coincide com a soma das sessões de caixa homologadas,
    - **Quando** o relatório é gerado,
    - **Então** o dia aparece assinalado como **erro de integridade** com o valor da diferença.

---

### `US-COB-08`: Relatório de dívida acumulada e taxa de inadimplência
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **ver a dívida exigível e reescalonada por ano letivo de origem, situação da matrícula e antiguidade, e a taxa de inadimplência**, *para* **planear a cobrança e informar a Direção**.
- **Rastreabilidade:** `RN-13.1`, `RN-13.2`, `RN-13.10` | [[C15 - Paineis de Gestao da Direcao|IND-18, IND-19]].
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** 4 alunos com matrícula `Ativa` e prestações não isentas, dos quais 1 tem uma prestação `Em Atraso` e 1 tem prestações `Em Acordo de Pagamento`,
    - **Quando** o `SUB_ADM` gera o relatório,
    - **Então** a taxa de inadimplência é `25%` (1 em 4), os alunos em acordo aparecem numa linha própria e não contam como inadimplentes.
  - **Cenário 2 (Exceção — Sem alunos elegíveis):**
    - **Dado** um curso sem matrículas ativas com prestações não isentas,
    - **Quando** o relatório é gerado,
    - **Então** a taxa aparece como `—` (sem dados), nunca como `0%`.

---

### `US-COB-09`: Relatório do custo das bolsas, descontos e multas perdoadas
- **História:** *Como* **Director Geral (`DIR_GERAL`)**, *quero* **saber quanto a escola deixa de receber com bolsas, isenções diocesanas, descontos de irmãos e filhos de funcionários, e com multas perdoadas**, *para* **prestar contas à Diocese de Caxito e decidir a política de benefícios**.
- **Rastreabilidade:** `RN-13.12` | `RN-07`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** um aluno com `BOLSA_50` sobre a propina de `15.000,00 Kz` e um aluno com `BOLSA_100`, ambos com 10 prestações não canceladas,
    - **Quando** o `DIR_GERAL` gera o relatório do Ano Letivo,
    - **Então** o custo é `75.000,00 Kz` na linha `BOLSA_50` e `150.000,00 Kz` na linha `BOLSA_100`, com 1 beneficiário em cada.
  - **Cenário 2 (Exceção — Bolsa revogada a meio do ano):**
    - **Dado** uma `BOLSA_50` revogada a partir de Fevereiro (`RN-07`),
    - **Quando** o relatório é gerado,
    - **Então** só contam os descontos de Setembro a Janeiro (`5 × 7.500,00 = 37.500,00 Kz`), porque as prestações seguintes já foram geradas sem desconto.

---

### `US-COB-10`: Relatório de emolumentos pagos, consumidos e por consumir
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **ver os emolumentos pagos por rubrica e quantos ainda não deram origem ao documento**, *para* **que nenhum serviço pago fique por prestar**.
- **Rastreabilidade:** `RN-13.13` | `RN-08` Condição 2.
- **Prioridade (proposta):** `Could` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** 10 recibos de *Declaração com Notas* em Outubro, dos quais 8 já consumidos pela Secretaria Pedagógica,
    - **Quando** o relatório é gerado em `31/10/2026`,
    - **Então** mostra 10 pagos, 8 consumidos e 2 por consumir com os dias desde o pagamento.
  - **Cenário 2 (Exceção — Emolumento estornado):**
    - **Dado** um dos 10 recibos estornado,
    - **Quando** o relatório é regenerado,
    - **Então** os pagos passam a 9 no mês da Nota de Crédito, sem alterar o total de Outubro já apresentado.

---

### `US-COB-11`: Importar o extrato bancário e conciliar com os borderôs
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **importar o extrato do mês e confirmar as correspondências propostas com os borderôs**, *para* **provar que cada talão registado entrou de facto na conta do IPCAG**.
- **Rastreabilidade:** `RN-13.14`, `RN-13.15` | `RN-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Correspondência exata):**
    - **Dado** o borderô `BFA-998877` de `30.000,00 Kz` registado em `05/10/2026`,
    - **Quando** o extrato do BFA de Outubro tem uma linha de crédito `998877` de `30.000,00 Kz` em `05/10/2026` e o `CHEFE_SEC_GER` confirma a sugestão,
    - **Então** o borderô passa a `CONCILIADO` e a linha a `CONCILIADA`.
  - **Cenário 2 (Exceção — Crédito agregado com comissão):**
    - **Dado** 3 borderôs TPA do mesmo dia num total de `45.000,00 Kz`,
    - **Quando** o extrato mostra uma só linha de `44.550,00 Kz` (valores fictícios),
    - **Então** o `CHEFE_SEC_GER` liga a linha aos 3 borderôs, regista a diferença de `450,00 Kz` como `COMISSAO_BANCARIA` e a correspondência só fica confirmada depois da aprovação do `SUB_ADM`.
  - **Cenário 3 (Bloqueio — Segregação):**
    - **Dado** o `OP_TES` que registou o borderô `BFA-998877`,
    - **Quando** tenta abrir a conciliação,
    - **Então** a API devolve `HTTP 403`.
  - **Cenário 4 (Bloqueio — Extrato duplicado):**
    - **Dado** o ficheiro do extrato de Outubro já importado,
    - **Quando** é importado de novo,
    - **Então** o sistema recusa com `HTTP 409 — EXTRATO JÁ IMPORTADO`.

---

### `US-COB-12`: Tratar um borderô não encontrado no extrato
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **ser alertado quando um borderô não aparece no extrato e decidir entre engano de registo e fraude**, *para* **detetar talões falsos dentro do mês e não meses depois**.
- **Rastreabilidade:** `RN-13.16` | DOC-01 §3.7 | `US-TES-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Alerta e fraude):**
    - **Dado** o borderô `OP-2026-778899` (BAI, `30.000,00 Kz`, `12/10/2026`) usado nos recibos `RC 2026/00105` e `RC 2026/00106`, e o extrato do BAI de Outubro importado sem correspondência,
    - **Quando** passam 5 dias úteis de tolerância (proposta),
    - **Então** o borderô passa a `NAO_ENCONTRADO`, o `SUB_ADM` recebe um alerta crítico e, ao confirmar a fraude, o sistema executa `declararFraudeBancaria` (Notas de Crédito em cascata e semáforo vermelho dos 2 alunos).
  - **Cenário 2 (Exceção — Engano de banco):**
    - **Dado** que a investigação mostra que o depósito foi feito no BFA e não no BAI,
    - **Quando** o `SUB_ADM` regista a decisão "engano de registo",
    - **Então** emite Notas de Crédito dos 2 recibos, o `OP_TES` regista o borderô correto no BFA e reemite os recibos, e o borderô original fica com o histórico completo, sem ter sido editado.
  - **Cenário 3 (Bloqueio — Usar saldo em investigação):**
    - **Dado** um borderô `NAO_ENCONTRADO` com `saldo_disponivel = 5.000,00 Kz`,
    - **Quando** o `OP_TES` o tenta usar num recibo,
    - **Então** o sistema recusa com `HTTP 409 — BORDERÔ EM INVESTIGAÇÃO`.

---

### `US-COB-13`: Homologar o fecho mensal da conciliação
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **homologar a conciliação do mês e imprimir o Mapa de Conciliação Bancária**, *para* **trancar o mês e prestar contas à Direção**.
- **Rastreabilidade:** `RN-13.19`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E2`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** que todas as linhas de crédito de Outubro do BFA estão tratadas e todos os borderôs do mês estão `CONCILIADO` ou com alerta registado,
    - **Quando** o `SUB_ADM` homologa após reautenticação,
    - **Então** o período fica `FECHADO_HOMOLOGADO` e é emitido o `DOF-20`.
  - **Cenário 2 (Bloqueio — Linhas por tratar):**
    - **Dado** 2 linhas de crédito ainda `POR_CONCILIAR`,
    - **Quando** o `SUB_ADM` tenta homologar,
    - **Então** o sistema recusa e lista as 2 linhas.
  - **Cenário 3 (Bloqueio — Autoconferência):**
    - **Dado** que foi o `SUB_ADM` quem confirmou as correspondências,
    - **Quando** tenta homologar,
    - **Então** o sistema exige a homologação do `DIR_GERAL`.

---

### `US-COB-14`: Fecho administrativo de caixa por ausência do operador
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **fechar a sessão de caixa de um operador que saiu sem a fechar**, *para* **que o turno fique conferido e homologado como os restantes**.
- **Rastreabilidade:** `RN-13.18` | `RN-09.2` | [[C14 - Gestao de Contas e Acesso|RN-16.8]].
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** a sessão do Turno da Manhã de `14/01/2027` `Aberto`, com 12 recibos, cujo operador saiu às `11h00`,
    - **Quando** o `CHEFE_SEC_GER` confere os talões, executa o fecho administrativo com o motivo *"Saída do operador"* e o `SUB_ADM` homologa,
    - **Então** o `DOF-11C` é emitido com a menção de fecho administrativo e a sessão fica `Homologado pela Administração`.
  - **Cenário 2 (Exceção — Talão em falta):**
    - **Dado** que só aparecem 11 dos 12 comprovativos físicos,
    - **Quando** o fecho administrativo é feito,
    - **Então** fica registada a diferença apurada com o recibo cujo comprovativo falta, sem alterar nenhum recibo, e o borderô desse recibo fica marcado para verificação prioritária na conciliação.
  - **Cenário 3 (Bloqueio — Mesma pessoa fecha e homologa):**
    - **Dado** que o fecho administrativo foi executado pelo `SUB_ADM`,
    - **Quando** o `SUB_ADM` tenta homologar,
    - **Então** o sistema exige a homologação do `DIR_GERAL`.

---

### `US-COB-15` *(fora das E1–E5 — `DEC-005` decidida)*: Conciliar automaticamente pagamentos por referência
- **Estado:** a `DEC-005` deixou as referências Multicaixa / *gateway* **fora das entregas E1–E5**. A história fica registada como referência para um futuro pedido de alteração; **não entra no catálogo da E1 a E5**.
- **Prioridade (proposta):** `Won't` (nesta linha de base).
- **Critério de referência:** **Dado** um pagamento por referência confirmado pelo fornecedor, **Quando** a notificação chega ao SGE, **Então** o borderô nasce `CONCILIADO` e o recibo é emitido pelas regras normais do `RN-09`.
- **Critério de exceção de referência:** **Dado** que o fornecedor envia duas vezes a notificação da mesma referência, **Quando** chega a segunda, **Então** o SGE não cria um segundo borderô nem um segundo recibo (unicidade de `(banco_id, numero_operacao_bordero)` — `RN-09.1`).

---

## ÉPICO 11 (`EP-COM`): Comunicação com Encarregados e Alunos (Avisos, Convocatórias, SMS e Portal)

> [!abstract] Origem
> Histórias da [[C12 - Comunicacao com Encarregados e Alunos|CAP-C12]] §6 (critérios expandidos para o formato BDD deste documento), com os identificadores mantidos. As regras provisórias da nota (C12) passam à família `RN-14` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-21` (Convocatória numerada) e `DOF-22` (Aviso impresso) (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Sobre os exemplos
> O limite de `12` faltas injustificadas, os limiares de `50%` e `80%` (`Q-C12-05`), o teto de `1.000` SMS e a convocatória de `15/03` são ilustrativos e vêm da [[C12 - Comunicacao com Encarregados e Alunos|CAP-C12]]. Os limiares e os gatilhos pedidos pela escola (faltas, propina vencida, resultados, convocatórias) e a taxa de `20–30%` de telefones errados vêm das entrevistas ([[Sintese das Respostas da Fase B|DESC-RESP]] R26).

> [!success] Faseamento da Central de Avisos — `DEC-015`
> A `DEC-015` (2026-11-09, Issue #18) antecipou a **central de avisos interna** (impresso e SMS sob teto, sem abrir dados à internet: `US-COM-01` a `US-COM-06`) para a **E3** (Fecho do I Trimestre), deixando o portal web de encarregados e alunos (`US-COM-07`, `US-COM-08`) na **E5** (`DEC-003`). As questões `Q-037` e `Q-C12-01` estão respondidas.

---

### `US-COM-01`: Aprovar os Modelos de Mensagem dos Avisos
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** (avisos pedagógicos) ou **Subdirector Administrativo (`SUB_ADM`)** (avisos financeiros), *quero* **aprovar os textos dos avisos e os campos substituíveis que cada um usa**, *para* **que nenhuma mensagem saia com dados que a APD não permite enviar**.
- **Rastreabilidade:** `RN-14.4`, `RN-14.5`, `RN-14.1` | [[11 - Protecao de Dados (APD)|APD-11]] §7.4 | `MOD-COM-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Utilizador autenticado como `SUB_PED`, `SUB_ADM` ou `DIR_GERAL`; lista de campos permitidos carregada (primeiro nome do aluno, mês de referência, data/hora/local, limiar atingido).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Modelo de faltas aprovado):**
    - **Dado** o modelo `FALTAS_80` com o texto *"IPCAG: o seu educando [primeiro_nome] tem faltas acumuladas com risco de retenção. Contacte o Director de Turma. Secretaria: [contacto]"*,
    - **Quando** o `SUB_PED` o aprova,
    - **Então** o modelo fica `ativo`, com aprovador e data, e passa a ser usado pelo gatilho `FALTAS_80`; grava-se `MODELO_APROVADO` em `audit_logs`.
  - **Cenário 2 (Bloqueio — Campo proibido):**
    - **Dado** um modelo de propina que inclui o campo `valor_divida`,
    - **Quando** o `SUB_ADM` tenta aprová-lo,
    - **Então** o sistema recusa com `HTTP 422`: *"O campo valor_divida não está na lista de campos permitidos (APD-11 §7.4)"*.
  - **Cenário 3 (Aviso — Excede uma mensagem SMS):**
    - **Dado** um modelo que, substituídos os campos no pior caso, chega a `175` caracteres,
    - **Quando** é gravado,
    - **Então** o sistema avisa que excede os `160` caracteres de uma mensagem e não o deixa aprovar para o canal `SMS` (`RN-14.4.4`).
- **Pós-condições e Efeitos Colaterais:** `modelos_mensagem` atualizado; eventos em `audit_logs`.

---

### `US-COM-02`: Gerar o Aviso Automático de Faltas ao Encarregado
- **História:** *Como* **Encarregado de Educação**, *quero* **ser avisado quando o meu educando acumula faltas numa disciplina**, *para* **poder agir antes da retenção por faltas**.
- **Rastreabilidade:** `RN-14.5`, `RN-14.1`, `RN-14.3`, `RN-03` | `RN-17.8` (alerta precoce) | `MOD-COM-02`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Gatilhos `FALTAS_50` e `FALTAS_80` ativos 🟡 (limiares parametrizáveis — `Q-C12-05`); modelos aprovados (`US-COM-01`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — 50% do limite):**
    - **Dado** um limite de `12` faltas injustificadas em *Matemática* e o aluno com `5`,
    - **Quando** o professor regista a `6.ª` falta,
    - **Então** gera-se um aviso `FALTAS_50` para o encarregado, sem indicar a disciplina nem o número de faltas.
  - **Cenário 2 (Exceção — Gatilho não se repete):**
    - **Dado** que o aviso `FALTAS_50` de *Matemática* já foi gerado neste ano letivo,
    - **Quando** o aluno chega à `7.ª` falta,
    - **Então** não se gera novo aviso `FALTAS_50` (`RN-14.5.2`).
  - **Cenário 3 (Exceção — Telefone inválido ou sem SMS):**
    - **Dado** o telefone do encarregado no estado `INVALIDO` (ou o SMS não aprovado pela Direção),
    - **Quando** o aviso é gerado,
    - **Então** vai para a lista diária de impressos do Director de Turma (`RN-14.1.3`, `RN-14.1.5`).
  - **Cenário 4 (Exceção — Justificação depois do aviso):**
    - **Dado** que o aviso `FALTAS_50` já saiu e a justificação aprovada faz descer o total para `4` faltas,
    - **Quando** o aluno volta a faltar,
    - **Então** o aviso enviado mantém-se no histórico e o próximo só sai se o total voltar a cruzar o limiar (`RN-14.5.3`).
- **Pós-condições e Efeitos Colaterais:** linha em `avisos` com o estado e a ligação à falta de origem.

---

### `US-COM-03`: Emitir uma Convocatória Numerada ao Encarregado
- **História:** *Como* **Director de Turma (`DIR_TURMA`)**, **Coordenador de Turno (`COORD_TURNO`)** ou **Direção**, *quero* **convocar um encarregado com uma convocatória numerada**, *para* **que compareça na escola e fique prova de que foi convocado**.
- **Rastreabilidade:** `RN-14.7`, `RN-14.8` | `RN-15.5.3` (convocatória disciplinar) | `DOF-21` | `MOD-COM-02`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Série anual de convocatórias configurada em `series_numeracao_documental`; encarregado atual registado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Convocatória numerada):**
    - **Dado** uma convocatória do `DIR_TURMA` de `CG10A-T` para `15/03` às `14h00`, motivo `PEDAGOGICO`,
    - **Quando** a emite,
    - **Então** recebe o número seguinte da série anual (`N.º ___/IPCAG/ano`), imprime-se o `DOF-21` e, se houver SMS, a mensagem sai com data, hora e local **sem o motivo**.
  - **Cenário 2 (Exceção — Duas faltas de comparência seguidas):**
    - **Dado** que o encarregado não compareceu à convocatória anterior,
    - **Quando** o `DIR_TURMA` regista a segunda falta de comparência seguida,
    - **Então** a Direção recebe um alerta (`RN-14.7.3`).
  - **Cenário 3 (Bloqueio — Turma de outro Director):**
    - **Dado** um `DIR_TURMA` de `CG10A-T`,
    - **Quando** tenta convocar o encarregado de um aluno de outra turma,
    - **Então** a API rejeita com `HTTP 403`.
- **Pós-condições e Efeitos Colaterais:** `convocatorias` e `avisos` gravados; evento `CONVOCATORIA_EMITIDA`.

---

### `US-COM-04`: Verificar e Atualizar os Contactos do Encarregado
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **confirmar na matrícula e na confirmação os telefones do encarregado e de quem é cada um**, *para* **que os avisos cheguem a quem deve (hoje `20–30%` dos telefones estão errados)**.
- **Rastreabilidade:** `RN-14.3`, `RN-14.2` | `US-PIN-07` | `MOD-COM-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Matrícula ou confirmação em curso; até dois telefones do encarregado (campos reais do boletim — DESC-L1 A12).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Verificação com SMS ativo):**
    - **Dado** um telefone novo `+244 9xx xxx xxx` com titular `MAE` e SMS ativo,
    - **Quando** o `OP_PED` o regista,
    - **Então** sai um código de `4` dígitos e o contacto só fica `VERIFICADO` depois de o encarregado o repetir ao balcão.
  - **Cenário 2 (Exceção — 3 falhas de entrega seguidas):**
    - **Dado** um contacto com `3` falhas de entrega seguidas,
    - **Quando** o `DIR_TURMA` abre a lista "contactos a atualizar",
    - **Então** o aluno aparece com a turma e o telefone passa a `INVALIDO` (`RN-14.3.3`).
  - **Cenário 3 (Bloqueio — Telefone do aluno menor):**
    - **Dado** um telefone marcado com titular `ALUNO` e um aluno com `16` anos,
    - **Quando** se gera um aviso,
    - **Então** o sistema não o usa como destino e o aviso segue para o encarregado ou para impresso (`RN-14.2.3`).
- **Pós-condições e Efeitos Colaterais:** `contactos_encarregado` atualizado; `CONTACTO_ALTERADO` em `audit_logs`.

---

### `US-COM-05`: Acompanhar as Entregas e o Custo dos Avisos
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **ver quantos avisos foram enviados, entregues e falharam, e o custo do mês**, *para* **controlar o orçamento de SMS**.
- **Rastreabilidade:** `RN-14.6`, `RN-14.8` | `MOD-COM-01`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Teto mensal de SMS definido pela Direção 🟡 (`Q-C12-01`, `Q-C12-06`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Alerta aos 80% do teto):**
    - **Dado** o teto mensal de `1.000` SMS e `799` já enviados,
    - **Quando** sai o `800.º`,
    - **Então** o `SUB_ADM` recebe um alerta.
  - **Cenário 2 (Exceção — Teto atingido):**
    - **Dado** que o teto de `1.000` SMS foi atingido,
    - **Quando** se gera um aviso `RESULTADOS_TRIMESTRE`,
    - **Então** o aviso passa a impresso; só as convocatórias e os avisos `FALTAS_80` continuam por SMS (`RN-14.6.3`).
- **Pós-condições e Efeitos Colaterais:** relatório mensal de envios por gatilho, canal e estado.

---

### `US-COM-06`: Registar o Consentimento e a Recusa de Avisos
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **registar se o encarregado aceita avisos por SMS e se recusa os não essenciais**, *para* **respeitar a escolha dele sem deixar de avisar o que é obrigatório**.
- **Rastreabilidade:** `RN-14.9` | APD-11 | `DOF-03` (consentimento na ficha) | `MOD-COM-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (`DEC-015`).
- **Pré-condições:** Matrícula ou confirmação em curso.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Recusa dos não essenciais):**
    - **Dado** um encarregado que recusou os avisos não essenciais,
    - **Quando** a Pauta Geral do I Trimestre é homologada,
    - **Então** não lhe sai o aviso `RESULTADOS_TRIMESTRE`, mas continuam a sair as convocatórias.
  - **Cenário 2 (Exceção — Avisos essenciais com recusa de SMS):**
    - **Dado** um encarregado que recusou todos os SMS,
    - **Quando** o educando atinge `80%` do limite de faltas,
    - **Então** o aviso `FALTAS_80` sai **pelo impresso** (`RN-14.9.2`).
- **Pós-condições e Efeitos Colaterais:** `consentimentos` (finalidade `CON-05` — avisos não essenciais por SMS) com valor e data; `CONSENTIMENTO_ALTERADO` em `audit_logs`.

---

### `US-COM-07` *(E5 — `DEC-003`)*: Ativar e Usar o Portal do Encarregado
- **História:** *Como* **Encarregado de Educação**, *quero* **consultar as notas, faltas e pagamentos dos meus educandos**, *para* **não ter de ir à escola só para saber como estão**.
- **Rastreabilidade:** `RN-14.10`, `RN-08` | `US-CTA-14`, [[C14 - Gestao de Contas e Acesso|CAP-C14]] §11 | `MOD-COM-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E5`.
- **Pré-condições:** Código de ativação de uso único entregue ao balcão contra o BI do encarregado (`RN-14.10.1`); L8 (proteção de dados) fechada antes de abrir o portal.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Ativação e vista dos educandos):**
    - **Dado** um código de ativação entregue ao balcão,
    - **Quando** o encarregado ativa a conta,
    - **Então** vê os `2` educandos ligados ao seu BI e só esses.
  - **Cenário 2 (Bloqueio — Boletim com dívida):**
    - **Dado** um educando com propinas em atraso,
    - **Quando** o encarregado pede o boletim (`DOF-06`) em PDF,
    - **Então** o sistema aplica a mesma regra do balcão (`RN-08`) 🟡 — mostra as notas mas não deixa descarregar o boletim oficial, se a Comissão de Gestão o confirmar (`Q-C12-03`).
  - **Cenário 3 (Exceção — Ocorrência disciplinar):**
    - **Dado** que o educando tem uma ocorrência disciplinar no trimestre,
    - **Quando** o encarregado consulta o portal,
    - **Então** vê só o comportamento do trimestre, sem a ocorrência (`RN-14.10.5`, `RN-15.8.2`).
- **Pós-condições e Efeitos Colaterais:** `PORTAL_ATIVADO` em `audit_logs`; consultas registadas.

---

### `US-COM-08` *(E5 — `DEC-003`)*: Consultar o Portal como Aluno
- **História:** *Como* **Aluno**, *quero* **ver as minhas faltas, as minhas notas e o meu horário**, *para* **não ser apanhado de surpresa por um limite de faltas ou por uma mudança de horário**.
- **Rastreabilidade:** `RN-14.10.6`, `RN-14.2.2` | `RN-03` | `MOD-COM-04`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E5` (🟡 a partir de que classe e se o aluno tem conta própria — `Q-C12-04`).
- **Pré-condições:** Conta `ALUNO` ativada presencialmente.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Justificação em todas as disciplinas):**
    - **Dado** que o aluno faltou um dia inteiro e a justificação foi aprovada pelo `DIR_TURMA` e pelo `SUB_PED`,
    - **Quando** consulta as faltas,
    - **Então** vê-as como justificadas em **todas** as disciplinas desse dia (prática real — DESC-RESP R3).
  - **Cenário 2 (Bloqueio — Parte financeira):**
    - **Dado** um aluno com conta própria,
    - **Quando** tenta abrir a situação de pagamentos,
    - **Então** o portal não mostra a parte financeira (`RN-14.10.6`).
- **Pós-condições e Efeitos Colaterais:** nenhuma alteração; consultas registadas.

---

## ÉPICO 12 (`EP-DIS`): Disciplina e Comportamento

> [!abstract] Origem
> Histórias da [[C13 - Disciplina e Comportamento|CAP-C13]] §6 (critérios expandidos para o formato BDD deste documento), com os identificadores mantidos. As regras provisórias da nota (C13) passam à família `RN-15` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-23` (Participação de Ocorrência) e `DOF-24` (Notificação de Decisão Disciplinar) (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Sobre os exemplos
> A distinção entre faltas por indisciplina e por não comparência, o comportamento por trimestre e a tolerância de `10–15 min` no 1.º tempo vêm do boletim real e das entrevistas ([[Achados dos Documentos Reais - Lote 1|DESC-L1]] A8; [[Sintese das Respostas da Fase B|DESC-RESP]] R1–R2). O 1.º tempo da manhã às `07h30` é o da janela do turno do DOC-01. Os tipos de ocorrência, as medidas e a escala de comportamento são **propostas** à espera do regulamento interno (`DEC-009`, ponto de controlo **E3**).

> [!warning] 🟡 Entrega por decidir — `Q-038`
> **Decidido na `DEC-013` (2026-11-05):** o **núcleo** da C13 sai antes, porque o boletim real (`DOF-06`) já imprime as faltas por tipo e o comportamento no fim do I Trimestre: tipos de falta (`US-DIS-01`) na **E2** e comportamento trimestral (`US-DIS-04`) na **E3**. Ocorrências completas, medidas e processos ficam na **E5**.

---

### `US-DIS-01`: Marcar uma Falta por Indisciplina em Sala
- **História:** *Como* **Professor (`PROF`)**, *quero* **marcar uma falta por indisciplina quando mando um aluno sair da sala, com uma ocorrência rápida ligada**, *para* **que o facto fique registado, seja acompanhado pelo Coordenador de Turno e saia no boletim como falta por indisciplina**.
- **Rastreabilidade:** `RN-15.1`, `RN-15.3`, `RN-03` | `US-PED-02`, `US-HOR-06` | `MOD-DIS-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2` (núcleo da C13 — `DEC-013`).
- **Pré-condições:** Aula `Lecionada` do horário publicado (`US-HOR-06`); professor alocado à turma.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Falta com ocorrência rápida):**
    - **Dado** o 3.º tempo de *Matemática* da `CG10A-T`,
    - **Quando** o `PROF` marca falta por indisciplina ao aluno `N.º 14`,
    - **Então** o sistema pede uma descrição factual curta, grava a falta com `tipo_falta = INDISCIPLINA` e cria a ocorrência ligada no estado `Registada`; o contador de faltas por indisciplina do aluno sobe `1`.
  - **Cenário 2 (Bloqueio — Justificar uma falta por indisciplina):**
    - **Dado** uma falta por indisciplina,
    - **Quando** o `DIR_TURMA` tenta justificá-la pelo circuito da `RN-03`,
    - **Então** o sistema recusa com `HTTP 422`: *"As faltas por indisciplina não se justificam"* 🟡 (`RN-15.1.3`, `Q-C13-03`).
  - **Cenário 3 (Exceção — Ocorrência por completar no fim do dia):**
    - **Dado** uma falta por indisciplina sem ocorrência completa às `18h05`,
    - **Quando** o dia letivo termina,
    - **Então** a falta aparece na lista do `COORD_TURNO` e bloqueia o fecho do trimestre da turma até ser completada (`RN-15.1.2`).
  - **Cenário 4 (Sucesso — Sem rede):**
    - **Dado** que o telemóvel do professor está sem rede,
    - **Quando** marca a falta e a ocorrência rápida,
    - **Então** ambas ficam na fila *offline* e sincronizam juntas quando a rede volta.
- **Pós-condições e Efeitos Colaterais:** `sumarios_e_faltas_alunos` com `tipo_falta` e `ocorrencia_id`; `OCORRENCIA_REGISTADA` em `audit_logs`. Se a falta por indisciplina conta para o limite da `RN-03` fica 🟡 por confirmar (`Q-C13-03`).

---

### `US-DIS-02`: Completar a Ocorrência e Aplicar uma Medida Simples
- **História:** *Como* **Coordenador de Turno (`COORD_TURNO`)**, *quero* **completar a ocorrência e aplicar uma medida simples do catálogo**, *para* **que o caso fique resolvido e registado sem passar pela Direção**.
- **Rastreabilidade:** `RN-15.3`, `RN-15.4`, `RN-15.5` | `MOD-DIS-02`.
- **Prioridade (proposta):** `Must` *(era `Should` — `DEC-013`, regra 1)* | **Entrega:** `E5`.
- **Pré-condições:** Ocorrência `Registada` ou `Em Análise`; catálogo de medidas aprovado 🟡 (regulamento interno — `Q-C13-06`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Medida simples):**
    - **Dado** uma ocorrência `LEVE` (🟡 escala de gravidade do regulamento interno — lista 46, `Q-C13-04`; E3),
    - **Quando** o `COORD_TURNO` aplica a medida "retenção do cartão de estudante",
    - **Então** a ocorrência passa a `Medida Aplicada`, a medida fica com data, decisor e fundamento, e o `DIR_TURMA` é notificado no sistema.
  - **Cenário 2 (Bloqueio — Suspensão sem processo):**
    - **Dado** uma ocorrência `MUITO_GRAVE`,
    - **Quando** o `COORD_TURNO` tenta aplicar "suspensão",
    - **Então** o sistema recusa: a suspensão só é aplicada pela Direção num processo disciplinar (`RN-15.5`, `US-DIS-03`).
  - **Cenário 3 (Exceção — Ocorrência no aluno errado):**
    - **Dado** uma ocorrência fechada registada no aluno errado,
    - **Quando** o `COORD_TURNO` a retifica com motivo,
    - **Então** o registo não se apaga, o aluno errado deixa de a ver associada e grava-se `OCORRENCIA_RETIFICADA` (`RN-15.3.5`).
- **Pós-condições e Efeitos Colaterais:** `ocorrencias_disciplinares` e `medidas_aplicadas` gravadas; convocatória, se aplicável, pela central de avisos (`US-COM-03`); participação imprimível (`DOF-23`).

---

### `US-DIS-03`: Conduzir um Processo Disciplinar com Direito de Defesa
- **História:** *Como* **Direção (`DIR_GERAL`, com instrução pelo `SUB_PED`)**, *quero* **instaurar, instruir e decidir um processo disciplinar**, *para* **que uma suspensão respeite o direito de defesa do aluno e do encarregado**.
- **Rastreabilidade:** `RN-15.6`, `RN-15.5` | `US-COM-03` | `DOF-24` | `MOD-DIS-04`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E5`.
- **Pré-condições:** Ocorrência `MUITO_GRAVE` ou que pode levar a suspensão; prazos dos passos 🟡 parametrizados pelo regulamento interno (`Q-C13-06`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Decisão e notificação):**
    - **Dado** um processo `Instaurado` com instrutor nomeado, audição do aluno e do encarregado registada e relatório anexado,
    - **Quando** o `DIR_GERAL` decide uma suspensão de `3` dias,
    - **Então** o processo passa a `Decidido`, a medida liga-se à ocorrência, emite-se a Notificação de Decisão Disciplinar (`DOF-24`) e grava-se `PROCESSO_DECIDIDO`.
  - **Cenário 2 (Bloqueio — Decidir sem audição):**
    - **Dado** um processo sem audição registada,
    - **Quando** o `DIR_GERAL` tenta decidir,
    - **Então** o sistema recusa, salvo se houver convocatória com falta de comparência registada (`US-COM-03`).
  - **Cenário 3 (Exceção — Dias de suspensão):**
    - **Dado** uma suspensão de `3` dias,
    - **Quando** chegam esses dias,
    - **Então** o sistema não gera faltas injustificadas automáticas 🟡 (`RN-15.5.2`, `Q-C13-05`).
- **Pós-condições e Efeitos Colaterais:** `processos_disciplinares` com as datas de cada passo; eventual recurso 🟡 (`Q-C13-06`).

---

### `US-DIS-04`: Propor e Confirmar o Comportamento do Trimestre
- **História:** *Como* **Director de Turma (`DIR_TURMA`)**, *quero* **propor a avaliação de comportamento de cada aluno vendo as ocorrências e as faltas por indisciplina do trimestre**, *para* **que o conselho de notas decida com base em factos e o boletim saia como o modelo real**.
- **Rastreabilidade:** `RF-C13-02` | `RN-15.4`, `RN-15.7` | `US-PED-06`, `US-DOC-01` (`DOF-06`) | `MOD-DIS-03`, `MOD-DIS-05` | `tipos_ocorrencia`, `medidas_disciplinares_catalogo`, `comportamento_trimestral` | 🟡 PC-E3 · `Q-C13-06`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (escala do comportamento) / `E5` (resto do regulamento) — `DEC-013`.
- **Pré-condições:** Trimestre `Em Conselho de Notas`; escala 🟡 parametrizada (qualitativa ou numérica — `Q-C13-02`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Proposta com factos):**
    - **Dado** um aluno com `3` ocorrências e `2` faltas por indisciplina no I Trimestre,
    - **Quando** o `DIR_TURMA` abre a proposta,
    - **Então** vê-as resumidas ao lado da escala e regista a proposta; o conselho confirma ou altera e a decisão fica na ata.
  - **Cenário 2 (Bloqueio — Alterar depois da homologação):**
    - **Dado** a Pauta Geral do trimestre homologada,
    - **Quando** alguém tenta alterar o comportamento,
    - **Então** o sistema exige a reabertura auditada (`US-GOV-04`) (`RN-15.7.4`).
  - **Cenário 3 (Exceção — Comportamento não entra nas notas):**
    - **Dado** um comportamento "Insuficiente",
    - **Quando** o motor calcula `CF` e `CA` e delibera a transição,
    - **Então** o comportamento não entra no cálculo nem na deliberação 🟡 (`RN-15.7.5`, `Q-C13-02`).
  - **Cenário 4 (Sucesso 🟡 — Parametrização da Escala de Comportamento e do Catálogo Disciplinar — `RF-C13-02`, `RN-15.4`, `MOD-DIS-05`, `DEC-009`, `DEC-013`):**
    - **Dado** a aprovação do regulamento interno da escola pela Direção (`DIR_GERAL`),
    - **Quando** o `SUB_PED` acede à consola de configuração disciplinar (`MOD-DIS-05`),
    - **Então** parametriza para a **E3** a escala oficial de avaliação do comportamento trimestral (qualitativa ou numérica, conforme `Q-C13-02`), e para a **E5** os tipos de ocorrência, graus de gravidade (`LEVE`, `GRAVE`, `MUITO_GRAVE`), catálogo de medidas disciplinares e competências de aplicação (`tipos_ocorrencia`, `medidas_disciplinares_catalogo`), garantindo que nenhuma sanção fora do regulamento possa ser aplicada.
- **Pós-condições e Efeitos Colaterais:** `comportamento_trimestral` fechado com a Pauta Geral; catálogo disciplinar versionado em `tipos_ocorrencia` e `medidas_disciplinares_catalogo`; impresso no `DOF-06`; `COMPORTAMENTO_ALTERADO` em `audit_logs` se o conselho alterar a proposta.

---

### `US-DIS-05`: Registar Atrasos com Tolerância no 1.º Tempo
- **História:** *Como* **Coordenador de Turno (`COORD_TURNO`)**, *quero* **registar as entradas tardias dos alunos**, *para* **que a tolerância e as faltas do 1.º tempo se apliquem sempre da mesma forma**.
- **Rastreabilidade:** `RN-15.2` | DESC-RESP R1 | `MOD-DIS-02`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E5`.
- **Pré-condições:** Tolerância do 1.º tempo parametrizada 🟡 (por omissão `15 min`; prática real `10–15 min`; igual nos dois turnos? — `Q-C13-04`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Dentro da tolerância):**
    - **Dado** uma tolerância de `15 min` e o 1.º tempo da manhã às `07h30`,
    - **Quando** o aluno entra às `07h40`,
    - **Então** fica registado um atraso de `10 min` dentro da tolerância, sem falta.
  - **Cenário 2 (Exceção — Depois da tolerância):**
    - **Dado** a mesma tolerância,
    - **Quando** o aluno entra às `07h50`,
    - **Então** aguarda o tempo seguinte e fica com falta de não comparência no 1.º tempo (`RN-15.2.2`).
  - **Cenário 3 (Exceção — Atrasos reiterados):**
    - **Dado** que o número de atrasos por mês que gera ocorrência é um parâmetro 🟡 (`Q-C13-04`),
    - **Quando** o aluno atinge esse número no mês,
    - **Então** o sistema cria automaticamente uma ocorrência do tipo "atrasos reiterados".
- **Pós-condições e Efeitos Colaterais:** `atrasos_alunos` gravado; falta no 1.º tempo quando aplicável.

---

### `US-DIS-06`: Consultar o Histórico Disciplinar com Restrições de Acesso
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **ver o histórico disciplinar completo de um aluno**, *para* **decidir casos graves com informação completa, sem que esses dados apareçam onde não devem**.
- **Rastreabilidade:** `RN-15.8` | APD-11 | `MOD-DIS-04`.
- **Prioridade (proposta):** `Must` *(era `Should` — `DEC-013`, regra 1)* | **Entrega:** `E5`.
- **Pré-condições:** Ocorrências registadas.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Histórico para a Subdireção):**
    - **Dado** um aluno com ocorrências na 10ª e na 11ª Classe,
    - **Quando** o `SUB_PED` abre o histórico,
    - **Então** vê todas as ocorrências, medidas e processos, por ano letivo.
  - **Cenário 2 (Bloqueio — Professor que não registou):**
    - **Dado** um `PROF` que não registou a ocorrência,
    - **Quando** tenta abri-la,
    - **Então** a API rejeita com `HTTP 403` e regista a tentativa.
  - **Cenário 3 (Exceção — Documentos para fora da escola):**
    - **Dado** um pedido de Declaração de Estudos ou de Guia de Transferência,
    - **Quando** o documento é emitido,
    - **Então** não inclui nenhuma ocorrência (`RN-15.8.2`).
- **Pós-condições e Efeitos Colaterais:** acessos registados; prazo de conservação 🟡 (`Q-APD-32`).

---

## ÉPICO 13 (`EP-CTA`): Gestão de Contas e Acesso (Ciclo de Vida, MFA, PIN Local, Títulos dos Cargos)

> [!abstract] Origem
> Histórias da [[C14 - Gestao de Contas e Acesso|CAP-C14]] §6, com os identificadores mantidos. As regras provisórias da nota (C14) passam à família `RN-16` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a nenhum documento novo; os blocos de assinatura de todos os `DOF` passam a usar os títulos configurados (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Sobre os exemplos
> Os nomes de pessoas são fictícios. Os valores de política (10 caracteres, 5 tentativas, 15 min, 7 dias, 6 dígitos) são **propostas** da [[C14 - Gestao de Contas e Acesso|CAP-C14]] ou metas propostas do PLN-00 §5.3, e serão substituídos pelos valores aprovados no [[08 - Requisitos Nao Funcionais]].

---

### `US-CTA-01`: Pedir e aprovar a conta de um funcionário novo
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **pedir a conta de um funcionário recém-admitido com os cargos e escopos propostos**, *para* **que a Direção aprove o acesso antes de a pessoa começar a trabalhar no SGE**.
- **Rastreabilidade:** `RN-16.1`, `RN-16.2`, `RN-16.3`, `RN-16.5`, `RN-16.18` | Fluxo C14-A | `C14`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Cadastro em `funcionarios_docentes` com Nome, BI e Telefone; utilizador autenticado como `CHEFE_SEC_GER`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Professor novo):**
    - **Dado** que o docente *Mateus Kiala* tem cadastro ativo com categoria `Docente`,
    - **Quando** o `CHEFE_SEC_GER` pede a conta com a atribuição `PROF` (escopo `ALOCACOES_DOCENTES`) e o `SUB_PED` a aprova com a referência do despacho,
    - **Então** a conta fica `PENDENTE_ATIVACAO`, a atribuição fica `ATIVA` e são gravados `CONTA_PEDIDA` e `ATRIBUICAO_APROVADA` em `audit_logs` (categoria `SEGURANCA_CONTAS`).
  - **Cenário 2 (Bloqueio — Auto-aprovação):**
    - **Dado** um pedido de atribuição `COORD_CURSO` cujo titular é o próprio `SUB_PED`,
    - **Quando** o `SUB_PED` tenta aprová-lo,
    - **Então** o sistema recusa com `HTTP 409 — APROVAÇÃO DE ATRIBUIÇÃO PRÓPRIA NÃO PERMITIDA` (`RN-16.5`) e o pedido fica a aguardar a aprovação do `DIR_GERAL`.
  - **Cenário 3 (Bloqueio — Cadastro incompleto):**
    - **Dado** um cadastro sem N.º do BI,
    - **Quando** o `CHEFE_SEC_GER` tenta pedir a conta,
    - **Então** o sistema recusa com `HTTP 422 — CADASTRO INCOMPLETO (BI EM FALTA)` e nenhuma conta é criada.
- **Pós-condições e Efeitos Colaterais:** Linhas em `usuarios_sistema` e `atribuicoes_cargo`; eventos em `audit_logs`.

---

### `US-CTA-02`: Ativar a conta com código presencial e definir a palavra-passe
- **História:** *Como* **funcionário com conta aprovada**, *quero* **ativar a conta com o código que recebi em mão e escolher a minha palavra-passe**, *para* **entrar no SGE sem que ninguém mais conheça a minha credencial**.
- **Rastreabilidade:** `RN-16.6`, `RN-16.11`, `RN-16.12`, `RN-16.16` | Fluxo C14-A.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Conta `PENDENTE_ATIVACAO` com pelo menos uma atribuição aprovada; Código de Acesso Presencial emitido.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** o código presencial emitido hoje às `08h10` para *Mateus Kiala*,
    - **Quando** às `09h00` ele introduz o código e a frase-passe `rio dande ao fim da tarde`,
    - **Então** a conta passa a `ATIVA`, o código fica `USADO` e grava-se `CONTA_ATIVADA`.
  - **Cenário 2 (Bloqueio — Palavra-passe fraca):**
    - **Dado** o mesmo código válido,
    - **Quando** ele escolhe `123456789`,
    - **Então** o sistema recusa com a mensagem *"Escolha uma palavra-passe com pelo menos 10 caracteres que não seja comum nem contenha os seus dados"* e a conta continua `PENDENTE_ATIVACAO`.
  - **Cenário 3 (Bloqueio — Código expirado):**
    - **Dado** um código emitido há 25 h (validade proposta de 24 h),
    - **Quando** o titular o introduz,
    - **Então** o sistema recusa com `HTTP 410 — CÓDIGO EXPIRADO` e indica que deve pedir novo código na Secretaria Geral.
- **Pós-condições e Efeitos Colaterais:** `usuarios_sistema.estado_conta = ATIVA`; `codigos_acesso_presencial.estado = USADO`.

---

### `US-CTA-03`: Acumular cargos com escopo (`PROF` + `DIR_TURMA`)
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **nomear um professor como Director de Turma sem lhe tirar o cargo de professor**, *para* **que ele lance notas nas suas disciplinas e justifique faltas apenas na turma que dirige**.
- **Rastreabilidade:** `RN-16.3`, `RN-16.5` | `RN-03`, `RN-04` | `MOD-GOV-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Conta `ATIVA` com atribuição `PROF`; turma `GE10A-M` criada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — União de permissões limitada ao escopo):**
    - **Dado** que a professora *Esperança Nzinga* leciona Matemática na `GE10A-M` e na `CG11B-T`,
    - **Quando** o `SUB_PED` executa `NomearDirectorTurma` da `GE10A-M` para ela,
    - **Então** o sistema cria a atribuição `DIR_TURMA` (escopo `TURMA = GE10A-M`, `origem = NOMEACAO`), ela passa a justificar faltas de qualquer disciplina da `GE10A-M`, continua a lançar notas de Matemática nas duas turmas, e **não** consegue justificar faltas na `CG11B-T` (`HTTP 403`).
  - **Cenário 2 (Bloqueio — Cargos incompatíveis):**
    - **Dado** que a mesma professora tem a atribuição `PROF` ativa,
    - **Quando** o `CHEFE_SEC_GER` propõe para ela a atribuição `OP_TES` e o `SUB_ADM` tenta aprovar,
    - **Então** o sistema recusa com `HTTP 409 — CARGOS INCOMPATÍVEIS (OP_TES × PROF — DOC-01 §2)`.
  - **Cenário 3 (Sucesso — Substituição do Director de Turma):**
    - **Dado** que *Esperança Nzinga* é `DIR_TURMA` da `GE10A-M` desde `15/09/2026`,
    - **Quando** o `SUB_PED` nomeia outro docente em `10/02/2027`,
    - **Então** a atribuição dela fica `TERMINADA` com `data_fim = 10/02/2027`, a nova fica `ATIVA`, e as justificações que ela fez continuam a mostrar o nome dela como autora.
- **Pós-condições e Efeitos Colaterais:** `atribuicoes_cargo` com o histórico completo; `turmas.director_turma` atualizado.

---

### `US-CTA-04`: Mudar de cargo sem perder histórico nem deixar dados no dispositivo
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **terminar uma alocação ou um cargo e atribuir outro**, *para* **que o acesso acompanhe a função real da pessoa a cada momento**.
- **Rastreabilidade:** `RN-16.3`, `RN-16.13`, `RN-16.15` | `RN-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Conta `ATIVA` com dispositivo autorizado que guarda em cache a Mini-Pauta de Física da `GE10A-M`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Fim da alocação com fila por sincronizar):**
    - **Dado** que o professor tem 3 operações de Física da `GE10A-M` por sincronizar,
    - **Quando** o `SUB_PED` termina a alocação dele nessa disciplina (`RN-04`) e o dispositivo volta a ter rede,
    - **Então** as 3 operações sobem primeiro (e, como a alocação terminou, entram em `conflitos_sincronizacao` com o motivo `ALOCACAO_DOCENTE_ENCERRADA`), e só depois a Mini-Pauta de Física da `GE10A-M` é apagada do dispositivo.
  - **Cenário 2 (Bloqueio — Efeito imediato no servidor):**
    - **Dado** uma sessão aberta no computador da sala de professores,
    - **Quando** a alocação termina,
    - **Então** o pedido seguinte desse professor à Mini-Pauta de Física da `GE10A-M` recebe `HTTP 403`, sem precisar de terminar a sessão.

---

### `US-CTA-05`: Suspender e reativar uma conta
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **suspender temporariamente a conta de um funcionário em licença ou sob suspeita**, *para* **impedir o acesso sem perder as suas atribuições nem o seu histórico**.
- **Rastreabilidade:** `RN-16.10`, `RN-16.14`, `RN-16.18`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Licença):**
    - **Dado** um `OP_TES` em licença a partir de `01/03/2027`,
    - **Quando** o `SUB_ADM`, após reautenticação, suspende a conta com o motivo *"Licença de maternidade"*,
    - **Então** a conta passa a `SUSPENSA`, as sessões terminam, as atribuições mantêm-se sem `data_fim` e grava-se `CONTA_SUSPENSA`.
  - **Cenário 2 (Exceção — Suspensão de emergência não confirmada):**
    - **Dado** que o `ADMIN_TEC` suspendeu às `10h00` uma conta com acessos suspeitos fora do horário,
    - **Quando** às `10h00` do dia seguinte nenhum `DIR_GERAL` ou `SUB_ADM` confirmou a suspensão,
    - **Então** a conta volta a `ATIVA`, exige autenticação completa no próximo acesso e o `DIR_GERAL` recebe o alerta *"Suspensão de emergência caducada sem decisão"*.

---

### `US-CTA-06`: Desativar a conta na saída do funcionário preservando a autoria
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, *quero* **registar a saída de um funcionário e que o sistema desative a conta e avise quem tem de agir**, *para* **que ninguém mantenha acesso depois de sair e nenhuma pauta ou caixa fique sem responsável**.
- **Rastreabilidade:** `RN-16.7`, `RN-16.8`, `RN-16.9` | `RN-04`, `RN-04.1`, `RN-09.2` | Fluxo C14-B.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Professor que sai a meio do II Trimestre):**
    - **Dado** que o professor *Mateus Kiala* tem alocações ativas em Matemática na `GE10A-M` e na `GE10B-M`,
    - **Quando** o `CHEFE_SEC_GER` regista `data_saida = 14/01/2027` (hoje) com motivo `FIM_CONTRATO`,
    - **Então** a conta passa a `DESATIVADA`, as atribuições recebem `data_fim = 14/01/2027`, o `SUB_PED` recebe a pendência *"2 Mini-Pautas sem titular ativo: Matemática GE10A-M, Matemática GE10B-M"*, e as notas do I Trimestre continuam a mostrar *"Lançado por: Mateus Kiala (conta desativada em 14/01/2027)"*.
  - **Cenário 2 (Exceção — Operador de caixa com sessão aberta):**
    - **Dado** um `OP_TES` com a sessão de caixa do Turno da Manhã `Aberto`,
    - **Quando** a sua saída é registada às `11h00`,
    - **Então** a conta é desativada, a sessão de caixa deixa de aceitar recibos e o `SUB_ADM` recebe a pendência bloqueante *"Fecho administrativo de caixa necessário"* (`RN-13.18`).
  - **Cenário 3 (Bloqueio — Tentativa de apagar a conta):**
    - **Dado** qualquer conta com registos associados,
    - **Quando** alguém tenta eliminá-la,
    - **Então** a operação não existe na interface e a base de dados recusa o `DELETE` (proteção igual à de `audit_logs`).

---

### `US-CTA-07`: Entrar com segundo fator (Direção e Tesouraria)
- **História:** *Como* **Operador de Tesouraria (`OP_TES`)**, *quero* **confirmar a minha identidade com um código da aplicação autenticadora**, *para* **que ninguém emita recibos em meu nome mesmo que descubra a minha palavra-passe**.
- **Rastreabilidade:** `RN-16.12`, `RN-16.13` | PLN-00 §5.3.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Sem internet, só com a LAN):**
    - **Dado** que a ligação à internet da escola está em baixo mas o servidor local responde,
    - **Quando** o `OP_TES` introduz a palavra-passe e o código de 6 dígitos da aplicação autenticadora,
    - **Então** a sessão `BALCAO` abre normalmente (a validação TOTP é feita no servidor local).
  - **Cenário 2 (Bloqueio — Código errado repetido):**
    - **Dado** a palavra-passe correta,
    - **Quando** o código MFA falha 5 vezes seguidas,
    - **Então** a conta passa a `BLOQUEADA_TENTATIVAS` e grava-se `MFA_FALHADO` (×5) e `CONTA_BLOQUEADA` em `eventos_autenticacao`.
  - **Cenário 3 (Exceção — Telemóvel perdido):**
    - **Dado** que o operador perdeu o telemóvel,
    - **Quando** usa um dos 10 códigos de recuperação impressos,
    - **Então** entra, esse código fica inutilizado, o sistema mostra *"Restam 9 códigos de recuperação — registe novo fator com o Administrador Técnico"*.

---

### `US-CTA-08`: Repor o acesso presencialmente, sem email
- **História:** *Como* **professor que esqueceu a palavra-passe e não tem email institucional**, *quero* **repor o acesso na Secretaria Geral apresentando o meu BI**, *para* **voltar a lançar notas no mesmo dia**.
- **Rastreabilidade:** `RN-16.16`, `RN-16.17` | Fluxo C14-C.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Conta não privilegiada):**
    - **Dado** que o professor apresenta o BI ao `CHEFE_SEC_GER` e o número coincide com o cadastro,
    - **Quando** o `CHEFE_SEC_GER` emite o código de reposição,
    - **Então** o código é entregue em mão num talão interno, válido até à mesma hora do dia seguinte; no acesso seguinte o professor define nova palavra-passe, todas as sessões antigas terminam e grava-se `ACESSO_REPOSTO`.
  - **Cenário 2 (Exceção — Conta privilegiada):**
    - **Dado** que quem pede é o `SUB_ADM`,
    - **Quando** o `ADMIN_TEC` tenta emitir o código,
    - **Então** o sistema exige a aprovação do `DIR_GERAL` antes de emitir, e o código só é gerado depois dessa aprovação.
  - **Cenário 3 (Bloqueio — Repor o próprio acesso):**
    - **Dado** o `ADMIN_TEC` autenticado,
    - **Quando** tenta emitir um código de reposição para a sua própria conta,
    - **Então** o sistema recusa com `HTTP 403 — REPOSIÇÃO DO PRÓPRIO ACESSO NÃO PERMITIDA`.

---

### `US-CTA-09`: Lançar notas *offline* com PIN local
- **História:** *Como* **Professor (`PROF`)**, *quero* **desbloquear a Mini-Pauta no meu telemóvel com um PIN quando não há rede no Panguila**, *para* **continuar a lançar notas e faltas sem perder nada até voltar a ter ligação**.
- **Rastreabilidade:** `RN-16.15` | `RN-10` §4 | DOC-05 §1.2 | Fluxo 03.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2` (o lançamento de notas entra na E2; o registo do dispositivo pode entrar na E1).
- **Pré-condições:** Dispositivo autorizado; última autenticação completa há menos de 7 dias.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Dia sem rede):**
    - **Dado** que o professor sincronizou na segunda-feira às `07h40`,
    - **Quando** na quarta-feira, sem rede, introduz o PIN e lança `MTP = 12`, `PP = 11`, `PT = 14` para o aluno n.º 7,
    - **Então** o ecrã mostra `M = 12` (`round_med(37/3) = round_med(12,33)`), a operação fica na fila cifrada com a sua chave de idempotência e sobe quando houver rede.
  - **Cenário 2 (Exceção — PIN errado 5 vezes):**
    - **Dado** 4 operações na fila,
    - **Quando** alguém introduz 5 PIN errados,
    - **Então** a sessão local bloqueia, as 4 operações continuam guardadas, e o desbloqueio só acontece com nome de utilizador e palavra-passe quando houver rede.
  - **Cenário 3 (Exceção — Prazo *offline* esgotado):**
    - **Dado** que a última autenticação completa foi há 8 dias,
    - **Quando** o professor tenta lançar uma nota nova,
    - **Então** o dispositivo mostra *"Ligue-se à rede da escola e entre com a palavra-passe para continuar a lançar"*, mantendo a fila existente intacta.
  - **Cenário 4 (Exceção — Dispositivo revogado por roubo):**
    - **Dado** que o telemóvel foi revogado pelo `ADMIN_TEC`,
    - **Quando** esse dispositivo tenta sincronizar,
    - **Então** o servidor recusa com `HTTP 401 — DISPOSITIVO REVOGADO` e grava o evento em `eventos_autenticacao`.

---

### `US-CTA-10`: Sessões e expiração no balcão da Tesouraria
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **que as sessões dos balcões bloqueiem por inatividade e que cada operador só tenha uma sessão de caixa ativa**, *para* **que ninguém emita recibos num posto deixado aberto**.
- **Rastreabilidade:** `RN-16.13` | `RN-09.2`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Inatividade):**
    - **Dado** um `OP_TES` com sessão `BALCAO` sem atividade desde as `09h00`,
    - **Quando** são `09h15`,
    - **Então** o ecrã fica bloqueado e só desbloqueia com a palavra-passe do mesmo operador.
  - **Cenário 2 (Exceção — Segunda sessão do mesmo operador):**
    - **Dado** que o `OP_TES` tem sessão aberta no posto 1,
    - **Quando** entra no posto 2,
    - **Então** a sessão do posto 1 termina com o motivo `NOVA_SESSAO_BALCAO` e o posto 1 mostra *"Sessão terminada: entrou noutro posto às HH:MM"*.

---

### `US-CTA-11`: Reautenticar antes de uma ação crítica
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **confirmar a minha identidade imediatamente antes de reabrir uma pauta**, *para* **que uma sessão esquecida aberta não permita alterar notas homologadas**.
- **Rastreabilidade:** `RN-16.14` | `MOD-GOV-04` | `US-GOV-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** o despacho `DESP-DG-IPCAG-008/2026` para reabrir Matemática da `GE10A-M` por 24 h,
    - **Quando** o `SUB_PED` introduz a palavra-passe e o código TOTP,
    - **Então** a reabertura é executada e a linha de `audit_logs` regista `reautenticado = Sim`, `metodo = PALAVRA_PASSE_TOTP`.
  - **Cenário 2 (Bloqueio — Código errado):**
    - **Dado** o mesmo pedido,
    - **Quando** o código TOTP está errado,
    - **Então** a pauta continua `Fechado / Homologado`, grava-se `REAUTENTICACAO_FALHADA` e, à 3.ª falha seguida, a sessão termina.

---

### `US-CTA-12`: Administrar contas sem ver notas nem finanças
- **História:** *Como* **Administrador Técnico (`ADMIN_TEC`)**, *quero* **desbloquear contas, terminar sessões e revogar dispositivos**, *para* **resolver problemas de acesso sem ter acesso aos dados pedagógicos e financeiros**.
- **Rastreabilidade:** `RN-16.17`, `RN-16.18`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Desbloqueio):**
    - **Dado** uma conta `BLOQUEADA_TENTATIVAS` pela 2.ª vez no dia,
    - **Quando** o `ADMIN_TEC` a desbloqueia,
    - **Então** a conta passa a `ATIVA`, o titular é notificado no acesso seguinte e grava-se `CONTA_DESBLOQUEADA`.
  - **Cenário 2 (Bloqueio — Abrir uma Mini-Pauta):**
    - **Dado** o `ADMIN_TEC` autenticado,
    - **Quando** pede a Mini-Pauta de qualquer turma,
    - **Então** a API devolve `HTTP 403` e a política RLS não devolve nenhuma linha de `avaliacoes_trimestrais`.
  - **Cenário 3 (Bloqueio — Aprovar um cargo):**
    - **Dado** um pedido de atribuição `OP_PED` pendente,
    - **Quando** o `ADMIN_TEC` tenta aprová-lo,
    - **Então** o sistema recusa com `HTTP 403 — APROVAÇÃO RESERVADA À DIREÇÃO`.

---

### `US-CTA-13`: Auditar contas e rever acessos no início do ano letivo
- **História:** *Como* **Director Geral (`DIR_GERAL`)**, *quero* **consultar a auditoria de contas e confirmar a lista de acessos no início de cada ano letivo**, *para* **garantir que só tem acesso quem tem função atribuída**.
- **Rastreabilidade:** `RN-16.18`, `RN-16.19` | `RN-10` | `C16`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E1` (consulta) / `E4` (revisão anual ligada à passagem de ano).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Lista de revisão):**
    - **Dado** o arranque do Ano Letivo `2027/2028`,
    - **Quando** o `DIR_GERAL` abre a Lista de Revisão de Acessos,
    - **Então** vê todas as contas ativas com cargos, escopos e último acesso, as contas sem acesso há mais de 90 dias destacadas, e pode terminar cada atribuição com motivo (reautenticação obrigatória).
  - **Cenário 2 (Sucesso — Término automático):**
    - **Dado** que o Ano Letivo `2026/2027` foi concluído (`concluirAnoLetivo`),
    - **Quando** o `DIR_GERAL` consulta as atribuições `DIR_TURMA`,
    - **Então** todas as de turmas de `2026/2027` estão `TERMINADA` com o motivo `CONCLUSAO_ANO_LETIVO`.

  - **Cenário 3 (Bloqueio — Terminar uma atribuição sem motivo ou sem reautenticação):**
    - **Dado** a Lista de Revisão de Acessos de `2027/2028` aberta pelo `DIR_GERAL`,
    - **Quando** tenta terminar a atribuição `OP_TES` de um operador sem indicar o motivo, ou falha a reautenticação (`US-CTA-11`),
    - **Então** o sistema recusa, a atribuição continua `ATIVA` e a tentativa fica em `eventos_autenticacao` (`RN-16.14`, `RN-16.18`).

---

### `US-CTA-14` *(E5 — `DEC-003` decidida: portal na E5)*: Ativar a conta de um encarregado de educação no portal
- **História:** *Como* **Encarregado de Educação**, *quero* **ativar a minha conta do portal na Secretaria Pedagógica**, *para* **consultar as notas, faltas e propinas dos meus educandos**.
- **Estado:** a `DEC-003` decidiu o portal para a **E5**. A história fica como referência; o que o portal mostra, os SMS e os consentimentos da APD-11 estão detalhados em `US-COM-07` (`EP-COM`).
- **Rastreabilidade:** [[C14 - Gestao de Contas e Acesso|CAP-C14]] §11 | `C12` | `DEC-003`.
- **Prioridade (proposta):** `Must` *(era `Should` — `DEC-013`, regra 1)* | **Entrega:** `E5`.
- **Critério de aceitação de referência (a detalhar com a `C12`):**
  - **Dado** um encarregado com 2 educandos ativos, **Quando** ativa a conta com o código entregue contra apresentação do BI, **Então** vê apenas os dados desses 2 educandos e nunca os de outros alunos.
  - **Exceção:** **Dado** um código de ativação já usado, **Quando** é introduzido de novo, **Então** o sistema recusa e indica que o encarregado deve voltar à Secretaria Pedagógica.

---

### `US-CTA-15`: Configurar os títulos dos cargos e ligá-los aos papéis do sistema
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`)**, com homologação da **direção da escola (papel `DIR_GERAL`)**, *quero* **registar os títulos reais dos cargos (ex.: *Coordenadora Geral da Comissão de Gestão*) e ligar cada um a um papel do sistema**, *para* **que os documentos saiam com os títulos que a escola usa e que uma mudança de estrutura não obrigue a mexer nas permissões**.
- **Rastreabilidade:** `RN-16.20`, `RN-16.3` | DESC-L1 A4 | REG-12 `Q-028`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1` (os documentos da E1 já levam blocos de assinatura).
- **Pré-condições:** Papéis do sistema carregados; utilizador `CHEFE_SEC_GER` autenticado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Comissão de Gestão):**
    - **Dado** que o `CHEFE_SEC_GER` regista o título *Coordenadora Geral da Comissão de Gestão* ligado ao papel `DIR_GERAL` e o título *Coordenador para a Área Pedagógica* ligado a `SUB_PED`, e a direção homologa,
    - **Quando** a Secretaria Pedagógica emite uma Declaração de Estudos (`DOF-09A`) assinada por quem tem a atribuição com o primeiro título,
    - **Então** o bloco de assinatura mostra *"A Coordenadora Geral da Comissão de Gestão"* e o nome da titular, e nunca o código `DIR_GERAL`.
  - **Cenário 2 (Sucesso — Renomear sem mexer em permissões):**
    - **Dado** o título *Coordenadora Geral da Comissão de Gestão* com uma atribuição ativa,
    - **Quando** a direção homologa a mudança do texto do título para *Directora Geral*,
    - **Então** as permissões da titular não mudam, os documentos emitidos a partir desse momento mostram o novo título, e as declarações já emitidas continuam a mostrar o título antigo (texto congelado no documento).
  - **Cenário 3 (Bloqueio — Mudar o papel de um título em uso):**
    - **Dado** o título *Coordenador para a Área Pedagógica* ligado a `SUB_PED` com uma atribuição ativa,
    - **Quando** alguém tenta ligá-lo ao papel `SUB_ADM`,
    - **Então** o sistema recusa com a mensagem *"Este título tem atribuições ativas. Crie um título novo e transfira as atribuições"*.
  - **Cenário 4 (Bloqueio — Título sem papel):**
    - **Dado** um título registado sem papel ligado,
    - **Quando** o `CHEFE_SEC_GER` o tenta usar num pedido de conta,
    - **Então** o sistema recusa: um título só pode ser atribuído depois de ligado a um papel e homologado.
- **Pós-condições e Efeitos Colaterais:** linhas em `cargos_institucionais`; evento `TITULO_CARGO_HOMOLOGADO` em `audit_logs` (categoria `SEGURANCA_CONTAS`).

---

## ÉPICO 14 (`EP-PNL`): Painéis de Gestão da Direção, Alertas e Estatísticas Impressas

> [!abstract] Origem
> Histórias da [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §7, com os identificadores mantidos. As regras provisórias da nota (C15) passam à família `RN-17` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a nenhum documento novo; rodapés estatísticos do `DOF-04` e do `DOF-05` (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Sobre os exemplos
> Turmas, alunos e contagens são **fictícios**. Os parâmetros usados — fator de faltas `3`, `max_deficiencias_transicao = 2`, propina de `15.000,00 Kz` — são os exemplos e valores por omissão que a própria especificação já indica (DOC-01 `RN-03`, DOC-05 `matrizes_curriculares`, `US-TES-01`); os reais vêm das matrizes oficiais e da tabela em vigor (PLN-00 §5.2).

---

### `US-PNL-01`: Painel do Director Geral e Catálogo de Indicadores
- **História:** *Como* **Director Geral (`DIR_GERAL`)**, *quero* **ver numa só página o estado pedagógico, financeiro e operacional da escola e homologar o catálogo versionado de indicadores de gestão**, *para* **preparar as reuniões de Direção sem pedir relatórios a cada área e garantir que todos os relatórios usam definições matemáticas consistentes**.
- **Rastreabilidade:** `RF-C15-01` | `RN-17.1` a `RN-17.5`, `RN-17.7`, `RN-17.10`, `RN-17.13` | [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §3, §4 | `MOD-GOV-08` | `indicadores_catalogo`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Provisório e oficial):**
    - **Dado** que o I Trimestre de `2026/2027` está homologado e o II Trimestre está aberto,
    - **Quando** o `DIR_GERAL` abre o painel,
    - **Então** vê o aproveitamento do I Trimestre com a etiqueta `OFICIAL`, o do II Trimestre com `PROVISÓRIO` e a percentagem de preenchimento, a receita do mês corrente, a dívida por antiguidade, as pendências da Tesouraria e "Dados até DD/MM/AAAA HH:MM".
  - **Cenário 2 (Exceção — Lançamentos por chegar):**
    - **Dado** 2 conflitos de sincronização pendentes e 1 dispositivo sem sincronizar há 4 dias,
    - **Quando** o painel abre,
    - **Então** os indicadores pedagógicos mostram o aviso *"Podem existir lançamentos ainda não recebidos"*.
  - **Cenário 3 (Exceção — Falha do cálculo diário):**
    - **Dado** que o cálculo das 01h00 falhou,
    - **Quando** o `DIR_GERAL` abre o painel às 08h00,
    - **Então** os indicadores diários mostram o valor do dia anterior com a sua data e um aviso de cálculo em atraso.
  - **Cenário 4 (Sucesso — Catálogo Central de Indicadores Versionado e Homologado — `RF-C15-01`, `RN-17.1`, `RN-17.7`, `RN-17.13`, `MOD-GOV-08`):**
    - **Dado** o catálogo central de indicadores de gestão (`indicadores_catalogo`) gerido no módulo `MOD-GOV-08`,
    - **Quando** a Direção (`DIR_GERAL`) homologa uma versão revista de um indicador (ex.: taxa de aproveitamento `IND-01` ou inadimplência `IND-07`), fixando fórmula de cálculo, fontes de dados, regras de agregação/denominador, limiares de alerta e perfis autorizados,
    - **Então** o sistema congela a versão homologada com histórico de vigência, garante que os instantâneos dos trimestres anteriores mantêm os resultados da fórmula em vigor à data e passa a aplicar a nova métrica prospetivamente nos painéis de gestão.
- **Pós-condições e Efeitos Colaterais:** Linha atualizada em `indicadores_catalogo`; evento `INDICADOR_HOMOLOGADO` registado em `audit_logs`.

---

### `US-PNL-02`: Painel do Subdirector Pedagógico sem dados financeiros
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **acompanhar o aproveitamento, a assiduidade, o risco de retenção, o estado das pautas e os conflitos de sincronização de toda a escola**, *para* **intervir antes dos Conselhos de Notas**.
- **Rastreabilidade:** `RN-17.3`, `RN-17.8`, `RN-17.9` | [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §4.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** o II Trimestre aberto,
    - **Quando** o `SUB_PED` abre o painel,
    - **Então** vê `IND-01` a `IND-17` e `IND-26` para todas as turmas, com detalhe até ao aluno.
  - **Cenário 2 (Bloqueio — Indicador financeiro):**
    - **Dado** o `SUB_PED` autenticado,
    - **Quando** pede o `IND-18` (dívida) por URL direta ou pela API,
    - **Então** recebe `HTTP 403` e a RLS não devolve linhas de `conta_corrente_propinas`.

---

### `US-PNL-03`: Painel do Subdirector Administrativo sem notas
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **ver receita, dívida, bolsas, pendências de caixa e conciliação, ocupação das salas e assiduidade do pessoal**, *para* **gerir a sustentabilidade e o funcionamento da escola**.
- **Rastreabilidade:** `RN-17.3` | `RN-13.1`, `RN-13.11`, `RN-13.12` | [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §4.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Receita e pendências):**
    - **Dado** que em Outubro foram emitidos recibos no valor de `1.200.000,00 Kz` e Notas de Crédito de `15.000,00 Kz` (valores fictícios), e há 1 sessão de caixa por homologar desde ontem,
    - **Quando** o `SUB_ADM` abre o painel,
    - **Então** o `IND-20` mostra `1.185.000,00 Kz` em Outubro, repartidos por canal, e o `IND-23` mostra 1 sessão por homologar com 1 dia.
  - **Cenário 2 (Bloqueio — Aproveitamento por turma):**
    - **Dado** o `SUB_ADM` autenticado,
    - **Quando** pede o `IND-01` da `GE10A-M`,
    - **Então** recebe `HTTP 403`; pode ver apenas os agregados oficiais do `IND-15` (como nos mapas GEPE).

---

### `US-PNL-04`: Painel do Coordenador de Curso
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`)**, *quero* **ver o aproveitamento, as faltas, o risco e os processos da 13ª Classe do meu curso**, *para* **apoiar professores e alunos do curso**.
- **Rastreabilidade:** `RN-17.2` | [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §4.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** o Coordenador do curso de Gestão Empresarial (`TGE`),
    - **Quando** abre o painel,
    - **Então** vê os indicadores das turmas `GE10*`, `GE11*`, `GE12*` e os processos da 13ª Classe de TGE por estado.
  - **Cenário 2 (Bloqueio — Outro curso):**
    - **Dado** o mesmo coordenador,
    - **Quando** pede o `IND-01` de uma turma de Contabilidade e Gestão,
    - **Então** recebe `HTTP 403`.

---

### `US-PNL-05`: Painel do Coordenador de Disciplina
- **História:** *Como* **Coordenador de Disciplina (`COORD_DISC`)**, *quero* **comparar o aproveitamento da minha disciplina entre turmas e ver o estado de lançamento das Mini-Pautas**, *para* **ajustar a dosificação e a Prova Trimestral Unificada**.
- **Rastreabilidade:** `RN-17.2`, `RN-17.3` | `MOD-DOC-DOS`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso):**
    - **Dado** 6 turmas da 10ª Classe com Matemática,
    - **Quando** o Coordenador de Matemática abre o painel no I Trimestre,
    - **Então** vê, por turma, `IND-01` a `IND-03` e `IND-11` (estado e preenchimento).
  - **Cenário 2 (Bloqueio — Faltas):**
    - **Dado** o mesmo coordenador,
    - **Quando** pede o `IND-06` (faltas),
    - **Então** recebe `HTTP 403` (DOC-01 linha 11: `COORD_DISC` sem acesso a faltas).

---

### `US-PNL-06`: Painel do Coordenador de Turno
- **História:** *Como* **Coordenador de Turno (`COORD_TURNO`)**, *quero* **ver as faltas e alertas dos alunos do meu turno, a ocupação das salas e a pontualidade do pessoal**, *para* **agir no dia a dia do turno**.
- **Rastreabilidade:** `RN-17.3`, `RN-17.8`, `RN-17.13` | `IND-16`, `IND-17`, `IND-27` | `RN-12.16`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Ocupação e lotação):**
    - **Dado** que no Turno da Manhã 11 das 12 salas têm turma e a `GE10A-M` tem 47 alunos ativos numa sala com lotação 45,
    - **Quando** o Coordenador do Turno da Manhã abre o painel,
    - **Então** vê ocupação de `91,7%` e a `GE10A-M` destacada com lotação de `104,4%`.
  - **Cenário 2 (Bloqueio — Notas):**
    - **Dado** o mesmo coordenador,
    - **Quando** pede o `IND-01` ou o `IND-28`,
    - **Então** recebe `HTTP 403` (DOC-01 linha 10: `COORD_TURNO` sem acesso a notas).
  - **Cenário 3 (Sucesso — Cumprimento de aulas, com o `C04` integrado):**
    - **Dado** que na semana anterior a `GE10A-M` tinha 30 aulas previstas, 2 canceladas por feriado, 26 lecionadas e 2 não lecionadas sem reposição (contagens fictícias),
    - **Quando** o coordenador abre o `IND-27`,
    - **Então** vê o valor calculado pela fórmula do `RN-12.16` (`26 ÷ 28 = 92,9%`) e a lista das 2 aulas não lecionadas.
  - **Cenário 4 (Exceção — `C04` ainda não integrado):**
    - **Dado** que as tabelas de aulas do `C04` ainda não existem,
    - **Quando** o coordenador abre o painel,
    - **Então** o `IND-05` e o `IND-27` aparecem como *"Indisponível — depende de C04"*, sem valor aproximado.

---

### `US-PNL-07`: Painel do Director de Turma
- **História:** *Como* **Director de Turma (`DIR_TURMA`)**, *quero* **ver o aproveitamento por disciplina, as faltas, os alunos em risco, o estado das Mini-Pautas e os conflitos de sincronização da minha turma**, *para* **preparar o Conselho de Notas e falar com os encarregados a tempo**.
- **Rastreabilidade:** `RN-17.2`, `RN-17.3`, `RN-17.7` | [[C15 - Paineis de Gestao da Direcao|CAP-C15]] §4.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Denominador correto):**
    - **Dado** que a Mini-Pauta de Matemática da `GE10A-M` tem 40 linhas, das quais 1 é de um aluno `TRANSFERIDO` em Outubro, e 27 dos 39 restantes têm `M1 >= 10` com soma de `M1 = 429`,
    - **Quando** o Director de Turma abre o painel,
    - **Então** vê aproveitamento de `69,2%` (27 ÷ 39) e média `11,0` (429 ÷ 39, uma casa decimal, sem `round_med`).
  - **Cenário 2 (Bloqueio — Outra turma e finanças):**
    - **Dado** o Director de Turma da `GE10A-M`,
    - **Quando** pede indicadores da `GE10B-M` ou o estado financeiro de um aluno da sua turma,
    - **Então** recebe `HTTP 403` em ambos os casos.

---

### `US-PNL-08`: Receber o alerta precoce de retenção por faltas
- **História:** *Como* **Director de Turma (`DIR_TURMA`)**, *quero* **ser alertado quando um aluno da minha turma atinge 80% do limite de faltas injustificadas numa disciplina**, *para* **contactar o encarregado antes de o aluno ficar retido**.
- **Rastreabilidade:** `RN-17.8`, `RN-17.12` | `RN-03` | `MOD-DOC-FAL` | Fluxo C15-B.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2` (o alerta é útil desde o primeiro trimestre) / painel na `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Cruzar os 80%):**
    - **Dado** Matemática com `4` tempos semanais e fator `3` → limite de `12` tempos (`RN-03`), e um aluno com `9` tempos de falta injustificada (`75%`),
    - **Quando** chega ao servidor uma nova falta de `1` tempo (total `10` → `83,3%`),
    - **Então** cria-se `ALERTA_FALTAS_80` para o `DIR_TURMA` da turma, o `COORD_TURNO` do turno e o `SUB_PED`.
  - **Cenário 2 (Exceção — Justificação):**
    - **Dado** o alerta acima aberto,
    - **Quando** o Director de Turma justifica `2` tempos (injustificadas passam a `8` → `66,7%`),
    - **Então** o alerta passa a `ARQUIVADO_AUTOMATICAMENTE` com o motivo *"Consumo abaixo do limiar após justificação"*.
  - **Cenário 3 (Sucesso — Retenção):**
    - **Dado** o mesmo aluno com `12` tempos injustificados,
    - **Quando** chega mais `1` tempo (`13 > 12`),
    - **Então** a situação na disciplina passa a `Retido por Faltas` (`RN-03`) e cria-se o alerta `RETENCAO_POR_FALTAS`.

---

### `US-PNL-09`: Ver os alunos em risco de retenção por notas
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **ver a lista de alunos com risco elevado ou moderado de retenção calculado pelas regras de transição**, *para* **organizar apoio pedagógico antes do fim do ano**.
- **Rastreabilidade:** `RN-17.9` | `RN-01`, `RN-02`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Veto LP + nuclear):**
    - **Dado** um aluno da 10ª com `max_deficiencias_transicao = 2`, Língua Portuguesa com `M1 = 9` e Contabilidade Geral (nuclear) com `M1 = 8`, e as restantes disciplinas com `M1 >= 10`,
    - **Quando** o cálculo diário corre,
    - **Então** o aluno aparece em `RISCO_ELEVADO` com o motivo *"Veto Língua Portuguesa + disciplina nuclear (RN-02 Caso 3)"*.
  - **Cenário 2 (Sucesso — Risco moderado):**
    - **Dado** um aluno da 11ª com 2 disciplinas não nucleares com `MP = 8` e `MP = 9`, e Língua Portuguesa com `MP = 12`,
    - **Quando** o cálculo corre,
    - **Então** o aluno aparece em `RISCO_MODERADO` (*"Provável transição com deficiência"*).
  - **Cenário 3 (Exceção — Disciplina com `DISP`):**
    - **Dado** um aluno com `DISP` anual em Educação Física e sem outras negativas,
    - **Quando** o cálculo corre,
    - **Então** Educação Física não é considerada e o aluno não aparece na lista.

---

### `US-PNL-10`: Acompanhar conflitos de sincronização e dispositivos sem sincronizar
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **ver os conflitos de sincronização pendentes e os professores cujos dispositivos não sincronizam há vários dias**, *para* **resolver tudo antes de homologar os Conselhos de Notas**.
- **Rastreabilidade:** `RN-17.5`, `RN-17.12` | DOC-05 §1.2, `conflitos_sincronizacao` | [[C14 - Gestao de Contas e Acesso|RN-16.15]].
- **Prioridade (proposta):** `Must` | **Entrega:** `E3`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Destaque em época de conselhos):**
    - **Dado** o I Trimestre em `Época de Conselhos` e 3 conflitos `PENDENTE` (2 `MINI_PAUTA_FECHADA`, 1 `VERSAO_DIVERGENTE`) com 2 dias,
    - **Quando** o `SUB_PED` abre o painel,
    - **Então** o `IND-13` aparece destacado com os 3 conflitos por turma e motivo, e cada um liga à decisão em `conflitos_sincronizacao`.
  - **Cenário 2 (Exceção — Conflito decidido):**
    - **Dado** um dos conflitos decidido como `DESCARTADO`,
    - **Quando** o painel é atualizado,
    - **Então** o `IND-13` passa a 2 e o alerta correspondente fica `ARQUIVADO_AUTOMATICAMENTE`.
  - **Cenário 3 (Sucesso — Dispositivo parado):**
    - **Dado** um professor cuja última sincronização foi há 4 dias,
    - **Quando** o `SUB_PED` consulta o `IND-14`,
    - **Então** vê o nome do professor e a data da última sincronização (sem ver o conteúdo do dispositivo).

---

### `US-PNL-11`: Ver tendências e exportar indicadores
- **História:** *Como* **Director Geral (`DIR_GERAL`)**, *quero* **comparar indicadores entre trimestres e meses e exportá-los**, *para* **prestar contas à Diocese de Caxito e ao Gabinete Provincial**.
- **Rastreabilidade:** `RN-17.10`, `RN-17.11`.
- **Prioridade (proposta):** `Could` | **Entrega:** `E4`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Instantâneos):**
    - **Dado** os instantâneos oficiais do I e do II Trimestre,
    - **Quando** o `DIR_GERAL` pede a evolução do `IND-01` por curso,
    - **Então** vê os dois valores com a versão da definição usada em cada um.
  - **Cenário 2 (Exceção — Exportação nominal):**
    - **Dado** a lista de alunos em `RISCO_ELEVADO`,
    - **Quando** o `DIR_GERAL` a exporta em CSV,
    - **Então** o sistema exige reautenticação e grava `EXPORTACAO_DADOS_PESSOAIS` em `audit_logs`.

---

### `US-PNL-12`: Calcular e imprimir as estatísticas da Mini-Pauta e da Pauta Geral
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **que a Mini-Pauta e a Pauta Geral saiam com as mesmas estatísticas que a escola já imprime (matriculados, avaliados, aprovados, reprovados, não avaliados; positivas e negativas; transitam, transitam com deficiência, desistentes, não transitam; por género)**, *para* **deixar de as contar à mão e garantir que coincidem com os painéis e com o mapa GEPE**.
- **Rastreabilidade:** `RN-17.1`, `RN-17.7`, `RN-17.14` | `IND-28`, `IND-29` | DESC-L1 A10, A16 | `DOF-04`, `DOF-05`, `DOF-12`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E3` (Mini-Pauta e Pauta Geral do I Trimestre) / `E4` (Pauta Geral anual).
- **Pré-condições:** Mini-Pauta submetida (ou Pauta Geral homologada, para a versão oficial); fórmulas do `RN-01` validadas (achado A1).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Estatística da Mini-Pauta por género):**
    - **Dado** a Mini-Pauta de Matemática da `GE10A-M` no I Trimestre com 40 alunos matriculados no trimestre (22 F, 18 M), dos quais 2 saíram por transferência durante o trimestre sem nota (1 F, 1 M), 26 têm nota `>= 10` (15 F, 11 M) e 12 têm nota `< 10` (6 F, 6 M) (contagens fictícias; 40 é o total da Mini-Pauta real recebida — A16),
    - **Quando** a `CHEFE_SEC_PED` imprime o `DOF-04`,
    - **Então** o rodapé estatístico mostra `MT 40 (F 22 · M 18)`, `AV 38 (F 21 · M 17)`, `AP 26 (F 15 · M 11)`, `RP 12 (F 6 · M 6)`, `NV 2 (F 1 · M 1)`, e o painel do Director de Turma mostra o mesmo, com o nome **"Matriculados"** em vez de `MT`.
  - **Cenário 2 (Sucesso — Estatística da Pauta Geral):**
    - **Dado** a Pauta Geral anual da 10ª A com 37 linhas, com deliberações: 24 transitam, 6 transitam com deficiência, 4 não transitam, 2 desistentes e 1 transferido; e em Contabilidade Geral 34 avaliados, 28 com classificação final `>= 10` e 6 abaixo,
    - **Quando** a Pauta Geral é homologada e impressa (`DOF-05`),
    - **Então** o quadro mostra para Contabilidade Geral `Positivas 28 (82,4%)` e `Negativas 6 (17,6%)`, e o quadro da turma mostra `Transitam 24`, `Transitam com deficiência 6`, `Não transitam 4`, `Desistentes 2`, `Transferidos 1`, todos por género, com soma `37`.
  - **Cenário 3 (Bloqueio — Identidade de controlo falhada):**
    - **Dado** um aluno da mesma Pauta Geral sem deliberação final registada (a soma dá `36` para `37` linhas),
    - **Quando** se tenta imprimir o `DOF-05`,
    - **Então** a impressão é recusada com a mensagem *"A estatística não fecha: 1 aluno sem situação final"* e é criado um alerta para a `CHEFE_SEC_PED`.
  - **Cenário 4 (Exceção — Sem avaliados):**
    - **Dado** uma disciplina sem nenhum aluno avaliado no trimestre,
    - **Quando** a estatística é calculada,
    - **Então** as percentagens aparecem como `—` e nunca como `0%` (`RN-17.7`).
- **Pós-condições e Efeitos Colaterais:** os mesmos valores ficam disponíveis no `IND-28`/`IND-29` e alimentam a secção 3 do `DOF-12`; instantâneo oficial gravado no fecho (`RN-17.10`).

---

## ÉPICO 15 (`EP-PAS`): Encerramento do Ano Letivo e Passagem de Ano

> [!abstract] Origem
> Histórias da [[C16 - Passagem de Ano Letivo|CAP-C16]] §6, com os identificadores mantidos. As regras provisórias da nota (C16) passam à família `RN-18` com o mesmo número de sub-regra (INT-V2 §2.1) e os documentos provisórios a `DOF-25` e `DOF-26` (INT-V2 §2.3). As regras ainda não validadas pela escola estão marcadas 🟡 na nota de origem e no [[01 - Dominio e Regras|DOC-01]] (`DEC-009`).

---

> [!note] Números dos exemplos
> Ilustrativos e coerentes com DOC-01 a DOC-05. A substituir pelos números reais do último ano letivo (plano §5.2: "Números reais: alunos por classe e curso, turmas…").

---

### `US-PAS-01`: Acompanhar o Encerramento do Ano no Painel de Verificação
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **ver num único painel, para o ano em encerramento, quais as verificações cumpridas e quais as pendências**, *para* **fechar o ano sem esquecer nenhuma pauta, matrícula ou conflito por resolver**.
- **Rastreabilidade:** `RN-18.1` a `RN-18.3` | `MOD-PAS-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Ano `2026/2027` `Em Curso` com o III Trimestre por encerrar.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Entrada em encerramento):**
    - **Dado** que o III Trimestre de `2026/2027` está `Encerrado Oficialmente`,
    - **Quando** o `SUB_PED` confirma a passagem do ano a `Em Encerramento`,
    - **Então** o painel apresenta B1–B8 e A1–A5 com contagens (ex.: *"B1: 22 de 24 turmas com Pauta Geral anual homologada"*) e o sistema bloqueia novas matrículas em `2026/2027`.
  - **Cenário 2 (Bloqueio — Pendências):**
    - **Dado** que `CG12A-T` ainda não tem a Pauta Geral anual homologada e existe 1 conflito de sincronização `PENDENTE` em `CG11B-M`,
    - **Quando** o `SUB_PED` pede a homologação do encerramento,
    - **Então** o sistema rejeita com `HTTP 422` e lista *"B1: CG12A-T sem Pauta Geral anual"* e *"B5: 1 conflito pendente em CG11B-M"*, cada um com ligação ao módulo que o resolve.
  - **Cenário 3 (Bloqueio — Abrir o novo ano antes de encerrar o anterior):**
    - **Dado** que `2026/2027` está `Em Encerramento`,
    - **Quando** o `SUB_PED` tenta abrir o I Trimestre de `2027/2028`,
    - **Então** o sistema rejeita com `HTTP 422`: *"O Ano Letivo 2026/2027 ainda não está Encerrado"*.
- **Pós-condições e Efeitos Colaterais:** `anos_letivos` em `EM_ENCERRAMENTO`; evento `ANO_LETIVO_EM_ENCERRAMENTO` em `audit_logs`.

---

### `US-PAS-02`: Gerar em Massa as Propostas de Destino Conforme a Deliberação Final
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **calcular de uma só vez o destino de todos os alunos no ano seguinte, a partir das deliberações homologadas**, *para* **preparar as confirmações de matrícula e as turmas sem redigitação**.
- **Rastreabilidade:** `RN-18.5`, `RN-18.6`, `RN-18.9`, `RN-18.16`, `RN-02` | `MOD-PAS-02`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** ano `Em Encerramento`; Ano `N+1` `Planeado`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Destinos por deliberação):**
    - **Dado** que `PROC-2025-00108` (10ª, **Transita com deficiência**, 2 cadeiras em atraso), `PROC-2025-00215` (11ª, **Não transita** — subtipo `NAO_TRANSITA_VETO_LP_NUCLEAR`, a validar) e `PROC-2023-00031` (13ª, `Defendido e Homologado`) têm as matrículas `Concluída`,
    - **Quando** o `SUB_PED` executa a passagem em simulação,
    - **Então** o sistema cria a proposta *11ª Classe, mesmo curso, com 2 cadeiras em atraso* para `PROC-2025-00108`, a proposta *11ª Classe (repetência)* para `PROC-2025-00215` e nenhuma proposta para `PROC-2023-00031`, cuja situação passa a `Concluiu o Curso`.
  - **Cenário 2 (Bloqueio — 12ª com cadeira em atraso):**
    - **Dado** que `PROC-2024-00077` aprovou todas as disciplinas da 12ª de Contabilidade e Gestão mas mantém *Introdução à Economia* (4 h na 10ª) em `Transitado com Deficiência`,
    - **Quando** a passagem é executada,
    - **Então** a proposta para a 13ª nasce `Bloqueada` com o motivo `CADEIRAS_PENDENTES_13A` e passa a `Apta a Confirmar` sozinha quando *Introdução à Economia* for eliminada em Exame Extraordinário (nota `>= 10`, limiar a validar — `Q-025`).
  - **Cenário 3 (Sucesso — Execução repetida):**
    - **Dado** que a execução 1 gerou 1.050 propostas e 30 já foram convertidas,
    - **Quando** o `SUB_PED` corre a execução 2 depois de uma retificação,
    - **Então** as 1.020 propostas não convertidas passam a `Substituída` e são recriadas; as 30 convertidas ficam intactas.
  - **Cenário 4 (Sucesso — Transferidos e desistentes):**
    - **Dado** que `PROC-2025-00340` tem a matrícula `Transferida (Externa)`,
    - **Quando** a passagem é executada,
    - **Então** não se cria proposta e a situação académica é `Transferido (Saída)`.
- **Pós-condições e Efeitos Colaterais:** `execucoes_passagem_ano` e `propostas_confirmacao_matricula` gravadas; evento `PASSAGEM_SIMULADA`.

---

### `US-PAS-03`: Planear e Criar as Turmas do Ano Seguinte
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **ver a previsão de alunos por curso, classe e turno e criar as turmas do ano seguinte dentro das salas disponíveis**, *para* **receber as confirmações e as novas matrículas sem sobrelotação nem choques de sala**.
- **Rastreabilidade:** `RN-18.7`, `RN-18.8` | `US-GOV-03`, `MOD-PAS-03`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** propostas geradas; vagas de admissão de `N+1` configuradas.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Previsão e criação):**
    - **Dado** que, para *Contabilidade e Gestão — 11ª — Manhã*, há `78` propostas de transição, `6` repetentes e uma reserva de `4` lugares para transferências, com lotação de `45` (máximo dos modelos reais — DESC-L1 A16),
    - **Quando** o `CHEFE_SEC_PED` abre o plano,
    - **Então** o sistema sugere $\lceil 88 / 45 \rceil = 2$ turmas (`CG11A-M`, `CG11B-M`, com ligação às turmas de origem `CG10A-M` e `CG10B-M`), cria-as com as Mini-Pautas da matriz real da 11ª de Contabilidade e Gestão (10 disciplinas, 32 h — DESC-L1 A5) ativa em `2027/2028` e `lista_chamada_congelada = FALSE`.
  - **Cenário 2 (Bloqueio — Salas esgotadas no turno):**
    - **Dado** que já existem 12 turmas no Turno da Manhã de `2027/2028`, uma por sala,
    - **Quando** o `CHEFE_SEC_PED` tenta criar a 13ª turma da Manhã,
    - **Então** o sistema rejeita com `HTTP 409` (*"Não há sala livre no Turno da Manhã"*, regra `UNIQUE(Ano Letivo + Turno + Sala Física)`) e mostra o saldo de salas no Turno da Tarde.
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um `OP_PED`,
    - **Quando** tenta criar turmas de `N+1`,
    - **Então** a API rejeita com `HTTP 403` (linha 3 da matriz RBAC do DOC-01).
- **Pós-condições e Efeitos Colaterais:** turmas de `N+1` em `turmas`, com `turma_origem`; Mini-Pautas em `turma_disciplinas`.

---

### `US-PAS-04`: Decidir a Renovação de Bolsas e Benefícios para o Ano Seguinte
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)** com homologação do **Director Geral (`DIR_GERAL`)**, *quero* **decidir para cada benefício ativo se é renovado, alterado ou terminado, vendo o resultado escolar do aluno**, *para* **que as propinas do ano seguinte nasçam com o valor líquido correto (`RN-07`)**.
- **Rastreabilidade:** `RN-18.11`, `RN-07` | `US-TES-02`, `MOD-PAS-04`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** propostas de renovação geradas pela passagem.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Renovação antes da confirmação):**
    - **Dado** que `PROC-2025-00108` tem `BOLSA_50` em `2026/2027` e a propina de `2027/2028` é `15.000,00 Kz`,
    - **Quando** o `SUB_ADM` propõe a renovação e o `DIR_GERAL` homologa antes da confirmação,
    - **Então** ao confirmar a matrícula as prestações de `2027/2028` nascem com `Valor Líquido = 15.000,00 − 7.500,00 = 7.500,00 Kz`.
  - **Cenário 2 (Sucesso — Desconto de irmãos recalculado):**
    - **Dado** que dois irmãos tinham `DESCONTO_IRMAOS` e um deles concluiu o curso em `2026/2027`,
    - **Quando** o outro confirma a matrícula em `2027/2028`,
    - **Então** o desconto não é aplicado (já não há 2 irmãos ativos) e o `OP_PED` vê o aviso para informar o encarregado.
  - **Cenário 3 (Sucesso — Sem decisão a tempo):**
    - **Dado** que a renovação da bolsa de `PROC-2025-00215` não foi decidida,
    - **Quando** a matrícula é confirmada,
    - **Então** as prestações nascem pelo valor bruto e, se a bolsa for homologada mais tarde, só as prestações `A Vencer` são recalculadas (`RN-07.2`).
  - **Cenário 4 (Segurança RBAC):**
    - **Dado** um `OP_TES`,
    - **Quando** tenta renovar um benefício,
    - **Então** a API rejeita com `HTTP 403`.
- **Pós-condições e Efeitos Colaterais:** `propostas_renovacao_beneficio` decididas; `beneficios_bolsas_matricula` de `N+1` criados na conversão, com `renovado_de_beneficio`; evento `BENEFICIO_RENOVADO`.

---

### `US-PAS-05`: Homologar o Encerramento do Ano e Ativar o Modo Só de Leitura
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** e **Director Geral (`DIR_GERAL`)**, *queremos* **homologar o encerramento do ano quando todas as verificações estão cumpridas**, *para* **proteger os dados do ano contra alterações e libertar a abertura do ano seguinte**.
- **Rastreabilidade:** `RN-18.3`, `RN-18.12`, `RN-18.15`, `RN-18.16` | `MOD-PAS-01`, `DOF-25`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** ano `Em Encerramento`; bloqueantes B1–B8 cumpridos.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Encerramento):**
    - **Dado** que B1–B8 estão cumpridos para `2026/2027`,
    - **Quando** o `SUB_PED` submete e o `DIR_GERAL` homologa,
    - **Então** o ano passa a `Encerrado`, a execução da passagem fica definitiva, é emitido o `DOF-25` e grava-se `ANO_LETIVO_ENCERRADO` em `audit_logs`.
  - **Cenário 2 (Bloqueio — Alteração de nota no ano encerrado):**
    - **Dado** que `2026/2027` está `Encerrado`,
    - **Quando** um `PROF` ou o `CHEFE_SEC_PED` tenta alterar uma falta ou uma nota desse ano,
    - **Então** o sistema rejeita com `HTTP 409`: *"Ano Letivo 2026/2027 encerrado (só leitura); use a reabertura auditada da Direção"*.
  - **Cenário 3 (Sucesso — Exceção da Tesouraria):**
    - **Dado** que `PROC-2025-00215` tem a propina de *Junho/2027* `Em Atraso (com Multa)` e o ano está `Encerrado`,
    - **Quando** o `OP_TES` regista o borderô e liquida essa prestação,
    - **Então** o recibo é emitido, a prestação passa a `Paga` e a proposta de confirmação do aluno desbloqueia.
  - **Cenário 4 (Sucesso — Exceção documental):**
    - **Dado** o ano `Encerrado`,
    - **Quando** o `OP_PED` emite uma Declaração com Notas (`DOF-09B`) com dados de `2026/2027` e o semáforo financeiro está verde,
    - **Então** o documento é emitido normalmente (Fluxo 08).
- **Pós-condições e Efeitos Colaterais:** `encerramentos_ano_letivo` homologado; `anos_letivos` `ENCERRADO`.

---

### `US-PAS-06`: Converter a Proposta numa Confirmação de Matrícula
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **abrir a proposta do aluno já preenchida (classe, curso, turno, turma sugerida, cadeiras em atraso, situação financeira e bolsa) e convertê-la em Confirmação de Matrícula**, *para* **atender cada encarregado em poucos minutos na época de matrículas**.
- **Rastreabilidade:** `RN-18.6`, `RN-18.8`, `RN-18.10` | `US-MAT-02`, Fluxo 02 Cenário B, `MOD-PED-MAT`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** proposta `Apta a Confirmar`; Ano `N+1` `Planeado`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Conversão):**
    - **Dado** a proposta de `PROC-2025-00108` para `CG11A-M` (`2027/2028`), com 2 cadeiras em atraso da 10ª,
    - **Quando** o `OP_PED` confirma,
    - **Então** é criada a matrícula `Pendente (Aguardando Pagamento Inicial)` com `num_processo = PROC-2025-00108`, `tipo_ingresso = CONFIRMACAO_INTERNA` e o N.º de Ordem provisório alfabético na turma; o Boletim de Confirmação recebe o `N.º 0137/2027-2028` *(ilustrativo)* e vem pré-preenchido com a classe, turma, sala e curso de `2026/2027` e as 2 cadeiras em atraso (DESC-L1 A12); a proposta passa a `Convertida em Matrícula`.
  - **Cenário 2 (Bloqueio — Dívida do ano anterior):**
    - **Dado** que `PROC-2025-00215` tem a propina de *Junho/2027* em atraso,
    - **Quando** o `OP_PED` tenta confirmar,
    - **Então** o sistema rejeita com `HTTP 403` (*"Pendência Financeira"* — `RN-08`) e mostra o código da pendência para a Tesouraria.
  - **Cenário 3 (Bloqueio — Turma cheia):**
    - **Dado** que `CG11A-M` já tem `45` matrículas,
    - **Quando** o `OP_PED` confirma para essa turma,
    - **Então** o sistema propõe `CG11B-M` (Fluxo 02, E2.4).
  - **Cenário 4 (Sucesso com autorização — Depois do prazo):**
    - **Dado** uma proposta `Não Confirmada` por prazo expirado e vaga disponível,
    - **Quando** o `CHEFE_SEC_PED` autoriza a confirmação tardia,
    - **Então** é criada nova proposta `Apta a Confirmar` e o ato fica registado em `audit_logs`.
  - **Cenário 5 (Sucesso — Modo `AUTOMATICA`):**
    - **Dado** que o Ano Letivo `2027/2028` está parametrizado com o modo de confirmação `AUTOMATICA` e o bloqueio por dívida desligado (`Q-LEG-05`),
    - **Quando** o `SUB_PED` e o `DIR_GERAL` homologam o encerramento de `2026/2027`,
    - **Então** cada proposta `Apta a Confirmar` dá origem a uma matrícula `Pendente` com o número anual do boletim, sem atendimento ao balcão; as matrículas `Pendente` por pagar no fim do prazo (proposta: 60 dias após o início do ano — `COR-LEG-15`, a validar) passam a `Anulada / Desistente`.
- **Pós-condições e Efeitos Colaterais:** `matriculas_anuais` com `proposta_confirmacao` e `matricula_anterior`; situação académica `Ativo`.

---

### `US-PAS-07`: Tratar os Alunos que Saem do Ciclo e Arquivar os Processos
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **ver a situação final de concluintes, transferidos, desistentes e alunos que não confirmaram, e passar os seus processos ao arquivo histórico**, *para* **manter o arquivo físico e digital em ordem sem perder a capacidade de emitir documentos a estes alunos**.
- **Rastreabilidade:** `RN-18.14`, `RN-18.15` | `MOD-PAS-05`, [[C03 - Processo Individual do Aluno]].
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** passagem executada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Concluintes):**
    - **Dado** que `86` alunos da 13ª têm o processo `Defendido e Homologado`,
    - **Quando** o `CHEFE_SEC_PED` abre a lista de saídas do ciclo,
    - **Então** os `86` aparecem com a situação `Concluiu o Curso` e a localização física por preencher; ao registar a localização, o processo passa ao arquivo histórico e continua a permitir emitir o Certificado e o Diploma (`DOF-10`).
  - **Cenário 2 (Sucesso — Não confirmou):**
    - **Dado** que a proposta de `PROC-2025-00412` expirou sem confirmação,
    - **Quando** a tarefa diária corre,
    - **Então** a proposta passa a `Não Confirmada` e o aluno a `Interrompido`, visível na lista de saídas.
  - **Cenário 3 (Bloqueio — Reingresso sem despacho):**
    - **Dado** um aluno `Desistente / Anulado` no ano anterior,
    - **Quando** o `OP_PED` tenta confirmar-lhe matrícula sem despacho da `SUB_PED`,
    - **Então** o sistema rejeita com `HTTP 422`: *"Reingresso exige despacho da Subdireção Pedagógica"*.
- **Pós-condições e Efeitos Colaterais:** `alunos.situacao_academica` atualizada; `DOF-25` com as listas de saídas.

---

### `US-PAS-08`: Retificar uma Deliberação Depois do Encerramento com Análise de Impacto
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)** com o **Director Geral (`DIR_GERAL`)**, *quero* **corrigir uma deliberação de um ano encerrado através da reabertura auditada, vendo o efeito no ano seguinte**, *para* **corrigir erros sem desfazer o encerramento nem mover alunos às escondidas**.
- **Rastreabilidade:** `RN-18.12.2c`, `RN-18.13` | `US-GOV-04`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E4`.
- **Pré-condições:** ano `Encerrado`; despacho da Direção.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Retificação com aluno já matriculado):**
    - **Dado** que `PROC-2025-00215` foi deliberado `NAO_TRANSITA_RETIDO_NOTAS` e já está matriculado na 11ª de `2027/2028`, e um erro de lançamento corrigido muda a deliberação para `TRANSITA_COM_DEFICIENCIA`,
    - **Quando** o `SUB_PED` e o `DIR_GERAL` trancam a pauta retificada,
    - **Então** a proposta é recalculada para a 12ª, a matrícula de `2027/2028` não é movida automaticamente, é criado um alerta crítico para o `CHEFE_SEC_PED` e grava-se `RETIFICACAO_POS_ENCERRAMENTO` com a deliberação antiga e a nova.
  - **Cenário 2 (Bloqueio — Ação isolada):**
    - **Dado** um ano `Encerrado`,
    - **Quando** só o `SUB_PED` (sem o `DIR_GERAL`) tenta reabrir uma pauta desse ano,
    - **Então** o sistema exige a segunda homologação e não abre a pauta.
- **Pós-condições e Efeitos Colaterais:** nova versão da pauta (`versao_pauta + 1`); alerta em aberto; registo em `audit_logs`.

---

## ÉPICO 16 (`EP-MIG`): Migração de Dados, Cargas Históricas, Digitação Assistida e Reconciliação (C17)

> Decidido na [[12 - Registo de Decisoes e Questoes em Aberto#DEC-010 — Integrar os ajustes da migração no modelo de dados|DEC-010]] e operacionalizado na Issue #13.  
> **Capacidade:** C17 ([[10 - Migracao de Dados e Implantacao|MIG-10]]).  
> **Módulo:** `MOD-MIG-01` Consola de Migração de Dados (Workspace 05 — [[04 - Telas e Documentos|DOC-04]] §5).  
> **Perfis RBAC:** Conta técnica de migração (`RN-16.21`), `ADMIN_TEC`, `OP_PED`, `OP_TES`, `CHEFE_SEC_PED`, `CHEFE_SEC_GER`, `SUB_PED`, `SUB_ADM`, `DIR_GERAL`.

---

### `US-MIG-01`: Carregar e Validar Ficheiros Modelo na Área de Preparação
- **História:** *Como* **Conta Técnica de Migração (`RN-16.21`)** sob supervisão do **Administrador Técnico (`ADMIN_TEC`)**, *quero* **carregar os ficheiros modelo de dados históricos (`MIG-F01` a `MIG-F08`) para a área de preparação e executar a validação sintática e semântica com anexo obrigatório da imagem digitalizada da fonte**, *para* **identificar anomalias e incoerências linha a linha antes de qualquer inserção na base de dados de produção**.
- **Rastreabilidade:** `RF-C17-01`, `RF-C17-02`, `RF-C17-03`, `RF-C17-06` | `RN-10`, `RN-16.21` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §4, §5, §6.4, §7.1 | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Autenticação com credencial nominal da conta `TECNICA_MIGRACAO`; formato de ficheiro compatível com os modelos normalizados; ficheiro digitalizado da fonte original em PDF/PNG anexado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Carga e isolamento na área de preparação):**
    - **Dado** um ficheiro `MIG-F01` (Alunos e Encarregados) preenchido e a imagem digitalizada do livro de matrícula anexada,
    - **Quando** a conta técnica submete a carga na consola `MOD-MIG-01`,
    - **Então** os registos são armazenados exclusivamente nas tabelas da área de preparação (`staging`), o estado do lote passa a `CARREGADO_EM_PREPARACAO`, nenhum registo é inserido nas tabelas de produção (`alunos`, `encarregados_educacao`) e o evento é registado em `audit_logs` com hash do ficheiro e utilizador.
  - **Cenário 2 (Deteção de anomalias com ocorrências por linha):**
    - **Dado** um ficheiro de notas com classificações fora da escala [0, 20], datas inválidas ou campos obrigatórios em falta,
    - **Quando** a validação automática é executada contra as regras de domínio (`RN-01` a `RN-10`) e regras de qualidade do MIG-10 §5,
    - **Então** o sistema gera entradas na tabela de ocorrências por linha (`ocorrencias_migracao`), identifica o número da linha, o campo faltoso e o código do erro, marca o lote como `VALIDADO_COM_ERROS` e impede o envio para aprovação até à correção ou justificação formal.
  - **Cenário 3 (Bloqueio — Tentativa de carga sem anexo do documento fonte digitalizado):**
    - **Dado** que a conta técnica tenta submeter um lote de histórico escolar sem anexar a digitalização correspondente da folha de termo ou pauta física,
    - **Quando** aciona o comando de validação,
    - **Então** o sistema rejeita o carregamento com `HTTP 422`: *"Carga bloqueada: é obrigatório anexar a imagem digitalizada da fonte documental (RF-C17-06)"*.
  - **Cenário 4 (Bloqueio de autorização — Tentativa de aprovação direta pela conta técnica):**
    - **Dado** que um lote se encontra na área de preparação com validação concluída,
    - **Quando** o operador com conta `TECNICA_MIGRACAO` tenta acionar a transição para produção,
    - **Então** a operação é bloqueada com `HTTP 403 Forbidden`: a conta técnica apenas carrega e valida; a aprovação exige perfil da Direção (`RN-16.21`).
- **Pós-condições e Efeitos Colaterais:** Dados residentes em `staging`; registo de auditoria com metadados do ficheiro e imagem associada.

---

### `US-MIG-02`: Digitação Assistida em Grelha com Dupla Digitação Cega e Arbitragem
- **História:** *Como* **Operador da Secretaria (`OP_PED` / `OP_TES`)** e **Chefe de Secretaria (`CHEFE_SEC_PED` / `CHEFE_SEC_GER`)**, *quero* **digitar dados de documentos históricos em grelha idêntica ao papel através de dupla digitação cega com comparação automática e arbitragem de divergências**, *para* **transcrever com fidelidade absoluta acervos em papel que não possuem folhas de cálculo originais**.
- **Rastreabilidade:** `RF-C17-04`, `RF-C17-05`, `RF-C17-06` | `RN-10` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §2.2, §7.1 | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Lote de transcrição criado no `MOD-MIG-01` com folha de termo/pauta digitalizada anexada; estrutura curricular e turma pré-carregadas.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Dupla digitação cega coincidente):**
    - **Dado** um termo de exame físico digitalizado,
    - **Quando** o Operador A realiza a primeira digitação na grelha e o Operador B (sem visualização do que A digitou) realiza a segunda digitação dos mesmos dados,
    - **Então** o sistema executa o batimento campo a campo dos dois lançamentos e, havendo 100% de coincidência e batimento com o total de controlo do papel (soma das notas e total de alunos), marca a grelha como `DIGITACAO_CONCILIADA_APTA` e disponibiliza para conferência de chefia.
  - **Cenário 2 (Divergência e arbitragem qualificada por terceiro):**
    - **Dado** que na disciplina de Matemática o Operador A digitou `14` e o Operador B digitou `11`,
    - **Quando** o batimento automático corre ao submeter a segunda digitação,
    - **Então** o sistema sinaliza a célula divergente a vermelho, bloqueia o lote e encaminha a linha para a fila de arbitragem do `CHEFE_SEC_PED`, que visualiza lado a lado as duas digitações e a imagem do termo original para fixar o valor correto (`14`) com registo nominal do árbitro.
  - **Cenário 3 (Bloqueio — Segregação de funções na digitação):**
    - **Dado** que o Operador A concluiu a primeira digitação de um termo ou pauta,
    - **Quando** tenta abrir a segunda digitação cega do mesmo documento,
    - **Então** o sistema impede o acesso com aviso: *"A segunda digitação cega exige um operador diferente para garantia de integridade (RF-C17-05)"*.
- **Pós-condições e Efeitos Colaterais:** Lote consolidado na área de preparação com histórico das versões digitadas e log da arbitragem.

---

### `US-MIG-03`: Execução Idempotente, Cargas Delta e Deteção/Fusão Controlada de Duplicados
- **História:** *Como* **Conta Técnica de Migração (`RN-16.21`)** e **Chefe de Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **executar recargas de ficheiros de forma idempotente por chave natural, suportar cargas delta e resolver duplicados através de fusão assistida e auditada**, *para* **evitar multiplicação de registos do mesmo aluno ou encarregado entre diferentes anos letivos migrados**.
- **Rastreabilidade:** `RF-C17-07`, `RF-C17-08` | `RN-05`, `RN-10` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §3.1, §5.2; [[C03 - Processo Individual do Aluno|CAP-C03]] §1.3 | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Definição das chaves naturais únicas (N.º de Processo, N.º de BI, Nome Completo + Data de Nascimento + Filiação); lote carregado na área de preparação.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Idempotência em recarga de ficheiro integral ou delta):**
    - **Dado** que um lote do ano letivo 2024/2025 já foi parcialmente ou totalmente carregado,
    - **Quando** a conta técnica executa uma recarga do ficheiro atualizado contendo registos existentes e 5 novas linhas (carga delta),
    - **Então** o sistema identifica as chaves já existentes sem criar registos duplicados, atualiza campos que tenham sofrido retificação controlada e insere unicamente as 5 novas linhas, mantendo a consistência referencial.
  - **Cenário 2 (Deteção e sugestão de fusão de duplicados potenciais):**
    - **Dado** um aluno carregado como `"António Manuel da Silva"` (Processo P-102, nascido a 12/03/2006) e outro no histórico de 2023 como `"António M. da Silva"` (Processo P-540, mesma filiação e data),
    - **Quando** o motor de validação da migração executa a verificação de duplicados,
    - **Então** assinala suspeita de duplicidade no relatório de ocorrências e abre a tela de fusão assistida para o `CHEFE_SEC_PED`, permitindo escolher o processo canónico, unificar os registos escolares e manter o número antigo como alias de busca histórica.
  - **Cenário 3 (Bloqueio — Tentativa de fusão por utilizador sem privilégio):**
    - **Dado** um caso de duplicados pendente na consola `MOD-MIG-01`,
    - **Quando** um utilizador com perfil `OP_PED` ou conta técnica tenta executar a fusão,
    - **Então** o sistema nega a operação com `HTTP 403`: fusão de identidades exige aprovação do Chefe de Secretaria Pedagógica com despacho fundamentado.
- **Pós-condições e Efeitos Colaterais:** Mapeamento de duplicados registado em `audit_logs`; integridade de histórico e chave primária preservadas.

---

### `US-MIG-04`: Recálculo de Médias, Deliberações e Classificação Final (`MFC`) com Sinalização de Discrepâncias
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **executar o recálculo automatizado das médias trimestrais, anuais, da `MFC` e das deliberações de transição/conclusão segundo os algoritmos oficiais do SGE, confrontando com os livros em papel**, *para* **sinalizar e auditar discrepâncias aritméticas ou normativas herdadas do passado sem alterar silenciosamente o histórico jurídico**.
- **Rastreabilidade:** `RF-C17-09` | `RN-01`, `RN-02`, `RN-06` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §6; `DEC-009` | 🟡 PC-E2 · `Q-025` | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Lote de notas e classificações carregado e conciliado na área de preparação; matriz curricular histórica do plano de estudos associada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Coincidência integral de cálculo e deliberação):**
    - **Dado** um conjunto de classificações de 10ª, 11ª e 12ª classes de uma turma histórica,
    - **Quando** o motor do SGE recalcula as médias por disciplina, as médias anuais e a deliberação de transição segundo as regras vigentes na respetiva época,
    - **Então** os resultados coincidem a 100% com o averbado no livro de termos em papel e os registos são marcados como `CALCULO_VERIFICADO_CONFORME`.
  - **Cenário 2 (Discrepância detetada — Alerta e preservação do averbamento oficial):**
    - **Dado** que no termo original em papel de 2021 consta *"Aprovado com 10 valores"* mas o recálculo aritmético exato das notas parcelares resulta em `9.4` (Não Transita / Recurso),
    - **Quando** o motor de recálculo processa a ficha do aluno,
    - **Então** o sistema marca a linha com alerta crítico `DISCREPANCIA_CALCULO_HISTORICO`, exibe o valor calculado e o valor averbado no papel, e exige que o `SUB_PED` despache se mantém o valor histórico formal (juridicamente soberano) com anotação explicativa obrigatória ou se instaura averiguação pedagógica.
  - **Cenário 3 (Tratamento de regimes de transição e disciplinas extintas):**
    - **Dado** um aluno proveniente de currículo técnico antigo com disciplina extinta ou sem equivalência direta,
    - **Quando** o sistema recalcula a `MFC` (13ª Classe),
    - **Então** aplica os pesos da matriz curricular histórica aprovada para o plano do aluno (`RN-06`), sem impor requisitos de disciplinas dos planos novos, e valida a fórmula `MFC = round_med(0.40 * MFD + 0.30 * Estagio + 0.30 * PAP)` ou a fórmula legal aplicável ao ano de conclusão.
- **Pós-condições e Efeitos Colaterais:** `resultados_anuais_disciplina` e `historico_externo_transcricoes` preenchidos com os sinalizadores de conformidade; pendências de discrepância registadas para despacho pedagógico.

---

### `US-MIG-05`: Reconciliação Contábil/Académica, Emissão em Ensaio e Homologação de Lote para Produção
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, **Subdirector Administrativo (`SUB_ADM`)** e **Director Geral (`DIR_GERAL`)**, *quero* **analisar relatórios de reconciliação global, emitir documentos de teste com marca indelével de ensaio e homologar os lotes mediante reautenticação**, *para* **garantir a entrada limpa e controlada dos dados em produção com responsabilização formal e ajuste auditado de saldos**.
- **Rastreabilidade:** `RF-C17-10`, `RF-C17-11`, `RF-C17-12`, `RF-C17-13` | `RN-09`, `RN-10` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §6.1, §6.2, §7.1, §7.2, §7.4, §8.4 | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Lote totalmente validado e sem ocorrências bloqueantes na área de preparação; relatórios de reconciliação contábil e pedagógica emitidos.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Emissão e verificação documental em regime de ensaio):**
    - **Dado** que a comissão de migração pretende testar a consistência antes da viragem definitiva para produção,
    - **Quando** solicita a emissão de pautas ou certificados de teste a partir dos dados da área de preparação,
    - **Então** o sistema gera os documentos com marca de água diagonal indelével *"ENSAIO — SEM VALIDADE"* em todas as páginas, e o QR Code direciona para aviso público de documento de ensaio não reconhecido.
  - **Cenário 2 (Sucesso — Ajuste de saldo devedor histórico migrado mediante despacho):**
    - **Dado** um aluno com saldo devedor de propinas migrado de 45.000 Kz contestado com apresentação de recibo bancário físico não contabilizado na folha antiga,
    - **Quando** o `SUB_ADM` aciona a funcionalidade de ajuste de saldo migrado na consola `MOD-MIG-01` e anexa o despacho fundamentado,
    - **Então** o saldo da conta corrente é retificado, registando-se a operação como `AJUSTE_MIGRACAO_SUB_ADM` e gravando em `audit_logs` os valores anterior, corrigido e número do despacho.
  - **Cenário 3 (Sucesso — Aprovação do lote e migração para produção):**
    - **Dado** que os relatórios de reconciliação de turmas, alunos e propinas foram validados pelo `SUB_PED` e `SUB_ADM`,
    - **Quando** o `SUB_PED` (para dados pedagógicos) e o `SUB_ADM` (para dados financeiros) confirmam a homologação com reautenticação obrigatória (palavra-passe + MFA),
    - **Então** os dados são migrados atomicamente para as tabelas de produção com o campo `origem_registo = 'MIGRADO'`, o lote passa ao estado `MIGRADO_PRODUCAO` e é gerado o Termo de Aceitação para assinatura digital do `DIR_GERAL`.
  - **Cenário 4 (Bloqueio — Violação de reautenticação ou tentativa de aprovação por operador):**
    - **Dado** um utilizador sem perfil de Subdireção ou que falhe a confirmação de reautenticação,
    - **Quando** tenta aprovar um lote de migração,
    - **Então** o sistema aborta a transação com `HTTP 401/403` e nenhum registo é inserido em produção.
- **Pós-condições e Efeitos Colaterais:** Registos integrados em produção com rastreabilidade de migração (`origem_registo = MIGRADO`); emissão do Termo de Aceitação arquivado eletronicamente.

---

### `US-MIG-06`: Bloqueio e Conferência Obrigatória do Histórico Migrado Antes da Certificação
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **bloquear a emissão do primeiro documento de certificação oficial de qualquer aluno com dados migrados até à conferência e validação presencial contra o acervo físico em papel**, *para* **impedir a circulação de certificados ou diplomas baseados em dados importados sem comprovação documental fidedigna**.
- **Rastreabilidade:** `RF-C17-14` | `RN-10.5` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §7.6 | `US-DOC-02` | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Aluno concluinte ou solicitante de certificado com registos com proveniência `origem_registo = MIGRADO` e estado de histórico `MIGRADO_PENDENTE_CONFERENCIA`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Bloqueio automático de emissão de certificado sem conferência física prévia):**
    - **Dado** um aluno que concluiu o curso em ano migrado cujo histórico escolar no SGE se encontra no estado `MIGRADO_PENDENTE_CONFERENCIA`,
    - **Quando** um operador da secretaria (`OP_PED`) tenta emitir o Certificado de Habilitações (`DOF-10A`) ou a Guia de Transferência (`DOF-09C`),
    - **Então** o sistema bloqueia a emissão e emite a notificação impeditiva: *"Emissão bloqueada: o histórico migrado do aluno requer conferência prévia presencial do livro de termos/pautas pelo Chefe da Secretaria Pedagógica (RN-10.5 / RF-C17-14)"*.
  - **Cenário 2 (Sucesso — Conferência física e desbloqueio do processo para certificação):**
    - **Dado** que o `CHEFE_SEC_PED` localizou os termos e pautas físicas no arquivo em papel e conferiu nome, filiação, notas de 10ª a 13ª classe e deliberação final,
    - **Quando** abre o ecrã de conferência do histórico migrado no `MOD-MIG-01`, introduz o livro, folha e termo do arquivo físico e aciona a homologação da conferência,
    - **Então** o estado do histórico passa a `MIGRADO_CONFERIDO`, anexa-se o registo nominal de quem conferiu com carimbo temporal e a emissão do Certificado e pedido de Diploma fica imediatamente desbloqueada para a Secretaria.
- **Pós-condições e Efeitos Colaterais:** Campo `historico_conferido = TRUE` com utilizador e data em `historico_externo_transcricoes` ou nos resultados anuais; desbloqueio das telas de certificação do aluno.

---

### `US-MIG-07`: Migração Individual a Pedido de Antigo Aluno e Desativação da Consola de Migração Massiva
- **História:** *Como* **Director Geral (`DIR_GERAL`)** e **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **encerrar formalmente a consola de migração massiva com desativação da conta técnica e disponibilizar o fluxo restrito de migração individual a pedido de antigos alunos**, *para* **blindar a integridade operacional pós-arranque mantendo a capacidade de atender alunos históricos sob demanda**.
- **Rastreabilidade:** `RF-C17-15`, `RF-C17-16` | `RN-10`, `RN-16.21` | [[10 - Migracao de Dados e Implantacao|MIG-10]] §2.3, §6.4 | `MOD-MIG-01`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Conclusão de todas as vagas de migração massiva; assinatura do Termo de Aceitação Final da migração pelo Director Geral.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Fecho da migração massiva e desativação da conta técnica):**
    - **Dado** que o último lote de dados históricos massivos foi aprovado e o Termo de Aceitação Final foi assinado pelo `DIR_GERAL`,
    - **Quando** o Administrador Técnico comanda o encerramento do processo de migração massiva,
    - **Então** o sistema desativa a consola de importação em lote (`MOD-MIG-01` modo massivo), comuta a conta de migração (`tipo_conta = TECNICA_MIGRACAO`) para `estado_conta = DESATIVADA` com motivo `"Fim da Migração Massiva"` (`RN-16.21`), revoga todas as sessões ativas dessa conta e regista a ação em `audit_logs`.
  - **Cenário 2 (Sucesso — Entrada de antigo aluno por migração individual a pedido):**
    - **Dado** um antigo aluno que concluiu o curso antes da informatização e requer Certificado na Secretaria durante o ano 2028,
    - **Quando** o `CHEFE_SEC_PED` abre o módulo restrito de "Migração Individual a Pedido", digita os dados do processo a partir da ficha do arquivo histórico, anexa a imagem da pauta e submete o pedido,
    - **Então** o sistema cria um lote individual na área de preparação, executa as validações de integridade, exige a aprovação do `SUB_PED` e, após homologação, insere o histórico como `MIGRADO` e desbloqueia a emissão requerida.
  - **Cenário 3 (Bloqueio — Tentativa de reutilizar conta técnica desativada):**
    - **Dado** que a conta técnica de migração foi formalmente desativada após o encerramento da migração massiva,
    - **Quando** qualquer operador tentar autenticar-se com as credenciais da referida conta,
    - **Então** a autenticação é categoricamente rejeitada com aviso de conta extinta, impedindo qualquer acesso à consola de importação.
- **Pós-condições e Efeitos Colaterais:** Consola massiva bloqueada permanentemente; conta técnica desativada; trilha de auditoria completa da transição do ciclo de vida da migração.

---

## ÉPICO 17 (`EP-APD`): Governação da Proteção de Dados, Gestão de Direitos e Políticas de Privacidade (C19)

> Criado em cumprimento da Issue #15 e da [[12 - Registo de Decisoes e Questoes em Aberto#DEC-014 — Critérios de aceitação da operação (C18)|DEC-014]].  
> **Capacidade:** C19 ([[11 - Protecao de Dados (APD)|APD-11]]).  
> **Módulo:** `MOD-GOV-09` Proteção de Dados (Workspace 01 — [[04 - Telas e Documentos|DOC-04]] §5) e `MOD-GER-RH`.  
> **Base Legal:** Lei n.º 22/11 (Proteção de Dados Pessoais), DP n.º 60/21 e Circular n.º 2/2024 da APD.  
> **Perfis RBAC:** `DIR_GERAL`, Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`, perfil técnico/institucional), `SUB_PED`, `SUB_ADM`, `CHEFE_SEC_PED`.

---

### `US-APD-01`: Gestão de Versões dos Avisos de Privacidade e Notificação de Maioridade aos 18 Anos
- **História:** *Como* **Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`)** e **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **gerir as versões dos avisos de privacidade (`AV-01` a `AV-12`), registar a entrega nominal a cada titular e receber a lista diária automatizada de alunos que completam 18 anos**, *para* **garantir o dever de informação (art. 25.º) e formalizar a transição dos consentimentos do representante legal para o próprio aluno maior de idade**.
- **Rastreabilidade:** `RF-C19-01`, `RF-C19-04` | `RN-10` | [[11 - Protecao de Dados (APD)|APD-11]] §3, §4, §7.1 | Lei n.º 22/11 arts. 13.º, 14.º, 25.º | `MOD-GOV-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Módulo `MOD-GOV-09` configurado; catálogo de modelos de avisos (`AV-01` a `AV-12`) carregado; data de nascimento dos alunos registada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Criação de versão de aviso e registo de entrega):**
    - **Dado** que a Direção aprova a versão 2.0 do Aviso de Matrícula (`AV-01`),
    - **Quando** o ponto de contacto publica a nova versão no `MOD-GOV-09` e a Secretaria emite a confirmação de entrega ao encarregado no balcão,
    - **Então** o sistema grava o evento em `avisos_entregues` com o código do aviso, versão, identificador do titular, data/hora e o operador emissor, mantendo o histórico de versões anteriores inalterado em `avisos_privacidade`.
  - **Cenário 2 (Sucesso — Deteção diária de maioridade e notificação de reconfirmação):**
    - **Dado** um aluno que completa 18 anos de idade no dia corrente,
    - **Quando** a rotina diária de verificação de maioridade corre às 06h00,
    - **Então** o aluno é adicionado à lista de trabalho do `MOD-GOV-09` ("Alunos Recém-Maiores"), o sistema gera a pendência `AVISO_MAIORIDADE_PENDENTE`, notifica a Secretaria Pedagógica para entrega presencial do aviso `AV-10` (Maioridade) e disponibiliza o termo de reconfirmação de consentimentos em nome próprio.
  - **Cenário 3 (Efeito da reconfirmação pelo aluno aos 18 anos):**
    - **Dado** um aluno que atingiu os 18 anos e compareceu à Secretaria para formalizar a sua autonomia de dados,
    - **Quando** o `CHEFE_SEC_PED` regista a aceitação do aviso e a opção do aluno sobre os consentimentos facultativos (`CON-01` a `CON-08`),
    - **Então** os consentimentos anteriormente outorgados pelo encarregado de educação são arquivados como `CESSADOS_POR_MAIORIDADE` e os novos consentimentos do titular assumem plena validade jurídica.
- **Pós-condições e Efeitos Colaterais:** `avisos_entregues` e `consentimentos` atualizados; auditoria registada em `audit_logs`.

---

### `US-APD-02`: Gestão de Incidentes de Segurança e Notificação Formal à APD (Circular n.º 2/2024)
- **História:** *Como* **Director Geral (`DIR_GERAL`)** e **Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`)**, *quero* **registar formalmente qualquer incidente de violação de dados pessoais, classificar o seu nível de risco e emitir a minuta de comunicação à APD dentro do prazo regulamentar de 72 horas**, *para* **cumprir a obrigação legal de notificação (art. 30.º da Lei n.º 22/11 e Circular n.º 2/2024 da APD) e mitigar impactos aos titulares**.
- **Rastreabilidade:** `RF-C19-23` | `RN-10` | [[11 - Protecao de Dados (APD)|APD-11]] §8.1; Circular APD 2/2024; Lei n.º 22/11 art. 30.º | `MOD-GOV-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E1`.
- **Pré-condições:** Utilizador autenticado com perfil `DIR_GERAL` ou `PONT_CONT_APD`; ocorrência identificada (ex.: extravio de suporte, acesso indevido, ataque cibernético).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Registo de incidente com contagem de prazo regulamentar):**
    - **Dado** a deteção de um acesso indevido a dados de estudantes no servidor local,
    - **Quando** o ponto de contacto regista o incidente no `MOD-GOV-09` indicando data/hora do conhecimento, categorias de dados afetadas, número estimado de titulares e medidas imediatas de contenção adotadas,
    - **Então** o sistema atribui identificador único `INC-AAAA-NNNN`, inicia o cronómetro regressivo do prazo legal de 72 horas para notificação à APD e emite alerta de severidade alta para o painel da Direção Geral.
  - **Cenário 2 (Sucesso — Geração de minuta normalizada para a APD):**
    - **Dado** um incidente registado e classificado com risco aos direitos e liberdades dos titulares,
    - **Quando** a Direção aciona o comando "Gerar Comunicação Oficial APD",
    - **Então** o sistema compila os dados técnicos e gera o documento em PDF pré-formatado nos moldes do formulário oficial da Circular n.º 2/2024 da APD, com cabeçalho institucional, descrição das medidas corretivas e campo para assinatura do `DIR_GERAL`.
  - **Cenário 3 (Fecho e evidência de comunicação):**
    - **Dado** o protocolo ou recibo de envio do expediente à APD e as recomendações recebidas da autoridade,
    - **Quando** o ponto de contacto anexa a prova de submissão e regista a data e o número de ofício no `MOD-GOV-09`,
    - **Então** o incidente transita para o estado `NOTIFICADO_APD` e o processo é arquivado com todos os registos forenses associados.
- **Pós-condições e Efeitos Colaterais:** Registo gravado em `incidentes_seguranca`; notificação arquivada; cópia retida no dossier de proteção de dados.

---

### `US-APD-03`: Gestão de Pedidos dos Titulares, Prazos de Resposta e Relatório de Acesso em PDF
- **História:** *Como* **Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`)** e **Secretaria Pedagógica**, *quero* **registar pedidos de exercício de direitos dos titulares (acesso, retificação, oposição, cancelamento), monitorizar o prazo legal de 60 dias úteis e exportar o Relatório de Acesso do Titular em PDF com salvaguarda médica**, *para* **atender escrupulosamente os direitos conferidos pelos artigos 26.º a 28.º da Lei n.º 22/11**.
- **Rastreabilidade:** `RF-C19-08`, `RF-C19-09` | `RN-10` | [[11 - Protecao de Dados (APD)|APD-11]] §8.3; Lei n.º 22/11 arts. 26.º, 27.º, 28.º | 🟡 DoR-E2 · `Q-APD-21` | `MOD-GOV-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Pedido formal apresentado pelo titular ou representante legal munido de documento de identificação comprovado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Registo de pedido de acesso e contagem de prazo):**
    - **Dado** um encarregado de educação devidamente legitimado que solicita o acesso integral aos dados escolares e financeiros do seu educando,
    - **Quando** o operador regista o pedido no `MOD-GOV-09` com número de processo, tipo de direito e contacto preferencial,
    - **Então** o sistema emite comprovativo numerado com o prazo limite legal de 60 dias úteis e agenda um alerta preventivo aos 40 dias úteis para a Direção caso o pedido não esteja concluído.
  - **Cenário 2 (Sucesso — Emissão do Relatório de Acesso com mediação de dados clínicos):**
    - **Dado** um pedido de acesso com despacho de deferimento,
    - **Quando** o ponto de contacto gera o "Relatório de Dados do Titular em PDF",
    - **Então** o sistema extrai e estrutura os dados por categoria (identificação, frequência escolar, pautas, pagamentos, comunicações a terceiros), omitindo anotações médicas livres e indicando expressamente que relatórios clínicos detalhados só podem ser entregues através de médico designado pelo titular (art. 26.º n.º 7 da Lei n.º 22/11).
  - **Cenário 3 (Alerta preventivo de estouro de prazo):**
    - **Dado** um pedido de direito que atinge o 40.º dia útil sem parecer ou resposta final concluída,
    - **Quando** a rotina de monitorização corre,
    - **Então** é gerado alerta amarelo crítico na caixa de alertas (`MOD-ALR`) do `DIR_GERAL` e do ponto de contacto para priorização imediata.
- **Pós-condições e Efeitos Colaterais:** Registos em `pedidos_titulares`; arquivo da resposta e comprovativo de entrega ao titular.

---

### `US-APD-04`: Auditoria Reforçada de Acesso a Dados Sensíveis (Saúde e Apoio Social)
- **História:** *Como* **Director Geral (`DIR_GERAL`)** e **Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`)**, *quero* **auditar de forma nominal e segregada todas as consultas, leituras e descarregamentos de dados de saúde e comprovativos socioeconómicos de bolsas**, *para* **garantir a estrita confidencialidade dos dados sensíveis e comprovar a legitimidade funcional de cada acesso (art. 31.º da Lei n.º 22/11)**.
- **Rastreabilidade:** `RF-C19-20` | `RN-10`, `RN-11.12` | [[11 - Protecao de Dados (APD)|APD-11]] §6.2, §7.1 | `MOD-GOV-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E2`.
- **Pré-condições:** Utilizador autenticado a tentar visualizar o compartimento de saúde (`documentos_saude`) ou dados financeiros de carência/bolsa.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Auditoria ativa na leitura de registo de saúde):**
    - **Dado** que o `SUB_PED` abre um atestado médico no compartimento de saúde para validação de dispensa de Educação Física,
    - **Quando** o documento é visualizado ou transferido,
    - **Então** o sistema regista atomicamente em `audit_logs` a categoria `ACESSO_DADO_SENSIVEL_SAUDE`, o ID do funcionário, IP, data/hora precisa, motivo invocado e o ID do documento visualizado, sem registar o conteúdo clínico no log.
  - **Cenário 2 (Sucesso — Auditoria de consulta a processos de bolseiro):**
    - **Dado** que um operador autorizado da Tesouraria consulta os comprovativos socioeconómicos de um candidato a bolsa diocesana,
    - **Quando** o ecrã de detalhe é acedido,
    - **Então** gera-se registo de auditoria qualificado com a tag `ACESSO_DADO_SOCIOECONOMICO`.
  - **Cenário 3 (Relatório de acessos a dados sensíveis para fiscalização):**
    - **Dado** a realização de auditoria interna periódica ou inspeção pela APD,
    - **Quando** o ponto de contacto extrai o mapa de rastreio de dados sensíveis no `MOD-GOV-09`,
    - **Então** o sistema devolve o histórico integral cronológico por utilizador e por titular, destacando acessos fora do horário habitual de serviço.
- **Pós-condições e Efeitos Colaterais:** Inserções invioláveis em `audit_logs`.

---

### `US-APD-05`: Bloqueio de Tratamento de Dados Pessoais em Disputa ou Oposição
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)** e **Subdirector Administrativo (`SUB_ADM`)**, *quero* **comutar temporariamente o estado de dados pessoais de um titular para `BLOQUEADO`**, *para* **suspender o seu processamento operacional em caso de oposição fundada ou contestação de exatidão enquanto decorre a averiguação (art. 28.º da Lei n.º 22/11)**.
- **Rastreabilidade:** `RF-C19-12` | `RN-10` | [[11 - Protecao de Dados (APD)|APD-11]] §8.3; Lei n.º 22/11 art. 28.º | `MOD-GOV-09`.
- **Prioridade (proposta):** `Should` | **Entrega:** `E3`.
- **Pré-condições:** Pedido formal de oposição deferido ou pendência de averiguação sobre identidade/exatidão de dados.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Ativação do bloqueio de dados):**
    - **Dado** um aluno cujo encarregado contestou judicialmente a legitimidade de contactos ou morada registada,
    - **Quando** a chefia aciona o comando "Bloquear Dados Pessoais" no `MOD-GOV-09` anexando o despacho,
    - **Então** o titular passa a `estado_dados = BLOQUEADO`, os contactos deixam de constar nas centrais de avisos por SMS, as listas públicas omitem os dados contestados e é aposto um aviso de bloqueio no processo individual do aluno.
  - **Cenário 2 (Tentativa de tratamento operacional sobre registo bloqueado):**
    - **Dado** um registo no estado `BLOQUEADO`,
    - **Quando** qualquer operador tenta enviar mensagens promocionais ou comunicações não essenciais ao titular,
    - **Então** o sistema impede o envio e exibe: *"Tratamento suspenso: registo encontra-se temporariamente bloqueado por determinação de proteção de dados (art. 28.º)"*.
  - **Cenário 3 (Desbloqueio após resolução da disputa):**
    - **Dado** a conclusão formal do processo de averiguação com confirmação de retificação ou improcedência,
    - **Quando** o `SUB_PED` e o ponto de contacto homologam o desbloqueio,
    - **Então** o registo retorna ao estado ativo regular com gravação da justificativa e autorização em auditoria.
- **Pós-condições e Efeitos Colaterais:** Estado de bloqueio refletido em `alunos` ou `encarregados_educacao`; logs registados.

---

### `US-APD-06`: Motor de Conservação, Purga Automatizada e Relatório de Execução
- **História:** *Como* **Director Geral (`DIR_GERAL`)** e **Ponto de Contacto de Proteção de Dados (`PONT_CONT_APD`)**, *quero* **configurar os prazos de conservação por categoria (`PC-01` a `PC-32`), avaliar propostas mensais automáticas de purga/anonimização e homologar a sua execução com emissão de relatório formal**, *para* **assegurar o cumprimento do princípio da limitação da conservação (art. 11.º da Lei n.º 22/11 e Lei n.º 14/17 de Arquivos) sem destruir património histórico escolar**.
- **Rastreabilidade:** `RF-C19-13` | `RN-10` | [[11 - Protecao de Dados (APD)|APD-11]] §5; Lei n.º 14/17; Lei n.º 22/11 art. 11.º | 🟡 DoR-E4 | `MOD-GOV-09`.
- **Prioridade (proposta):** `Must` | **Entrega:** `E4`.
- **Pré-condições:** Catálogo de políticas de conservação configurado com prazos definitivos (ex.: pautas permanentes `PC-01`, recibos 10 anos `PC-10`, dados de migração intermediários 90 dias `PC-28`, processos disciplinares 5 anos `PC-30`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Proposta mensal automática de lote de expiração):**
    - **Dado** que decorreu mais um mês e certos dados temporários (ex.: ficheiros de migração com mais de 90 dias ou comprovativos de justificação de faltas expirados) atingiram o termo do seu prazo de retenção,
    - **Quando** o motor de conservação corre no primeiro dia do mês,
    - **Então** agrupa os registos elegíveis num lote de execução em `execucoes_conservacao` com estado `PROPOSTO` e apresenta à Direção um resumo estatístico das categorias e volumes a expurgar/anonimizar.
  - **Cenário 2 (Proteção de arquivo histórico escolar permanente):**
    - **Dado** registos de pautas finais, termos de exame, livros de matrícula ou certificados (`PC-01`),
    - **Quando** o motor de conservação analisa as tabelas do acervo escolar permanente,
    - **Então** o sistema classifica categoricamente estes registos como de preservação definitiva por força da Lei n.º 14/17, impedindo qualquer sugestão de eliminação física.
  - **Cenário 3 (Homologação de lote com reautenticação e relatório formal de destruição):**
    - **Dado** um lote de purga validado pelo ponto de contacto contendo logs técnicos com mais de 12 meses,
    - **Quando** o `DIR_GERAL` comanda a execução no `MOD-GOV-09` e confirma com palavra-passe e MFA,
    - **Então** os dados são purgados/anonimizados atomicamente da base de produção, gera-se o Relatório Oficial de Execução de Conservação (com contagens e hash do lote, sem reproduzir o conteúdo apagado) e arquiva-se permanentemente como prova de conformidade perante a APD.
- **Pós-condições e Efeitos Colaterais:** Purga executada; registo em `execucoes_conservacao` e `audit_logs`.

---

### `US-APD-07`: Confidencialidade e Garantias do Titular na Avaliação de Desempenho Docente (Fora das E1–E5 `DEC-016`)
- **História:** *Como* **Professor Avaliado (`PROF`)** e **Subdirector Pedagógico (`SUB_PED`)**, *quero* **aceder à ficha individual de avaliação de desempenho docente sob estrita confidencialidade, com garantia de vista prévia, registo de observações e manifestação formal de concordância ou discordância**, *para* **respeitar os princípios da lealdade e transparência no tratamento de dados laborais (art. 11.º da Lei n.º 22/11 e DP n.º 28/22)**.
- **Rastreabilidade:** `RF-C19-33` | [[11 - Protecao de Dados (APD)|APD-11]] §7.1; DP n.º 28/22; Lei n.º 22/11 | fora da linha de base (`DEC-016`, `Q-036`) | `MOD-GER-RH`.
- **Prioridade (proposta):** `Won't` (fora da linha de base das entregas E1–E5 por `DEC-016`) | **Entrega:** `Fora das E1–E5 (`DEC-016`)`.
- **Pré-condições:** Decisão formal favorável da Comissão de Gestão quanto à inclusão do módulo de avaliação de desempenho no SGE (`Q-036`); processo de avaliação do ano letivo aberto.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Restrição de visibilidade estrita da avaliação):**
    - **Dado** uma ficha de avaliação de desempenho preenchida pelo Coordenador de Disciplina ou Subdirector Pedagógico,
    - **Quando** o registo é guardado no módulo de RH,
    - **Então** a visualização da ficha e das pontuações atribuídas é restrita exclusivamente ao docente avaliado, ao avaliador direto e ao `DIR_GERAL`, ficando expressamente bloqueada a qualquer outro colega, coordenador não envolvido ou operador da secretaria.
  - **Cenário 2 (Sucesso — Vista e contraditório do docente avaliado):**
    - **Dado** um professor notificado da conclusão da sua proposta de avaliação,
    - **Quando** acede à sua área individual no sistema,
    - **Então** pode consultar as classificações parcelares, introduzir observações escritas em campo próprio e assinalar expressamente a sua declaração de concordância ou manifestação de reclamação prévia à homologação final pela Direção.
- **Pós-condições e Efeitos Colaterais:** Registo em `avaliacoes_desempenho` (se ativada); auditoria em `audit_logs`.

---

## Distribuição das Histórias por Entrega (E1–E5)

Contagem pela **primeira entrega** em que cada história tem de estar em produção (linha *Prioridade (proposta) | Entrega* de cada US). Uma história com duas entregas (ex.: `US-PED-06`: E3 trimestral / E4 anual) conta na primeira.

| Épico | E1 | E2 | E3 | E4 | E5 | Fora das E1–E5 | Total |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| `EP-GOV` | 3 | — | 1 | — | — | — | 4 |
| `EP-ADM` | — | — | — | — | 4 | — | 4 |
| `EP-MAT` | 4 | — | — | — | — | — | 4 |
| `EP-PED` | — | 5 | 1 | — | — | — | 6 |
| `EP-DEF-13` | — | — | — | 4 | — | — | 4 |
| `EP-TES` | 5 | — | — | — | — | — | 5 |
| `EP-DOC-AUD` | 1 | 2 | — | 2 | — | — | 5 |
| `EP-PIN` | 8 | — | — | 1 | — | — | 9 |
| `EP-HOR` | — | 11 | — | — | — | — | 11 |
| `EP-COB` | 2 | 12 | — | — | — | 1 | 15 |
| `EP-COM` | — | — | 6 | — | 2 | — | 8 |
| `EP-DIS` | — | 1 | 1 | — | 4 | — | 6 |
| `EP-CTA` | 13 | 1 | — | — | 1 | — | 15 |
| `EP-PNL` | — | 1 | 10 | 1 | — | — | 12 |
| `EP-PAS` | — | — | — | 8 | — | — | 8 |
| `EP-MIG` | 5 | 1 | — | 1 | — | — | 7 |
| `EP-APD` | 2 | 2 | 1 | 1 | — | 1 | 7 |
| **Total** | **43** | **36** | **20** | **18** | **11** | **2** | **130** |

- **MoSCoW proposto:** 104 `Must`, 21 `Should`, 3 `Could`, 2 `Won't` (`US-COB-15` por `DEC-005` e `US-APD-07` por `DEC-016`, fora da linha de base).
- **Faseamento da Central de Avisos (`DEC-015`, 2026-11-09):** `US-COM-01` a `US-COM-06` integradas na **E3** (E3 sobe para 20 US, E5 desce para 11 US); `US-COM-07` e `-08` mantêm-se na **E5** (`DEC-003`).
- **Pontos de controlo da `DEC-009`** que afetam as histórias: **E1** — homologação das decisões (modo de confirmação `US-MAT-02`, bloqueio por dívida, software certificado e regime de IVA da `DEC-002`/`DEC-026`); **E2** — recálculo de pautas (`US-PED-04`, `US-PED-06`, `US-13C-02`, `US-GOV-02`); **E3** — regulamento interno (`EP-DIS`, `US-PED-02` faltas por indisciplina) e modelos de aviso (`EP-COM`).

---

## Alterações da v2.0

### Aplicação da DEC-002 — VER-02 #43 (2026-11-09)

- Nota de leitura e `US-TES-03`/`US-TES-04`: os documentos fiscais vêm do software certificado através do adaptador (`DEC-002` (b), decidida a 2026-11-09, homologação pendente); deixam de dizer "pendente".
- `US-TES-03` Cenário 6 reescrito: contingência do adaptador — recibo escolar provisório + `fila_emissao_fiscal`, sem bloquear o balcão; regularização quando o canal volta.
- Nota de cobertura de `RF-C10-10` atualizada (deixa de ser condicional à `DEC-002` (a)).

### Âmbito: Avaliação de desempenho e expediente geral fora das entregas E1–E5 (2026-11-09 — Issue #23, DEC-016)

- Formalizada a exclusão da avaliação de desempenho do pessoal (`Q-036`) e do expediente geral de correspondência (`Q-039`) das entregas E1–E5, conforme `DEC-016` e `DEC-008` (itens 9 e 10).
- A história `US-APD-07` passa a prioridade `Won't` e entrega `Fora das E1–E5`, e o requisito `RF-C19-33` passa a `W` fora da linha de base.
- Atualizada a distribuição de US: E4 passa de 19 para 18 US; Fora das E1–E5 passa de 1 para 2 US (`US-COB-15` e `US-APD-07`). Total MoSCoW: 104 Must, 21 Should, 3 Could, 2 Won't (130 US no total).
- Fecha a lacuna `L-RF-08` da Matriz de Rastreabilidade.

### Faseamento da Central de Avisos (2026-11-09 — Issue #18, DEC-015)

- Antecipada a central de avisos interna da capacidade C12 (`US-COM-01` a `US-COM-06`) para a **E3** (Fecho do I Trimestre), cobrindo aprovação de modelos (`MOD-COM-01`), avisos de faltas e propinas (`MOD-COM-02`), convocatórias numeradas (`DOF-21`), contactos verificados (`MOD-COM-03`), monitorização de custos de SMS e consentimentos (`RN-14`).
- O canal impresso (`DOF-21`, `DOF-22`) está garantido sem custos adicionais; o SMS opera como canal complementar com teto orçamental e degradação para lista impressa diária.
- O portal web de encarregados e alunos (`US-COM-07` e `US-COM-08`) e a respetiva ativação de contas (`US-CTA-14`) permanecem na **E5** (`DEC-003`), sem expor dados de menores à internet antes de concluída a conformidade APD.
- Atualizada a distribuição de US: E3 passa de 14 para 20 US; E5 passa de 17 para 11 US.
- Fecha a questão `Q-037` (`Q-C12-01`) e a lacuna `L-RF-07` da Matriz de Rastreabilidade.

### Cobertura dos restantes requisitos sem US (2026-11-08 — Issue #17)

- Cobertos integralmente os restantes 7 requisitos funcionais pendentes do catálogo através de cenários específicos nas histórias existentes e explicitação de rastreabilidade:
  - `RF-C03-15` (devolução de originais e arquivo histórico na saída): coberto em `US-PIN-02` (Cenário 5);
  - `RF-C09-11` (registo de certificados na Plataforma Nacional de Certificação): coberto em `US-DOC-02` (Cenários 1 e 5) e `DOF-10`;
  - `RF-C10-10` (contingência via adaptador: o balcão não bloqueia, recibo escolar provisório e fila de emissão — `DEC-002` (b); redefinido na VER-02 #43): coberto em `US-TES-03` (Cenário 6);
  - `RF-C10-24` (distinção de emolumentos pagos por RUPE ao Estado sem documento fiscal da escola): coberto em `US-TES-03` (Cenário 7);
  - `RF-C10-25` (mapas de bolsas e isenções para a Diocese de Caxito): coberto em `US-TES-02` (Cenário 4);
  - `RF-C13-02` (parametrização do regulamento interno, escala do comportamento na E3 e catálogo disciplinar na E5): coberto em `US-DIS-04` (Cenário 4, `MOD-DIS-05`);
  - `RF-C15-01` (catálogo central versionado e homologado de indicadores): coberto em `US-PNL-01` (Cenário 4, `MOD-GOV-08`).
- Atingida a **cobertura total de 100% dos requisitos funcionais da linha de base** por histórias de utilizador (0 RF sem US no DOC-07).
- Fecha a lacuna `L-RF-05` da Matriz de Rastreabilidade.

### Parâmetros institucionais e modelos de documento (2026-11-08 — Issue #16)

- Atualizada a `US-GOV-01` com o **Cenário 6**, cobrindo a parametrização institucional de instalação única (`RF-C01-07`) e completando a herança de modelos de documento com cabeçalhos, rodapés e blocos de assinatura (`RF-C09-07`), em conformidade com a `DEC-001` e `US-CTA-15`.
- Cobertura funcional detalhada: designação oficial (*Instituto Politécnico Católico de Administração e Gestão (IPCAG) N.º 12008 / BGO*) e designação complementar, número da instituição por tipo de documento (12008 / 8009 — 🟡 `Q-027`), NIF institucional, códigos regulamentares de cabeçalho/rodapé (`IPCAG.SG-ACE`, `DEE-PEEP-001-ACE`), rótulos impressos configuráveis ("Período" = Turno, "Cadeira" = Disciplina) e herança em `modelos_documento` (`DOF-01` a `DOF-26`).
- Fecha a lacuna `L-RF-04` da Matriz de Rastreabilidade.

### Épico 17 (EP-APD) — Governação da Proteção de Dados (2026-11-08 — Issue #15)

- Criado o **Épico 17 (`EP-APD`)** com as histórias `US-APD-01` a `US-APD-07`, cobrindo os 9 requisitos funcionais pendentes da capacidade C19 (`RF-C19-01`, `RF-C19-04`, `RF-C19-08`, `RF-C19-09`, `RF-C19-12`, `RF-C19-13`, `RF-C19-20`, `RF-C19-23`, `RF-C19-33`), em conformidade com a Lei n.º 22/11, o DP n.º 60/21 e as orientações da APD (Circular n.º 2/2024).
- Cobertura funcional detalhada: gestão de versões dos avisos de privacidade `AV-01` a `AV-12` e notificação de maioridade aos 18 anos (`US-APD-01`), registo de incidentes de violação de dados e notificação à APD em 72h (`US-APD-02`), gestão dos direitos do titular, prazo de resposta de 60 dias e relatório de acesso filtrado (`US-APD-03`), auditoria reforçada de acessos a dados sensíveis de saúde e bolsas (`US-APD-04`), bloqueio cautelar de dados contestados (`US-APD-05`), motor automático de conservação e purga com relatório formal de destruição e salvaguarda permanente do arquivo histórico (`US-APD-06`), confidencialidade e garantias na avaliação de desempenho docente (`US-APD-07`, condicional à `Q-036`).
- Total do documento atualizado para **17 épicos** e **130 histórias de utilizador** (104 Must, 21 Should, 4 Could, 1 Won't). Distribuição: E1 = 43, E2 = 36, E3 = 14, E4 = 19, E5 = 17, Fora = 1.
- Fecha a lacuna `L-RF-03` da Matriz de Rastreabilidade.

### Épico 16 (EP-MIG) — Migração de Dados (2026-11-08 — Issue #13)

- Criado o **Épico 16 (`EP-MIG`)** com as histórias `US-MIG-01` a `US-MIG-07`, cobrindo integralmente os 16 requisitos funcionais `RF-C17-01` a `RF-C17-16` da capacidade C17 e o módulo `MOD-MIG-01` (Workspace 05 — [[04 - Telas e Documentos|DOC-04]] §5).
- Cobertura funcional detalhada: carga e validação em área de preparação com anexo de fonte digitalizada (`US-MIG-01`), digitação assistida em grelha com dupla digitação cega e arbitragem por chefia (`US-MIG-02`), recarga idempotente, suporte a cargas delta e fusão controlada de duplicados (`US-MIG-03`), recálculo de médias, deliberações e `MFC` com sinalização de discrepâncias históricas (`US-MIG-04`), reconciliação contábil/académica, emissão em regime de ensaio e homologação de lote (`US-MIG-05`), bloqueio e conferência física obrigatória do histórico migrado pré-certificação (`US-MIG-06`), migração individual a pedido de antigo aluno e desativação da consola massiva com encerramento da conta técnica (`US-MIG-07`).
- Total do documento atualizado para **16 épicos** e **123 histórias de utilizador** (99 Must, 20 Should, 3 Could, 1 Won't). Distribuição: E1 = 41, E2 = 34, E3 = 13, E4 = 17, E5 = 17, Fora = 1.
- Fecha a lacuna `L-RF-01` da Matriz de Rastreabilidade.

### Decisão [[12 - Registo de Decisoes e Questoes em Aberto#DEC-013 — Entregas e prioridades|DEC-013]] — entregas e prioridades (2026-11-05)

- Núcleo da C13 antecipado: `US-DIS-01` na E2 e `US-DIS-04` na E3; `EP-DIS` atualizado.
- Prioridade `Must` em `US-CTA-14`, `US-DIS-02` e `US-DIS-06` (regra 1: igual à do RF mais prioritário).
- Distribuição por entrega e contagem MoSCoW recalculadas.


### Decisão [[12 - Registo de Decisoes e Questoes em Aberto#DEC-012 — Alinhar permissões RBAC e RLS|DEC-012]] — permissões (2026-11-05)

- `US-GOV-01`: o `SUB_PED` cria e o `DIR_GERAL` homologa.
- `US-PED-03`: o atestado é carregado pelo `OP_PED`.
- `US-PED-06`: o `SUB_PED` e o `DIR_GERAL` homologam a Pauta Geral.


### Correções da verificação [[00.4 - Relatorio de Verificacao v2.0-rc1|VER-01]] (2026-11-05)

- `RF-P-APD-nn` → `RF-C19-nn` (issue #1).
- Tabelas inexistentes substituídas: `candidaturas_10a`, `conta_corrente_propinas`, `historico_externo_transcricoes`, `exames_extraordinarios`, `tabelas_precos_emolumentos`, `itens_recibo`, `consentimentos` (issue #2).
- Estados alinhados com o DOC-01: Trimestre (`Encerrado Oficialmente`), 13ª Classe (`Em Estágio / Projecto Tecnológico`, `Apto para Defesa`), `Não Transita (Retido)` (issue #3).
- "Nota de Estorno" → "Nota de Crédito"; `MT1` → `M1`; marcas 🟡 em falta; exemplos fiscais uniformizados; auto-aprovação com `HTTP 409` (issue #4).


> [!note] Origem
> Integração decidida na `DEC-009` e coordenada pelo [[00.2 - Mapa de Integracao v2.0|Mapa de Integração (INT-V2)]] §4 (linha DOC-03). O conteúdo substituído fica registado aqui com a sua origem; a versão `1.2` desta nota é a última anterior à integração. Os números das sub-regras novas de `RN-01` (prova de 2.ª chamada) e de `RN-09` (crédito do aluno) são atribuídos no [[01 - Dominio e Regras|DOC-01]]; este documento cita só a regra-mãe.

### 1. Épicos e histórias novas
| Épico | Histórias | Origem |
| :--- | :--- | :--- |
| `EP-PIN` (Épico 08) | `US-PIN-01` a `09` | [[C03 - Processo Individual do Aluno\|CAP-C03]] §6 e §13 |
| `EP-HOR` (Épico 09) | `US-HOR-01` a `11` | [[C04 - Horarios e Distribuicao de Servico Docente\|CAP-C04]] §6 e §13 |
| `EP-COB` (Épico 10) | `US-COB-01` a `15` (`US-COB-15` fora da linha de base) | [[C10 - Cobranca, Relatorios Financeiros e Conciliacao\|CAP-C10]] §6 e §13 |
| `EP-COM` (Épico 11) | `US-COM-01` a `08` — critérios expandidos para o formato BDD completo | [[C12 - Comunicacao com Encarregados e Alunos\|CAP-C12]] §3, §6 e §13 |
| `EP-DIS` (Épico 12) | `US-DIS-01` a `06` — critérios expandidos para o formato BDD completo | [[C13 - Disciplina e Comportamento\|CAP-C13]] §3, §6 e §13 |
| `EP-CTA` (Épico 13) | `US-CTA-01` a `15` | [[C14 - Gestao de Contas e Acesso\|CAP-C14]] §6 e §14 |
| `EP-PNL` (Épico 14) | `US-PNL-01` a `12` | [[C15 - Paineis de Gestao da Direcao\|CAP-C15]] §7 e §14 |
| `EP-PAS` (Épico 15) | `US-PAS-01` a `08` | [[C16 - Passagem de Ano Letivo\|CAP-C16]] §6 e §13 |

Numeração aplicada ao integrar (INT-V2 §2.1 e §2.3): regras provisórias de cada nota → família final, com o mesmo número de sub-regra — C03 → `RN-11`, C04 → `RN-12`, C10 → `RN-13`, C12 → `RN-14`, C13 → `RN-15`, C14 → `RN-16`, C15 → `RN-17`, C16 → `RN-18`; documentos provisórios → C03 `DOF-13`/`14`, C04 `DOF-15`/`16`, C10 `DOF-17` a `20`, C12 `DOF-21`/`22`, C13 `DOF-23`/`24`, C16 `DOF-25`/`26`. Nenhum identificador provisório fica no documento. Os termos fiscais das histórias da C10 passaram a "Nota de Crédito" (`COR-LEG-03`) e as notas parcelares da C14 a `MTP`/`PP`/`PT`. Acrescentaram-se critérios de exceção onde faltavam: `US-PIN-07` (Cenário 4), `US-CTA-04` (Cenário 2 passa a bloqueio), `US-CTA-13` (Cenário 3), `US-COB-15` (critério de referência). Cada história nova tem uma linha *Prioridade (proposta) | Entrega*; as da C10, C14 e C15 mantêm a da nota de origem.

### 2. Histórias existentes corrigidas
| História | O que mudou | Origem |
| :--- | :--- | :--- |
| `US-GOV-01` | Calendário real (Prova Global, extraordinários em maio, recurso em julho) e calendário pelo decreto executivo anual; `nota_minima_por_prova` por omissão **10** (era 0); idade mínima 15 anos no ano da matrícula; idade máxima sem fonte 🟡; **Cenário 5** novo: I Trimestre só abre com o ano anterior `Encerrado` | `COR-LEG-07`, `-08`, `-11`; CAP-C16 §13; DESC-RESP §3 |
| `US-GOV-02` | Área de Formação e Especialidade; os 4 cursos reais (saem Informática de Gestão e Finanças); cargas reais; componente Sócio-Ambiental-Cultural; fonte da matriz; fator de faltas 🟡; 13ª com **Projecto Tecnológico**, Estágio e PAP; **Cenário 4** novo: veto LP + nuclear não se ativa na 12ª | A5–A7; `COR-LEG-13`, `-16`, `-23`, `-28`, `-29` |
| `US-GOV-03` | Formação de turmas atribuída ao `SUB_PED`; "Período" como rótulo; título do Director de Turma configurável; atribuição `DIR_TURMA` com escopo | `COR-LEG-22`; A4, A9; CAP-C14 |
| `US-GOV-04` | Exemplo passa de `NPT`/`MT`/`MFD` a `PT`/`M1`/`CF` | INT-V2 §3.3 |
| `US-ADM-01` | Descrição correta do DE n.º 361/26; idade mínima 15 anos (sem idade máxima); 2ª opção marcada como prática interna 🟡; **Cenário 3** novo (idade) | `COR-LEG-07`, `-10`, `-11` |
| `US-ADM-02`, `US-ADM-03` | Documento fiscal (Fatura-Recibo/Recibo) em vez de "Recibo Oficial"; mínimo por secção 🟡 | `COR-LEG-02`; `Q-LEG-10` |
| `US-ADM-04` | **Mínimo de 10 em cada prova**; desempate pela **menor idade** (saem LP/nuclear e média da 9ª); sai a redução do limiar por despacho; repescagem 🟡; prazos de 72 h / 24 h / 24 h e lista definitiva homologada; cenários novos 2, 4, 5, 6 | `COR-LEG-08`, `-09`, `-10`, `-12` |
| `US-MAT-01` | Documentos conferidos passam pelo processo individual (`US-PIN-02`); boletim com número anual; 10 prestações; **Cenário 3** novo: anulação aos 60 dias 🟡 | CAP-C03 §13; `COR-LEG-15`; A12, A13 |
| `US-MAT-02` | **Confirmação automática** a partir da proposta `Apta a Confirmar` (modo `BALCAO`/`AUTOMATICA`); bloqueio por dívida parametrizável 🟡; perda da confirmação por faltas; prazo de 60 dias e confirmação tardia | `COR-LEG-14`, `-15`; CAP-C16 §13; DESC-RESP R4, R5 |
| `US-MAT-03` | `CA` (ou `MFD` de origem) e `M1`/`M2`; curso real no exemplo | INT-V2 §3.3; A5 |
| `US-MAT-04` | Ordem alfabética pelo nome do BI; 40–45 alunos; **Cenário 4** novo (bloqueio de renumeração) | DESC-RESP R6 |
| `US-PED-01` | Provas unificadas `PT` e `PG` com variantes A (Manhã), B (Tarde) e de 2.ª chamada, com visto do Coordenador Pedagógico; III Trimestre sem `PT`; cenário RBAC | DESC-RESP §1; A1 |
| `US-PED-02` | Faltas **por tempo letivo** a partir da aula do horário publicado; **tempo duplo = 2 faltas**; **tipos de falta** (não comparência / indisciplina); justificação **numerada** aprovada por DT + Coordenador Pedagógico e abatida **em todas as disciplinas**; limite de faltas 🟡; perda da confirmação; cenários 1, 2, 5, 6 novos | A8; DESC-RESP R1, R3; CAP-C04, CAP-C13 §13; `COR-LEG-13`, `-14` |
| `US-PED-03` | Células `DISP` com a nomenclatura `MTP`…`CA` | INT-V2 §3.3 |
| `US-PED-04` | `MTP`/`PP`/`PT` (com `MAC`/`NPP`/`NPT` como rótulos); `M1`; III Trimestre sem `PT` 🟡; **prova de 2.ª chamada** com célula pendente; PIN local | A1, A2; `COR-LEG-26`, `-27`; DESC-RESP §1 |
| `US-PED-05` | `MTP`/`PP`/`PT`; **Cenário 2** novo: choque de horário do professor substituto | CAP-C04 §13 |
| `US-PED-06` | Sai o recurso 40%/60% como valor por omissão; entram **`CF`**, **`PG`** e **`CA = round_med(CF × 0,6 + PG × 0,4)`**, aprovação `CA ≥ 10`, recurso se `CA < 10` e `CF ≥ 7` (fórmula pós-recurso 🟡); veto LP + nuclear só na 10ª/11ª; 12ª sem deficiência; bloqueio por 2.ª chamada e por conflitos de sincronização; comportamento e estatísticas da Pauta Geral | A1, A7, A10; DESC-RESP §1; `COR-LEG-13`, `-26`; CAP-C13, CAP-C15 |
| `US-DEF-01`, `US-DEF-02` | Acordo de pagamento no semáforo; taxa por disciplina e época de maio; RUPE 🟡; livro de Termos de Exame próprio | CAP-C10; DESC-RESP §1, R17; `Q-034` |
| `US-13C-01` | **Projecto Tecnológico** (12ª e 13ª), Estágio de 20 tempos, PAP como defesa do relatório; supervisor na empresa e tutor interno; Coordenador GIVA | A6; `COR-LEG-16`, `-22`, `-28`; DESC-RESP R21 |
| `US-13C-02` | Júri com **representantes dos trabalhadores e dos empregadores**; pré-requisitos reais da defesa; pesos da `MFC` 🟡 sem dupla contagem do estágio; cenários 3 e 4 novos | `COR-LEG-16`, `-17`; DESC-RESP R20, R21; `Q-030` |
| `US-TES-01` | 10 prestações (setembro a junho), vencimento ao dia 10 ou 15, multa em `parametros_cobranca`, emolumentos RUPE 🟡; **Cenário 2** novo | DESC-RESP R9, R15; CAP-C10 |
| `US-TES-02` | Lista nominal de bolseiros diocesanos; **Cenário 3** novo: revogação a meio do ano | DESC-RESP §2; `RN-07` |
| `US-TES-03` | Fatura-Recibo/Recibo e numeração por tipo e ano fiscal; **crédito do aluno** com o excedente do talão; talão com valor a menos não quita; borderô em investigação | `COR-LEG-02`, `-04`; DESC-RESP R10, R14; CAP-C10 |
| `US-TES-04` | **Nota de Estorno → Nota de Crédito** (`NC`) com menção e referência; DP n.º 292/18 → **DP n.º 71/25**; fraude detetada pela conciliação | `COR-LEG-01`, `-03`; CAP-C10 |
| `US-TES-05` | Canal RUPE; conferência pela Secretaria Geral; Nota de Crédito depois do fecho; fecho administrativo | DESC-RESP R13; `RN-09.2`; CAP-C10 |
| `US-DOC-01` | **Requerimento numerado com talão destacável**; prazo de **5 dias úteis**; campos reais da declaração; numeração anual por tipo; boletim retido por dívida; Guia com dívida reescalonada zero; anulação do cartão | A11, A13; DESC-RESP R12, R16, R28; `COR-LEG-20`; CAP-C03, CAP-C10 |
| `US-DOC-02` | **Certificado** (escola) separado do **Diploma** (Ministério — o SGE exporta os dados e o pedido); registo no livro de Certificados (folha e termo 🟡); QR da Plataforma Nacional 🟡 e prazo de 30 dias; cabeçalho real; bloqueio por pendência documental | `COR-LEG-18`, `-19`; A14; DESC-RESP R17, R18; CAP-C03 §13 |
| `US-DOC-03` | QR nacional nos certificados e QR próprio nos restantes; Nota de Crédito | `COR-LEG-19`; DESC-RESP R19 |
| `US-DOC-04` | Faltas dos professores por tempo letivo; N.º de Agente; mapa de efetividade exportado (salários fora); **Cenário 2** novo | DESC-RESP R24; A15; CAP-C04 |
| `US-DOC-05` | Modelo do mapa sem normativo do GEPE 🟡; mesmo cálculo das estatísticas da Pauta Geral; mapa provisório; categoria `SEGURANCA_CONTAS` | `COR-LEG-25`; CAP-C14, CAP-C15 |

### 3. Visão geral e convenções
- Tabela de épicos com as colunas **Capacidade**, **Entrega** e **MoSCoW**; épicos 08–15; total de 15 épicos e 116 histórias; propostas `Q-037` e `Q-038` marcadas como pendentes.
- Linha *Prioridade (proposta) | Entrega* em todas as histórias; secção de distribuição por entrega.
- Títulos dos épicos 01, 03, 04, 05, 06 e 07 atualizados à terminologia da v2.0.
- **Mantidos de propósito**, à espera do [[01 - Dominio e Regras|DOC-01]] e do [[05 - Modelagem de Dados|DOC-05]]: ~~o nome do estado `Em Estágio / Elaboração de PAP`~~ *(resolvido em 2026-11-05: passa a `Em Estágio / Projecto Tecnológico`, como no DOC-01 — VER-01 G3)* e os nomes de tabela `notas_estorno` e `trg_prevent_recibo_mutation`. Os estados `Certificado Emitido` e `Diploma Pedido` (`US-DOC-02`) e `Admitido (2ª Opção — Repescagem)` são os que estas histórias pedem à máquina de estado do DOC-01.

---

> [!tip] Próximo Passo na Arquitetura
> Avance para [[04 - Telas e Documentos]] para consultar a **Arquitetura da Informação dos Workspaces**, os módulos das capacidades novas e a **Anatomia dos Documentos Oficiais `DOF-01` a `DOF-26`**, consulte o [Quadro DOC-03 no FigJam](https://www.figma.com/board/PZgRkbRHrNR6UfehirGDPd) (ainda na v1.2) ou regresse a [[02 - Fluxos de Trabalho]].
