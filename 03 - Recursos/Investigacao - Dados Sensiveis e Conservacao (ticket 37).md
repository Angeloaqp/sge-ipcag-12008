---
title: "Investigação — Dados sensíveis, menores e prazos de conservação (ticket #37)"
aliases:
  - "Investigacao - Dados Sensiveis e Conservacao (ticket 37)"
  - "INV-APD-37"
created: 2026-11-08
status: rascunho
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - investigacao
  - apd
---

# Investigação — Dados sensíveis, menores e prazos de conservação (ticket #37)

> [!abstract] Navegação
> - **Ticket:** [#37](https://github.com/Angeloaqp/sge-ipcag-12008/issues/37) (parte do mapa #11)
> - **Notas que esta investigação estende (sem repetir):** [[11 - Protecao de Dados (APD)]] (APD-11 §1.3 C, D, I, J; §5; §7.3; §9) · [[12.1 - Indice de Questoes em Aberto]] · *Investigação — Enquadramento APD (ticket #36)* (ramo `research/enquadramento-apd`) · *Investigação — Regras Fiscais (ticket #33)* (ramo `research/regras-fiscais`)

> [!important] Natureza deste documento
> É uma **investigação em fontes**, não um parecer jurídico. Cada afirmação indica a fonte e o estado: ✅ **confirmado** (lido no texto citado), 🔶 **inferido** (interpretação nossa), ❌ **não confirmado**. Fontes consultadas a **08/11/2026**. O sítio da APD (apd.ao) continuava **em manutenção** nesta data, por isso **nenhuma orientação ou prática da APD** foi lida. A §5 só aponta implicações; não toma decisões.

---

## 1. Pergunta

| ID | Pergunta |
| :---: | :--- |
| `Q-APD-15` | Atestados médicos: basta o **consentimento escrito** ou é sempre precisa **autorização da APD**? |
| `Q-APD-21` | O acesso aos dados de saúde tem de ser **por intermédio de médico** (art. 26.º)? |
| `Q-APD-16` | Propinas em atraso e semáforo financeiro são **dados de crédito** (art. 16.º)? |
| `Q-APD-17` | Um **borderô fraudulento** ligado a um encarregado é dado sobre **atividades ilícitas** (art. 15.º)? |
| `Q-APD-23` | A **situação socioeconómica** nos pedidos de bolsa é dado sensível ("vida privada")? |
| `Q-APD-18` | Base legal e dados mínimos do **portal QR** e da **carta de estágio** (BI). |
| `Q-APD-22` | Com que **idade** o aluno exerce os seus direitos e consente sozinho? |
| `Q-APD-20` | Prazo adequado para os **`audit_logs`**. |
| `Q08-05` | Prazos legais de conservação de **recibos, pautas e processos**. |
| `Q-APD-26` | Prazos da legislação laboral para o **processo do trabalhador** e o **ponto**. |
| `Q-APD-31` | Diploma da **avaliação de desempenho**, acesso e conservação das fichas. |
| `MIG-Q36` | Prazo de guarda dos **ficheiros de preparação e imagens** da migração. |
| `MIG-Q41` | **Dados reais** em ensaios de migração no **servidor de produção**. |

---

## 2. Resposta curta por questão

> [!note] Ponto de partida comum
> ✅ A **Lei n.º 22/11** continua a ser a lei em vigor. A 25/06/2026 a Assembleia Nacional **rejeitou na generalidade** um projeto de alteração da UNITA (sobre dados eleitorais); não foi encontrada nova lei aprovada (AllAfrica/ANGOP, 26/06/2026). A proposta de 2025 citada na APD-11 (consentimento aos 16 anos) **não está em vigor**.

### `Q-APD-15` — Saúde: consentimento escrito ou autorização da APD?

**A letra da lei não decide; a solução prudente continua a ser pedir autorização.**
- ✅ Art. 14.º n.º 1: o tratamento de dados de saúde exige consentimento "inequívoco, expresso e escrito" do titular **ou do representante legal** "**e/ou**" autorização da APD. O n.º 2 dispensa o consentimento só para fins médicos (medicina preventiva, diagnóstico, assistência, gestão de serviços de saúde, emergência) ou interesse público.
- ✅ Art. 13.º (sensíveis em geral): sem disposição legal, exige **autorização** da APD; o consentimento escrito é uma das **condições** para a APD autorizar, não um substituto da autorização.
- ✅ O DP n.º 60/21 prevê uma taxa própria de **autorização para dados de saúde (139.123,00 Kz)** — o legislador conta com esse ato (ver ticket #36).
- ✅ Arts. 31.º n.º 2 e 51.º n.º 1 a): separação lógica obrigatória; incumprir os arts. 14.º–17.º dá multa de USD 75.000 a 150.000 (triplicada para pessoas coletivas).
- 🔶 **Leitura:** o "ou" permitiria defender que o consentimento escrito basta; o art. 13.º (regime geral dos sensíveis) e a existência da taxa apontam para a **autorização como regra** quando não há lei que imponha o tratamento. Como a escola não presta cuidados de saúde (n.º 2 não se aplica), a combinação **consentimento escrito + pedido de autorização** é a única que resiste às duas leituras. ❌ Sem confirmação da prática da APD.

### `Q-APD-21` — Acesso por intermédio de médico?

**Sim, quando o titular exerce o direito de acesso aos dados de saúde.**
- ✅ Art. 26.º n.º 7: "o acesso aos dados relativos à saúde e vida sexual, incluindo os dados genéticos, é feito por intermédio de médico escolhido pelo titular ou pelo seu representante legítimo" (resumo do texto).
- 🔶 A regra está no **direito de acesso do titular** (art. 26.º). Não regula o acesso **interno** do pessoal da escola (isso é o art. 31.º: só pessoas autorizadas, registo de quem acede). Também não distingue a origem dos dados: um atestado entregue pelo encarregado é, ainda assim, dado de saúde. ❌ Não há texto da APD sobre se basta devolver ao titular uma cópia do documento que ele próprio entregou.

### `Q-APD-16` — Propinas em atraso e semáforo: dados de crédito?

**Provavelmente não no sentido próprio, mas o risco não é nulo.**
- ✅ Art. 16.º (epígrafe: "dados de crédito e de solvabilidade"): n.º 1 exige consentimento ou autorização; n.º 2 refere os dados "relativos ao cumprimento e incumprimento das **obrigações creditícias**" e exige **notificar o titular em 60 dias** e **autorização** da APD. ✅ O art. 5.º **não define** "dados de crédito". ✅ O art. 22.º n.º 3 liga estes dados a bancos e autoridades judiciais.
- 🔶 "Obrigações creditícias" e "solvabilidade" apontam para **operações de crédito** e avaliação da capacidade de pagar (bancos, centrais de risco), não para a conta-corrente de um contrato de ensino, que tem base no **contrato** (art. 12.º n.º 2 a)). O risco aumenta se o semáforo for usado para **avaliar a pessoa** além do contrato (p. ex., recusar matrícula de irmãos, partilhar listas de devedores). ❌ Não confirmado pela APD.

### `Q-APD-17` — Borderô fraudulento: dado sobre ilícito?

**Marcar a pessoa como suspeita sim; registar que o documento é inválido, provavelmente não.**
- ✅ Art. 15.º n.º 1: dados "relativos a pessoas **suspeitas** de actividades ilícitas, infracções penais, contravenções" só podem ser tratados por **autoridade pública** com disposição legal e parecer da APD, ou com **autorização** da APD (taxa de 46.546,00 Kz, DP n.º 60/21, ticket #36).
- ✅ Art. 22.º n.º 2: a comunicação ao Ministério Público ou aos órgãos de investigação por obrigação legal dispensa o consentimento.
- 🔶 Registar que **um documento bancário** foi recusado (estado do borderô, motivo técnico) é necessário à execução do contrato e à contabilidade. Uma etiqueta sobre **a pessoa** ("tentativa de fraude", lista de suspeitos) cai no art. 15.º. A mitigação RF-P-APD-25 está alinhada com a lei. A suspeita deve seguir para as autoridades, não ficar como atributo do encarregado no SGE.

### `Q-APD-23` — Situação socioeconómica nas bolsas: dado sensível?

**Provavelmente sim ("vida privada").**
- ✅ Art. 5.º c): são sensíveis os dados sobre "**vida privada**", sem definição do conceito. ✅ Art. 13.º: sensíveis só com disposição legal ou autorização da APD (taxa "outros dados sensíveis": 11.943,00 Kz, ticket #36).
- 🔶 Rendimentos, composição e condições do agregado familiar, desemprego ou doença na família são o núcleo típico da vida privada. Não foi encontrada norma que **obrigue** a escola a recolhê-los, por isso a via é **consentimento escrito + autorização**, ou recolher só o resultado (escalão, despacho) e devolver os comprovativos. ❌ A APD não publicou leitura do conceito que tenhamos lido.

### `Q-APD-18` — Portal QR e carta de estágio

- ✅ A Lei n.º 22/11 **não tem** fundamento geral de "interesse legítimo" (art. 12.º n.º 2 a)–d) legíveis: contrato, obrigação legal, interesses vitais, interesse público; alínea e) ilegível). ✅ A comunicação a terceiros sem consentimento só nos casos do art. 22.º n.º 2 (lei, contrato, obrigação legal…). ✅ Princípio da finalidade (art. 9.º) e da conservação (art. 11.º). ❌ O art. 8.º (provável princípio da adequação/proporcionalidade) **não é legível** na reprodução.
- ✅ Lei n.º 25/12, art. 30.º n.º 3 d): proteção da criança contra "inadequada exposição, uso ou disseminação" de informação na internet.
- 🔶 **Portal QR:** a base é a **execução do serviço** ao titular (o documento emitido a pedido dele serve para ser apresentado a terceiros) e, para documentos fiscais, a **obrigação legal**. O portal **confirma** o que o terceiro já tem na mão; não deve **revelar** mais. A lista da APD-11 §7.3 é compatível com a lei. Para **menores**, o art. 30.º da Lei n.º 25/12 reforça a minimização.
- 🔶 **Carta de estágio:** comunicação à empresa com base no **contrato** e no regime curricular da 13.ª Classe (art. 22.º n.º 2). Dados mínimos: nome, curso, classe, ano letivo, período e área do estágio. O **BI** só se a empresa o exigir para um fim próprio (seguro, controlo de acesso); nesse caso, é a empresa que o pede ao aluno, ou vai com consentimento. ❌ Não foi lido o diploma do estágio da 13.ª Classe.

### `Q-APD-22` — Idade para exercer direitos sozinho

**18 anos. Antes disso, pelo representante legal.**
- ✅ A Lei n.º 22/11 **não fixa idade**; refere o **representante legal** (arts. 12.º n.º 2 c), 13.º, 14.º n.º 1) e informação adaptada a **menores** (art. 25.º n.º 4).
- ✅ Maioridade aos **18 anos** (CRA, art. 24.º — APD-11 F4). ✅ A Lei n.º 25/12 aplica-se a menores de 18 (art. 2.º); fala de exercício "progressivo" dos direitos (art. 25.º) e de participação "de acordo com a sua idade e maturidade" (art. 35.º), **sem fixar idade**.
- ❌ Proposta de 16 anos (2025): **não vigente**.
- ❌ Não foi lido o texto angolano do Código Civil sobre exceções à incapacidade (art. 127.º) e emancipação (arts. 132.º–133.º); só as epígrafes (AngoLEX). 🔶 Um aluno **emancipado** (p. ex., por casamento) exerceria os direitos sozinho; o SGE não deve presumir, mas permitir registar.
- 🔶 Boa prática compatível com a lei: **ouvir** o aluno menor com maturidade, mas o consentimento formal é do representante. Aos 18 anos, o acesso do encarregado às notas deixa de ter base automática.

### `Q-APD-20` — `audit_logs`: prazo adequado

**A lei não fixa número; manda que seja "adequado" e limitado à finalidade.**
- ✅ Art. 31.º n.º 1: verificar *a posteriori* que dados foram introduzidos, quando e por quem, "em prazo adequado à natureza do tratamento". ✅ Art. 11.º n.º 1: só pelo tempo necessário; depois eliminar ou anonimizar. ✅ Art. 28.º: **bloquear/conservar** quando necessário a interesse legítimo (exercício de direito, obrigação legal).
- 🔶 O prazo justifica-se pela **prova que o registo serve**: registos permanentes (Livro/Folha/Termo, reaberturas) — enquanto durar o registo; financeiro — 5 anos mínimo, 10 por prudência (CGT); laboral — 1 ano após a cessação / 2 anos para salários (LGT); disciplinar — 1 ano (LGT art. 101.º). A estrutura do PC-15 (permanente / 10 anos / 3 anos / IP 90 dias) é **compatível** com isto. ❌ Não confirmados os prazos de prescrição do procedimento penal dos crimes dos arts. 56.º–57.º (Código Penal), que poderiam justificar um prazo maior para acessos indevidos.

### `Q08-05` — Recibos, pautas e processos

- ✅ **Recibos:** mínimo **5 anos** (CGT art. 62.º n.º 7; art. 220.º n.º 3 na redação da Lei n.º 21/20; DP n.º 71/25 art. 26.º); **10 anos** por prudência (caducidade alargada por crime tributário, art. 62.º n.º 3). Já confirmado no ticket #33.
- ✅ **Lei Geral dos Arquivos (Lei n.º 14/17):** aplica-se a arquivos **públicos e privados** (art. 2.º); **não fixa** prazos por tipo de documento, remete para **Tabelas de Temporalidade** (arts. 16.º n.º 2, 18.º, 19.º). Fases: ativa até 10 anos, semiativa 10–25, inativa após 25 (art. 10.º). Nos **arquivos públicos**, conservação até **25 anos** e depois preservação definitiva (art. 19.º n.º 3). São públicos os arquivos de órgãos do Estado e de entidades privadas "**encarregues de serviços públicos**" (art. 14.º a)).
- 🔶 (AngoLEX, não confirmado no DR) **DP n.º 198/26** (Regulamento da Lei Geral dos Arquivos, assinado a 06/10/2026): remete os prazos para um **Regulamento Arquivístico** e para Tabelas de Temporalidade **ainda a aprovar**; exige **auto de eliminação** assinado por três responsáveis, com duplicado ao órgão coordenador (art. 20.º).
- ❌ **Nenhuma norma do MED** sobre conservação de pautas, livros de termos ou processos individuais foi encontrada (pesquisa no índice do MED em lex.ao).
- 🔶 **Pautas e processos:** sem tabela aprovada, o PC-01 (**permanente** para o que certifica habilitações) é a escolha coerente com a finalidade (art. 11.º) e com a Lei n.º 14/17, sobretudo se o IPCAG for entidade "encarregue de serviço público".

### `Q-APD-26` — Processo do trabalhador e ponto

**A LGT não fixa prazo de conservação; fixa prazos de prescrição que dão o mínimo.**
- ✅ **Lei n.º 12/23** (LGT, DR I Série n.º 245, 27/12/2023; vigor 90 dias após publicação, art. 322.º):
  - créditos do contrato prescrevem **1 ano** após o dia seguinte à cessação (art. 312.º n.º 1);
  - salários e outras prestações: **2 anos** a contar do vencimento, ou 1 ano após a cessação (art. 255.º n.º 1);
  - se o trabalhador reclamar antes da prescrição e o empregador não apresentar o **recibo**, presume-se o não pagamento (art. 247.º n.º 4);
  - registo obrigatório de **trabalho extraordinário** (art. 187.º) e de horas em isenção de horário (art. 156.º);
  - medidas disciplinares registadas no **processo individual** (art. 95.º n.º 1); infração disciplinar prescreve em **1 ano** (art. 101.º n.º 2);
  - **certificado de trabalho** com datas de admissão e cessação, funções e qualificação, a entregar na cessação (art. 275.º);
  - dados do trabalhador sujeitos à lei de proteção de dados (art. 24.º n.º 4).
- 🔶 **Mínimo laboral:** vínculo + **1 ano** (art. 312.º), mas recibos de salário e registos de horas que provam pagamentos **pelo menos 2 anos** desde o vencimento. Como os salários e o IRT são **operações fiscais**, prevalece o CGT: **5 anos** (10 por prudência). O PC-13 (ponto 5 anos) é compatível; o PC-12 pode ficar "vínculo + 5 anos" para o processo, mantendo os dados mínimos para segundas vias do certificado de trabalho.
- ❌ Não foram lidos: prazos da **segurança social** (contribuições, carreira contributiva) nem o regime da **função pública**, que se aplicaria se o pessoal for agente público (liga a `Q-APD-02`, ticket #36).

### `Q-APD-31` — Fichas de avaliação de desempenho

- ✅ **DP n.º 28/22, de 27 de Janeiro** (DR I Série n.º 18, p. 971): Regime Jurídico da Avaliação de Desempenho dos **Agentes de Educação** (educadores, auxiliares, professores, técnicos pedagógicos, especialistas), com vínculo definitivo, probatório ou de colaboração (art. 2.º). Avalia o diretor, ouvido o Conselho Pedagógico (art. 24.º); avaliação **anual** (art. 16.º n.º 2); o avaliado **assina** a ficha (art. 25.º); reclamação em 5 dias úteis (art. 28.º); recurso hierárquico (arts. 28.º–30.º, prazos contraditórios: 5 ou 10 dias úteis). Efeitos: promoção após **5 anos consecutivos** de "Bom"; avaliação negativa suspende contagem de tempo e pode impedir renovação (art. 23.º). **Não fixa prazo de conservação** das fichas.
- ✅ Para empregadores privados, a LGT (art. 233.º) manda avaliar com objetivos divulgados no regulamento interno, sem prazo de conservação.
- 🔶 O DP n.º 28/22 refere "organismos do Sector da Educação" e a legislação da função pública: aplica-se ao IPCAG se o pessoal for **agente público** (`Q-APD-02`). As fichas são necessárias pelo menos durante a **janela de 5 anos** de que depende a promoção, mais o tempo de recurso: proposta coerente "vínculo ativo: últimos 5–6 anos; após cessação: + prazo laboral".

### `MIG-Q36` — Ficheiros de preparação e imagens da migração

- ✅ Não há norma com prazo próprio. ✅ Art. 11.º (só o necessário) e art. 23.º (o subcontratado destrói ou devolve os dados no fim do contrato).
- ✅ Lei n.º 14/17 art. 38.º: o armazenamento eletrónico é permitido (n.º 1), mas os documentos digitalizados "não se equiparam aos documentos físicos originais" e estes **não podem ser eliminados** sem autorização do Órgão Reitor (n.º 2; ver também art. 5.º h)).
- 🔶 A destruição das **cópias intermédias** (folhas de cálculo, extratos, digitalizações de trabalho) não toca nos originais em papel, que ficam no arquivo da escola. O PC-28 (**90 dias** após o fecho da onda e aprovação das reconciliações) é compatível. Convém manter um **registo de destruição** (análogo ao auto de eliminação do DP n.º 198/26). As digitalizações que passem a ser a **imagem oficial** associada ao processo (se o SGE as guardar) seguem o prazo do registo a que pertencem, não o PC-28.

### `MIG-Q41` — Dados reais em ensaios no servidor de produção

**Não há proibição expressa; há deveres que tornam o ensaio com dados reais um tratamento a justificar.**
- ✅ "Tratamento" inclui organizar, conservar, adaptar, consultar, interconectar (art. 5.º o)). ✅ Finalidade (art. 9.º); segurança adequada e controlo de quem acede e introduz dados (arts. 30.º–31.º); subcontratado com contrato escrito (art. 23.º); sigilo (art. 32.º); acesso indevido é crime (art. 56.º).
- 🔶 Migrar os dados do próprio IPCAG para o seu novo sistema é **compatível** com as finalidades originais (é o mesmo tratamento noutro meio). Mas um ensaio com dados reais exige: ambiente **isolado** da base de produção ativa (para não misturar ensaio e registos oficiais), acesso restrito e registado, compartimento de saúde **excluído ou mascarado**, **eliminação** da cópia de ensaio após aprovação, e contrato do art. 23.º com quem executa. Mencionar a migração na notificação à APD. Preferir **dados pseudonimizados** nos ensaios iniciais e dados reais só no ensaio geral. ❌ Sem orientação da APD.

---

## 3. Evidência

| Ponto | Fonte | Estado |
| :--- | :--- | :---: |
| Lei n.º 22/11 continua em vigor; projeto de alteração rejeitado a 25/06/2026 | AllAfrica (ANGOP), 26/06/2026 | ✅ confirmado (fonte secundária) |
| Saúde: consentimento escrito "e/ou" autorização; exceções médicas | Lei n.º 22/11, art. 14.º (lex.ao) | ✅ confirmado |
| Sensíveis: disposição legal ou autorização; consentimento é condição da autorização | Lei n.º 22/11, art. 13.º | ✅ confirmado |
| Taxa de autorização de saúde existe (139.123 Kz) | DP n.º 60/21, Anexo (ticket #36) | 🔶 reprodução não oficial |
| Autorização é necessária mesmo com consentimento | Interpretação dos arts. 13.º–14.º | 🔶 inferido |
| Acesso a dados de saúde por intermédio de médico | Lei n.º 22/11, art. 26.º n.º 7 | ✅ confirmado |
| Art. 26.º n.º 7 não limita o acesso interno do pessoal | Leitura sistemática (art. 26.º vs. art. 31.º) | 🔶 inferido |
| Art. 16.º: "dados de crédito e de solvabilidade"; n.º 2 "obrigações creditícias"; 60 dias + autorização | Lei n.º 22/11, art. 16.º | ✅ confirmado |
| "Dados de crédito" sem definição no art. 5.º | Lei n.º 22/11, art. 5.º | ✅ confirmado |
| Propinas em atraso fora do art. 16.º | Interpretação | 🔶 inferido |
| Art. 15.º: pessoas **suspeitas** de atividades ilícitas; autoridade pública ou autorização | Lei n.º 22/11, art. 15.º n.º 1 | ✅ confirmado |
| Estado do documento ≠ dado sobre a pessoa | Interpretação | 🔶 inferido |
| "Vida privada" é dado sensível, sem definição | Lei n.º 22/11, art. 5.º c) | ✅ confirmado |
| Socioeconómico das bolsas = vida privada | Interpretação | 🔶 inferido |
| Sem fundamento geral de interesse legítimo; art. 12.º n.º 2 a)–d) | Lei n.º 22/11, art. 12.º (e) ilegível) | ✅ confirmado (e) ❌) |
| Comunicação a terceiros: casos do art. 22.º n.º 2 | Lei n.º 22/11, art. 22.º | ✅ confirmado |
| Art. 8.º (adequação/minimização) | lex.ao — não legível | ❌ não confirmado |
| Proteção contra exposição de informação da criança na internet | Lei n.º 25/12, art. 30.º n.º 3 d) | ✅ confirmado |
| Lei n.º 22/11 sem idade de consentimento | Lei n.º 22/11 (leitura integral até ao art. 65.º) | ✅ confirmado |
| Maioridade aos 18 | CRA, art. 24.º (APD-11 F4) | ✅ confirmado |
| Lei n.º 25/12: exercício progressivo, sem idade | Lei n.º 25/12, arts. 25.º, 35.º | ✅ confirmado |
| Código Civil angolano, arts. 127.º e 132.º–133.º | AngoLEX (só epígrafes) | ❌ não confirmado |
| Auditoria "em prazo adequado"; conservação só o necessário | Lei n.º 22/11, arts. 31.º n.º 1, 11.º n.º 1 | ✅ confirmado |
| Recibos: 5 anos; 10 com crime tributário | CGT arts. 62.º, 220.º; DP n.º 71/25 art. 26.º (ticket #33) | ✅ confirmado |
| Lei Geral dos Arquivos: público e privado; prazos por Tabela de Temporalidade; 25 anos em arquivos públicos | Lei n.º 14/17, arts. 2.º, 10.º, 14.º, 18.º, 19.º | ✅ confirmado |
| Digitalizados não substituem originais; eliminação de originais só com autorização | Lei n.º 14/17, art. 38.º | ✅ confirmado |
| DP n.º 198/26: auto de eliminação; tabelas a aprovar | AngoLEX (reprodução) | 🔶 não confirmado no DR |
| Norma do MED sobre conservação de pautas e processos | Índice do MED em lex.ao | ❌ não encontrada |
| LGT: prescrição 1 ano após cessação; salários 2 anos; presunção de não pagamento sem recibo | Lei n.º 12/23, arts. 312.º, 255.º, 247.º (lex.ao) | ✅ confirmado |
| LGT: registo de trabalho extraordinário; processo individual; infração disciplinar 1 ano; certificado de trabalho | Lei n.º 12/23, arts. 187.º, 95.º, 101.º, 275.º | ✅ confirmado |
| LGT sem prazo de conservação de registos | Lei n.º 12/23 (leitura de três partes do texto) | 🔶 inferido (ausência; ~11% final não lido) |
| Avaliação de desempenho dos agentes de educação | DP n.º 28/22, arts. 2.º, 16.º, 23.º–31.º (lex.ao) | ✅ confirmado |
| DP n.º 28/22 só se aplica a agentes públicos | Leitura do âmbito (art. 3.º; remissões para a função pública) | 🔶 inferido |
| Avaliação de desempenho em empresas privadas | Lei n.º 12/23, art. 233.º | ✅ confirmado |
| Ensaios com dados reais: deveres de finalidade, segurança, subcontratação | Lei n.º 22/11, arts. 5.º o), 9.º, 23.º, 30.º–32.º | ✅ confirmado; aplicação 🔶 inferida |
| Orientações da APD sobre qualquer destes temas | apd.ao (em manutenção a 08/11/2026) | ❌ não confirmado |

---

## 4. O que não foi possível confirmar

1. **Prática da APD** sobre: se o consentimento escrito dispensa a autorização de saúde; se basta devolver ao titular o atestado que ele entregou; se propinas em atraso são "dados de crédito"; o alcance de "vida privada". O sítio apd.ao continua em manutenção.
2. **Art. 8.º** e **art. 12.º n.º 2 e)** da Lei n.º 22/11 (ilegíveis na reprodução).
3. **Código Civil angolano** (incapacidade, exceções, emancipação): só as epígrafes foram lidas.
4. **Norma do MED** sobre conservação de pautas, livros de termos e processos individuais; **Tabelas de Temporalidade** (ainda por aprovar segundo o DP n.º 198/26).
5. **DP n.º 198/26** no Diário da República (número, data, página e texto oficial).
6. Se o arquivo do IPCAG é "**arquivo público**" (entidade encarregue de serviço público, Lei n.º 14/17 art. 14.º a)) — depende do título jurídico (`Q-APD-01`/`Q-APD-02`, ticket #36).
7. Prazos da **segurança social** e da **função pública** para processos de pessoal.
8. Prazo de prescrição do procedimento penal dos crimes dos arts. 56.º–57.º da Lei n.º 22/11 (Código Penal).
9. Diploma do **estágio curricular da 13.ª Classe** e os dados que exige das empresas.
10. A parte final (~11%) do texto da LGT não foi lida; pode haver disposição transitória relevante.

---

## 5. Impacto na especificação (só implicações)

### APD-11 ([[11 - Protecao de Dados (APD)]])

- **§1.3 C / `Q-APD-15`:** a recomendação "consentimento escrito + autorização" fica reforçada pelos arts. 13.º–14.º e pela taxa própria; a autorização continua no caminho crítico (prazo de decisão desconhecido, ticket #36).
- **§1.3 C / `Q-APD-21`:** o SGE precisa de um caminho para responder a pedidos de **acesso** a dados de saúde **através de médico** indicado pelo titular ou representante (registo do pedido e do médico).
- **§1.3 C / `Q-APD-23`:** tratar os comprovativos socioeconómicos como **sensíveis**: consentimento escrito, compartimento restrito, pedido de autorização ("outros sensíveis") ou não guardar os comprovativos. O PC-11 (comprovativos 1 ano) mantém-se coerente.
- **§1.3 D / `Q-APD-22`:** confirmado 18 anos como regra; prever o estado "**emancipado**" como exceção registável; nenhuma idade intermédia legal.
- **§1.3 J / `Q-APD-16`–`Q-APD-17`:** a conta-corrente fica na base contratual se o semáforo **não sair** do contrato (sem listas, sem uso noutras decisões). RF-P-APD-25 alinhado com o art. 15.º; o evento de fraude em `audit_logs` deve referir o **documento**, não qualificar a pessoa.
- **§5 PC-nn:**
  - **PC-01:** "permanente" sem norma que o contrarie; a validar com a futura Tabela de Temporalidade e o MED.
  - **PC-10:** 10 anos mantém-se (mínimo legal 5).
  - **PC-12:** passar de "por identificar" para "vínculo + 5 anos" (fiscal) com base mínima laboral de 1–2 anos (LGT arts. 255.º, 312.º).
  - **PC-13:** 5 anos compatível (prova de horas extraordinárias, art. 187.º; salários e IRT).
  - **PC-15:** estrutura compatível com os arts. 11.º e 31.º; a categoria (c) poderia alinhar com o prazo penal, quando confirmado.
  - **PC-28:** 90 dias compatível; acrescentar **registo de destruição**; originais em papel nunca destruídos sem autorização (Lei n.º 14/17 art. 38.º).
  - **PC-32:** ancorar em DP n.º 28/22 (janela de 5 anos para promoção) se o pessoal for agente público.
- **§7.3 / `Q-APD-18`:** a lista de campos do portal QR é compatível com arts. 9.º, 11.º, 22.º e Lei n.º 25/12 art. 30.º; a carta de estágio deve **excluir o BI** por defeito.
- **§9.2:** as questões passam a ter resposta provisória; ficam abertas só nas partes da §4.

### DOC-05 (tabelas)

- `dispensas_medicas`, anexos clínicos e "problema de saúde" (ALT-05-22): compartimento separado (art. 31.º n.º 2) e registo de pedidos de acesso **via médico**.
- `beneficios_bolsas_matricula`: separar o **resultado** (despacho, escalão, %) dos **comprovativos** sensíveis.
- `borderos_bancarios` / `audit_logs`: o estado `INVALIDADO_POR_FRAUDE` qualifica o documento; nenhum campo de "suspeito" em `encarregados_educacao`.
- `alunos`: campo/estado para **emancipação**; a maioridade calcula-se pela data de nascimento.
- `funcionarios_docentes`, `assiduidade_funcionarios`: datas de fim de vínculo para contar PC-12/PC-13; registo de horas extraordinárias (LGT art. 187.º).
- `audit_logs`: partição por categoria de prazo (já proposta no PC-15).

### RF-C19 (migração e conformidade)

- Ensaios com dados reais: ambiente isolado, acesso registado, saúde excluída ou mascarada, eliminação da cópia de ensaio, contrato do art. 23.º com quem executa, menção na notificação à APD.
- Ficheiros intermédios: PC-28 com registo de destruição; os originais em papel ficam fora do âmbito da destruição.

---

## 6. Fontes

**Primárias (texto legal; reprodução do DR em lex.ao, consultada a 08/11/2026)**
- Lei n.º 22/11, de 17 de Junho — Lei da Protecção de Dados Pessoais (arts. 5.º, 9.º–16.º, 22.º, 26.º, 31.º). <https://lex.ao/docs/assembleia-nacional/2011/lei-n-o-22-11-de-17-de-junho/>
- Lei n.º 12/23, de 27 de Dezembro — Lei Geral do Trabalho. DR I Série n.º 245, 27/12/2023, p. 8412 (arts. 24.º, 95.º, 101.º, 156.º, 187.º, 233.º, 247.º, 255.º, 275.º, 312.º, 322.º). <https://lex.ao/docs/assembleia-nacional/2023/lei-n-o-12-23-de-27-de-dezembro/>
- Decreto Presidencial n.º 28/22, de 27 de Janeiro — Regime Jurídico da Avaliação de Desempenho dos Agentes de Educação. DR I Série n.º 18, 27/01/2022, p. 971. <https://lex.ao/docs/presidente-da-republica/2022/decreto-presidencial-n-o-28-22-de-27-de-janeiro/>
- Lei n.º 14/17, de 7 de Agosto — Lei Geral dos Arquivos. DR I Série n.º 133, 07/08/2017, p. 3517 (arts. 2.º, 5.º, 10.º, 14.º, 16.º–19.º, 38.º). <https://lex.ao/docs/assembleia-nacional/2017/lei-n-o-14-17-de-07-de-agosto/>
- Lei n.º 25/12, de 22 de Agosto — Protecção e Desenvolvimento Integral da Criança. DR I Série n.º 162, 22/08/2012, p. 3692 (arts. 2.º, 25.º, 30.º, 35.º). <https://lex.ao/docs/assembleia-nacional/2012/lei-n-o-25-12-de-22-de-agosto/>
- Lei n.º 21/14, de 22 de Outubro (CGT), e Lei n.º 21/20, de 9 de Julho; DP n.º 71/25 — via *Investigação — Regras Fiscais (ticket #33)*.
- DP n.º 60/21, de 10 de Março (taxas da APD) — via *Investigação — Enquadramento APD (ticket #36)*.
- Constituição da República de Angola, art. 24.º — via APD-11 (F4).
- APD — sítio oficial (em manutenção a 08/11/2026). <https://apd.ao/>

**Reproduções não oficiais de texto legal**
- AngoLEX — Decreto Presidencial n.º 198/26, Regulamento da Lei Geral dos Arquivos (arts. 11.º, 12.º, 14.º, 19.º–21.º, 36.º). <https://www.angolex.com/paginas/decreto-presidencial/regulamento-lei-geral-arquivos-198a-26a.html>
- AngoLEX — Código Civil (só o sumário: arts. 122.º–133.º). <https://angolex.com/paginas/codigos/codigo-civil.html>

**Secundárias**
- AllAfrica (ANGOP), *Angola: Parliament Rejects Data Protection Draft Law*, 26/06/2026. <https://allafrica.com/stories/202606260073.html>
