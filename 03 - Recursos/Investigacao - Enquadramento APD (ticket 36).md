---
title: "Investigação — Enquadramento do IPCAG na proteção de dados, notificação à APD, nuvem e transferências (ticket #36)"
aliases:
  - "Investigacao - Enquadramento APD (ticket 36)"
  - "INV-APD-36"
created: 2026-11-08
status: rascunho
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - investigacao
  - apd
---

# Investigação — Enquadramento APD (ticket #36)

> [!abstract] Navegação
> - **Ticket:** [#36](https://github.com/Angeloaqp/sge-ipcag-12008/issues/36) (parte do mapa #11)
> - **Notas que esta investigação estende (sem repetir):** [[11 - Protecao de Dados (APD)]] (APD-11 §1, §9, §10) · [[Verificacao das Referencias Legais]] (LEG-VER §3.10) · [[12.1 - Indice de Questoes em Aberto]]
> - **Decisão afetada:** `DEC-006` (servidor local + réplica na nuvem) no [[12 - Registo de Decisoes e Questoes em Aberto|REG-12]]

> [!important] Natureza deste documento
> É uma **investigação em fontes**, não um parecer jurídico. Cada afirmação indica a fonte e o estado: ✅ **confirmado** (lido no texto citado), 🔶 **inferido** (interpretação nossa), ❌ **não confirmado**. As fontes foram consultadas a **08/11/2026**. Não toma decisões: a §5 só aponta implicações.

---

## 1. Pergunta

Responder, por questão do ticket #36:

| ID | Pergunta |
| :---: | :--- |
| `Q-APD-02` | O IPCAG é sector **privado/cooperativo** ou **público** para a Lei n.º 22/11? Que consequências (art. 40.º)? |
| `Q-LEG-13` | O **DP n.º 93/21** aplica-se ao IPCAG? Qual o enquadramento jurídico de uma escola católica comparticipada? |
| `Q-APD-14` | Notificação à APD **única ou por finalidade**? **Taxas** do DP n.º 60/21? **Canal**? |
| `Q-016` | A **réplica na nuvem** exige notificação ou autorização? |
| `Q09-16` | Há **restrições legais à localização** dos dados? |
| `Q-APD-19` | **Transferências internacionais:** países adequados, condições, **acesso remoto**. |
| `Q-APD-24` | **Lei n.º 9/26** (cibersegurança): obrigações para a escola e para o fornecedor de nuvem. |
| `Q-APD-25` | Confirmar os **artigos ilegíveis** da Lei n.º 22/11 e a **data de publicação** no DR. |

---

## 2. Resposta curta por questão

### `Q-APD-02` — Sector privado ou público?

**Provavelmente privado (Secção IX), mas depende de um documento que ainda não temos.**

- A Lei n.º 22/11 aplica-se a todos os sectores (art. 3.º n.º 1). O privado e cooperativo segue toda a lei **menos a Secção VIII** (art. 42.º).
- O regime mais pesado do sector público (art. 40.º n.º 1) aplica-se a "ficheiros da **Administração Pública** e dos Tribunais". Estes ficheiros só podem ser criados, modificados ou eliminados **ao abrigo de disposição legal**, com conteúdo mínimo (responsável, finalidades, dados, destinatários, segurança…). O critério é ser **Administração Pública**, não receber dinheiro do Estado.
- A Lei de Bases (Lei n.º 17/16, art. 57.º) classifica as escolas como públicas, privadas ou **público-privadas**. O **DP n.º 37/23** regula as **instituições privadas e público-privadas**. Define as público-privadas como escolas "resultantes de parceria público-privada" (art. 3.º h) e diz que os diretores são **designados pelas próprias instituições** (art. 44.º n.º 4). Os professores têm contrato de trabalho ao abrigo da Lei Geral do Trabalho (art. 32.º n.º 1).
- O **Acordo-Quadro Angola–Santa Sé** (DP n.º 302/19) reconhece a personalidade jurídica das dioceses e institutos (art. 3.º) e o direito da Igreja a "erigir e dirigir escolas próprias" (art. 18.º n.º 1 a).
- 🔶 **Conclusão:** se o IPCAG é uma **escola da Igreja** (titular: Diocese ou instituto) em **parceria** com o Estado, é sector **privado**. O art. 40.º não se aplica e a base legal é a do art. 12.º. **Mas** o Acordo-Quadro prevê também que a Igreja **colabore na gestão de escolas públicas** por acordo específico (art. 18.º n.º 3). Os indícios dos documentos reais (cabeçalho do Gabinete Provincial, Comissão de Gestão, pessoal com n.º de agente) são compatíveis com **esta** hipótese. Nesse caso, o responsável pelo tratamento poderia ser o próprio Estado (Gabinete Provincial), e aplicar-se-ia a Secção VIII. **O que decide é o título jurídico da escola** (alvará/licença, acordo de parceria ou acordo de gestão). Esse título ainda não foi obtido (`Q-APD-01`).

### `Q-LEG-13` — O DP n.º 93/21 aplica-se?

**Não por obrigação, se o IPCAG for privado ou público-privado.** O DP n.º 93/21 aplica-se às "Instituições **Públicas**" (art. 2.º, já confirmado em LEG-VER). O DP n.º 37/23, que é o regime das público-privadas, tem regras próprias de direção (art. 44.º: designação pela instituição, homologação pelo ministério, exclusividade) e **não remete** para o DP n.º 93/21 na parte lida. 🔶 Só se aplicaria se o IPCAG fosse uma **escola pública** com gestão confiada à Igreja (art. 18.º n.º 3 do Acordo-Quadro), ou se o acordo de parceria o mandasse aplicar. Nos outros casos, usa-se por **analogia** e como boa prática.

### `Q-APD-14` — Notificação, taxas e canal

- **Única ou por finalidade:** a lei não responde de forma expressa. ✅ A lei fala sempre de "o tratamento" (art. 35.º) e o registo público é **por tratamento** (art. 38.º). ✅ A tabela do DP n.º 60/21 cobra **por ato**: registo **por tipo de ficheiro** e autorização **por tipo de tratamento**. 🔶 Conclusão provável: **um processo por tratamento ou ficheiro**, e não uma notificação única "do SGE". No mínimo: alunos/encarregados, trabalhadores e, se existir, videovigilância. Além disso, há **pedidos de autorização separados** para saúde e, se houver, para transferência internacional. ❌ Não confirmado na prática da APD.
- **Taxas (DP n.º 60/21, Anexo)** — valores em Kz, segundo a reprodução AngoLEX do anexo (lex.ao não reproduz a tabela):
  - **Registo:** ficheiros de trabalhadores **5.100,00**; ficheiros de gestão de clientes **35.777,00**; ficheiros com dados pessoais não sensíveis **4.315,00**; ficheiros não automatizados de entradas e saídas **isento**.
  - **Autorização:** saúde e vida sexual **139.123,00**; outros dados sensíveis **11.943,00**; transferência internacional **350.450,00**; videovigilância e meios eletrónicos de controlo **24.321,00**; crédito e solvabilidade **162.557,00**; interconexão **50.897,00**; dados sobre atividades ilícitas **46.546,00**; biometria **8.400,00**; definição de perfis **14.200,00**.
  - ✅ (lex.ao) Só pagam **metade** os órgãos da Administração Direta do Estado e as autarquias (art. 5.º). 🔶 O IPCAG não parece estar abrangido, salvo se for escola pública.
  - ✅ Pagamento por **RUPE** para a Conta Única do Tesouro (art. 9.º). Se o pedido for eletrónico, paga-se em **5 dias úteis**; se for em papel, paga-se **antes** (art. 11.º). Pode pagar-se em até 3 prestações (art. 10.º).
- **Canal:** ✅ O DP n.º 60/21 prevê **pedidos eletrónicos** e **em papel** (art. 11.º). ❌ O sítio da APD (apd.ao) continuava **em manutenção** a 08/11/2026, por isso não foi possível confirmar o formulário atual, o balcão em linha nem o endereço de correio.

### `Q-016` — A réplica na nuvem exige notificação ou autorização?

- **Nuvem em Angola:** não há autorização própria para "usar nuvem". 🔶 O fornecedor é **subcontratado**: exige **contrato escrito** e **notificação** à APD (art. 23.º n.º 1). O local da réplica e o subcontratado entram na notificação do tratamento (art. 36.º).
- **Nuvem fora de Angola:** é **transferência internacional**. Se a APD considerar o país adequado, exige **notificação** (art. 33.º). Se não, exige **autorização** (art. 34.º). A APD tratou exatamente este caso como transferência internacional: multou a Crescer Tech em cerca de USD 505.000 por **armazenamento numa cloud no exterior** sem notificação nem autorização (Lusa/Ver Angola, 24/06/2026).

### `Q09-16` — Restrições à localização dos dados

**Não foi encontrada nenhuma norma que obrigue a guardar os dados em Angola.** A Lei n.º 22/11 não proíbe a saída de dados: sujeita-a a notificação ou autorização (arts. 33.º–34.º). A Lei n.º 9/26 **não contém regra de localização** (leitura integral da reprodução AngoLEX). O Data Center e Nuvem Nacional do Estado (2026) é apresentado como "soberania digital" em notícias, sem norma de localização associada para entidades privadas. 🔶 Na prática, a localização em Angola é a forma de **evitar** o procedimento de transferência, não uma obrigação legal.

### `Q-APD-19` — Transferências internacionais e acesso remoto

- ✅ A adequação é decidida pela APD **por parecer, caso a caso** (art. 33.º n.º 3–4). ❌ **Não existe lista pública** de países adequados que tenhamos encontrado (nem no texto legal, nem em fontes secundárias; apd.ao inacessível).
- ✅ Sem adequação, a autorização só é dada com uma das condições do art. 34.º n.º 1 (consentimento, contrato, interesse público, interesses vitais, fonte pública, tratado…) ou com **contrato** cujas condições a APD define (n.º 2). Para grupos empresariais, servem regras internas vinculativas (n.º 3). Taxa: **350.450,00 Kz**.
- ✅ A notificação tem de indicar as "transferências de dados previstas para países terceiros" (art. 37.º n.º 1 f).
- **Acesso remoto:** 🔶 o "tratamento" inclui a **consulta** e a **transmissão** (art. 5.º o). Um técnico no estrangeiro que **consulta** dados alojados em Angola faz tratamento a partir de outro país. É prudente tratá-lo como transferência internacional e indicá-lo na notificação. ❌ Não há texto da APD que o confirme.
- **Prazo de decisão de uma autorização:** ❌ não encontrado. Só a **notificação** tem prazo (30 dias, art. 35.º n.º 2).

### `Q-APD-24` — Lei n.º 9/26 (cibersegurança)

- ✅ (AngoLEX, reprodução do articulado) **Lei n.º 9/26 — Lei da Cibersegurança**, aprovada pela AN a 12/08/2026, promulgada a 08/09/2026, datada de **28 de setembro** (Afriwise/VdA, 15/10/2026). Revoga a **Lei n.º 7/17** (art. 65.º) e entra em vigor na publicação (art. 67.º). ❌ **Não confirmada no Diário da República:** a página lex.ao não existe e não temos o número nem a página do DR.
- **Para o IPCAG:** aplica-se a "pessoas públicas e privadas… que utilizem o ciberespaço angolano" (art. 2.º). Tem deveres gerais: segurança e resiliência (art. 29.º) e notificação de incidentes com **impacto significativo** às autoridades competentes (art. 30.º). Entre esses incidentes está a violação de dados pessoais (art. 28.º). O prazo fica para lei especial, com notificação imediata se o impacto for alto (art. 30.º n.º 5). A notificação ao CERT.ao **não substitui** a notificação à APD (art. 30.º n.º 3). 🔶 Os deveres pesados (CSIRT, ponto focal, registo no Centro Nacional de Cibersegurança) recaem sobre **infraestruturas críticas** e **prestadores de serviços essenciais** (art. 14.º). Uma escola não parece estar nestas categorias, salvo designação expressa.
- **Para o fornecedor de nuvem** (arts. 19.º–20.º, 39.º–40.º): CSIRT institucional; registo de utilizadores; **registo no CNC** em 180 dias (art. 64.º; prazo indicado: 27/03/2027); notificação de incidentes aos **clientes** sem demora injustificada e ao CERT.ao (art. 40.º). Segundo a Afriwise, também seguro, política de continuidade e recuperação e resumo dessa política aos clientes. Os centros de dados têm deveres análogos (arts. 18.º, 38.º).
- **Coimas** (art. 56.º, em salários mínimos): pessoas coletivas de 70–150 (leves), 300–500 (graves), 2.000–4.000 (muito graves).

### `Q-APD-25` — Lei n.º 22/11: data e artigos

- ✅ **Designação oficial:** Lei n.º 22/11, de 17 de Junho. Aprovada pela AN a **24/05/2011**, promulgada a **08/06/2011**. Os metadados do lex.ao indicam **DR I Série n.º 114, de 17/06/2011, p. 3185**. ❌ O rodapé de cada página da mesma reprodução diz "n.º 114 de **22** de Junho de 2011". A contradição **mantém-se**: só o DR impresso ou o PDF oficial a resolve.
- **Artigos:** ✅ art. 12.º n.º 2 a) a d) legíveis (contrato, obrigação legal, interesses vitais, interesse público/autoridade pública). ❌ a **alínea e)** continua ilegível. 🔶 O texto do art. 28.º (retificação, atualização e eliminação em **60 dias úteis**) está legível, mas **sem epígrafe**, por isso o número do artigo é inferido. ❌ art. 34.º n.º 1 **i)**, art. 36.º **h)–i)**, art. 40.º n.º 1 **g)–h)** continuam ilegíveis. ✅ arts. 58.º–65.º e 67.º legíveis (art. 63.º: notificação dos tratamentos existentes; art. 65.º: regulamentação em 120 dias; art. 67.º: vigência na data da publicação).
- Anomalia: o art. 39.º, na reprodução, diz "sector **público e cooperativo**", mas a Secção VIII é do sector público e o art. 42.º trata do "privado e cooperativo". 🔶 Provável gralha da reprodução, a verificar no DR.

---

## 3. Evidência

| Ponto | Fonte | Estado |
| :--- | :--- | :---: |
| Lei aplica-se ao sector público, privado ou cooperativo | Lei n.º 22/11, art. 3.º n.º 1 (lex.ao) | ✅ confirmado |
| Privado e cooperativo: tudo menos a Secção VIII | Lei n.º 22/11, art. 42.º (lex.ao) | ✅ confirmado |
| Art. 40.º só para "ficheiros da Administração Pública e dos Tribunais", exige disposição legal | Lei n.º 22/11, art. 40.º n.º 1 (lex.ao) | ✅ confirmado (g–h ilegíveis) |
| Escolas públicas, privadas e público-privadas; o Estado pode co-financiar escolas privadas em parceria | Lei n.º 17/16, arts. 57.º e 98.º n.º 4 (lex.ao) | ✅ confirmado |
| Regime das privadas e público-privadas; público-privadas = parceria; diretores designados pela instituição | DP n.º 37/23, DR I Série n.º 28, 09/02/2023, p. 327, arts. 2.º, 3.º h), 4.º, 32.º, 44.º (lex.ao) | ✅ confirmado (articulado lido parcialmente) |
| Igreja pode erigir e dirigir escolas; pode colaborar na gestão de escolas públicas por acordo | DP n.º 302/19 (Acordo-Quadro Angola–Santa Sé), DR I Série n.º 137, 21/10/2019, p. 8976, arts. 3.º, 15.º, 18.º (lex.ao) | ✅ confirmado |
| IPCAG é escola própria da Igreja em parceria (privada) e não escola pública gerida pela Igreja | — (falta o título jurídico da escola) | ❌ não confirmado |
| DP n.º 93/21 só para instituições públicas | DP n.º 93/21, art. 2.º (LEG-VER §3.10) | ✅ confirmado |
| DP n.º 37/23 não remete para o DP n.º 93/21 | DP n.º 37/23 (lex.ao, articulado lido até ao art. 68.º com lacunas) | 🔶 inferido |
| Notificação por tratamento; registo público por tratamento | Lei n.º 22/11, arts. 35.º, 38.º | 🔶 inferido |
| Taxas cobradas por tipo de ficheiro e por tipo de autorização | DP n.º 60/21, DR I Série n.º 43, 10/03/2021, p. 2119, arts. 1.º, 4.º (lex.ao) | ✅ confirmado |
| Valores da tabela (4.315 a 350.450 Kz) | Anexo do DP n.º 60/21 na reprodução AngoLEX; intervalo coincide com o Expansão (23/03/2021) | 🔶 confirmado em reprodução não oficial |
| Metade para a Administração Direta do Estado; RUPE; 5 dias úteis | DP n.º 60/21, arts. 5.º, 9.º, 11.º (lex.ao) | ✅ confirmado |
| Formulário, balcão em linha e correio da APD | apd.ao (em manutenção a 08/11/2026) | ❌ não confirmado |
| Subcontratado: contrato escrito + notificação à APD | Lei n.º 22/11, art. 23.º n.º 1 | ✅ confirmado |
| País adequado → notificação; não adequado → autorização; adequação por parecer | Lei n.º 22/11, arts. 33.º–34.º | ✅ confirmado |
| Lista pública de países adequados | — | ❌ não encontrada |
| Cloud no exterior sem notificação/autorização = infração (Crescer Tech, ~USD 505.000) | Lusa/Ver Angola, 24/06/2026 (comunicado da APD) | ✅ confirmado (fonte secundária) |
| MAXAM, USD 150.000, transferência ilegal para o Reino Unido | PLMJ/RVA, agosto de 2024 | ✅ confirmado (fonte secundária) |
| "Tratamento" inclui consulta e transmissão (base para o acesso remoto) | Lei n.º 22/11, art. 5.º o) | ✅ confirmado; aplicação ao acesso remoto 🔶 inferida |
| Sem norma de localização de dados | Lei n.º 22/11; Lei n.º 9/26 (AngoLEX); pesquisa de decretos | 🔶 inferido (ausência) |
| Lei n.º 9/26: âmbito, deveres, coimas, revogação da Lei n.º 7/17 | AngoLEX (articulado); Afriwise/VdA, 15/10/2026 | 🔶 confirmado em reprodução não oficial; DR ❌ |
| Lei n.º 22/11: aprovada a 24/05/2011, promulgada a 08/06/2011, DR n.º 114 | lex.ao | ✅ confirmado |
| Data do DR n.º 114 (17 ou 22/06/2011) | lex.ao (metadados vs. rodapé) | ❌ não confirmado |
| Arts. 12.º n.º 2 e), 34.º n.º 1 i), 36.º h)–i), 40.º g)–h) | lex.ao (texto perdido) | ❌ não confirmado |

---

## 4. O que não foi possível confirmar

1. **Título jurídico do IPCAG:** quem é o titular (Diocese de Caxito, instituto religioso ou o Estado), e se existe acordo de parceria (DP n.º 37/23, art. 4.º) ou acordo de gestão de escola pública (Acordo-Quadro, art. 18.º n.º 3). Sem isto, `Q-APD-02` e `Q-LEG-13` ficam em hipótese. **Só a Direção ou a Diocese pode responder** (liga a `Q-APD-01`).
2. **Sítio da APD:** em manutenção. Não foi possível confirmar o formulário, o canal (balcão em linha, correio, presencial), as orientações setoriais, uma eventual lista de países adequados, nem as condições do contrato do art. 34.º n.º 2.
3. **Tabela de taxas no DR:** o lex.ao não reproduz o anexo. Os valores vêm da reprodução AngoLEX. Também não se sabe se houve **atualização** por Decreto Executivo Conjunto (art. 15.º do DP n.º 60/21).
4. **Prazo de decisão** de uma autorização da APD (saúde, transferência).
5. **Lei n.º 9/26 no Diário da República:** número, data e página do DR, e se o texto AngoLEX corresponde ao publicado. Ainda não há lei especial com o prazo de notificação de incidentes nem regulamentação técnica.
6. **Lei n.º 22/11:** a data do DR n.º 114 e as alíneas ilegíveis. Exige o PDF oficial da Imprensa Nacional ou o exemplar impresso.
7. Se o **acesso remoto** de suporte a partir do estrangeiro é, para a APD, transferência internacional.
8. Alterações ao DP n.º 37/23 e as partes do articulado que não foram lidas.

---

## 5. Impacto na especificação (só implicações)

### APD-11 ([[11 - Protecao de Dados (APD)]])

- §1.3 A e `Q-APD-02`: a dúvida passa a ter **duas hipóteses concretas**, ligadas a um documento a pedir: (i) escola da Igreja em parceria → privado (Secção IX); (ii) escola pública com gestão da Igreja → público (Secção VIII, art. 40.º; responsável possivelmente o Gabinete Provincial). A hipótese escolhida muda o responsável, quem assina a notificação e as bases legais.
- §1.3 B e `Q-APD-14`: o plano de conformidade pode prever **vários processos** de notificação e autorização, em vez de um único. A tabela de taxas permite estimar o custo (p. ex., registos de alunos e trabalhadores + autorização de saúde ≈ 4.315 ou 35.777 + 5.100 + 139.123 Kz), por confirmar com a APD.
- §1.3 F: a Lei n.º 9/26 acrescenta um **segundo canal** de notificação de incidentes (CERT.ao e autoridades competentes), cumulativo com a APD.
- §1.3 L: a Lei n.º 9/26 deixa de ser "só fonte secundária" e passa a ter articulado lido, mas continua sem confirmação no DR.
- §9.2: `Q-APD-19` (lista de países adequados, prazo de autorização), `Q-APD-24` (DR) e `Q-APD-25` (data e alíneas) continuam em aberto só nas partes listadas na §4.

### DEC-006 (alojamento: servidor local + réplica na nuvem)

- Uma réplica **em Angola** implica contrato de subcontratação (art. 23.º) e inclusão na notificação. Uma réplica **fora de Angola** implica um procedimento de transferência adicional. Sem lista de adequação, conta-se com **autorização** (taxa de 350.450 Kz, prazo desconhecido), e há um precedente sancionatório recente e específico de *cloud* no exterior.
- Não há obrigação legal de localização. A condição "dados em Angola" é uma **escolha de redução de risco e de prazo**, não uma imposição da lei.
- O **suporte remoto** a partir do estrangeiro pode precisar do mesmo tratamento que a réplica fora de Angola.
- O fornecedor de nuvem terá deveres próprios pela Lei n.º 9/26 (registo no CNC, notificação de incidentes aos clientes, continuidade). Podem servir de **critérios de seleção** e de cláusulas de contrato.

### OPS-09 ([[09 - Integracoes, Infraestrutura e Operacao]])

- §3.3 e §3.5 (localização e cópias): o inventário de locais de dados (RNF-PRV-07) tem de incluir também o **local de onde se acede** (suporte remoto), e não só onde os dados ficam.
- Gestão de incidentes: os procedimentos operacionais teriam de prever a notificação à **APD** e, havendo impacto significativo, às autoridades da Lei n.º 9/26. Prazo: o que a lei especial vier a fixar.
- Contratos com fornecedores (nuvem, SMS, correio): cláusulas do art. 23.º da Lei n.º 22/11 e, para nuvem e centros de dados, as obrigações dos arts. 18.º–20.º e 38.º–40.º da Lei n.º 9/26.

---

## 6. Fontes

**Primárias (texto legal; reprodução integral do DR em lex.ao, consultada a 08/11/2026)**
- Lei n.º 22/11, de 17 de Junho — Lei da Protecção de Dados Pessoais. DR I Série n.º 114 (data por confirmar: 17 ou 22/06/2011), p. 3185. <https://lex.ao/docs/assembleia-nacional/2011/lei-n-o-22-11-de-17-de-junho/>
- Decreto Presidencial n.º 60/21, de 10 de Março — Regulamento das Taxas a Cobrar pela APD. DR I Série n.º 43, 10/03/2021, p. 2119. <https://lex.ao/docs/presidente-da-republica/2021/decreto-presidencial-n-o-60-21-de-10-de-marco/>
- Decreto Presidencial n.º 37/23, de 9 de Fevereiro — Regime Jurídico das Instituições Privadas e Público-Privadas de Educação Pré-Escolar e de Ensino Primário e Secundário. DR I Série n.º 28, 09/02/2023, p. 327. <https://lex.ao/docs/presidente-da-republica/2023/decreto-presidencial-n-o-37-23-de-09-de-fevereiro/>
- Decreto Presidencial n.º 302/19, de 21 de Outubro — aprova o Acordo-Quadro entre a República de Angola e a Santa Sé (assinado a 13/09/2019). DR I Série n.º 137, 21/10/2019, p. 8976. <https://lex.ao/docs/presidente-da-republica/2019/decreto-presidencial-n-o-302-19-de-21-de-outubro/>
- Lei n.º 17/16, de 7 de Outubro — Lei de Bases do Sistema de Educação e Ensino. <https://lex.ao/docs/assembleia-nacional/2016/lei-n-o-17-16-de-07-de-outubro/>
- Decreto Presidencial n.º 93/21, de 16 de Abril — via [[Verificacao das Referencias Legais]] §3.10. <https://lex.ao/docs/presidente-da-republica/2021/decreto-presidencial-n-o-93-21-de-16-de-abril/>
- APD — formulários de tratamento de dados (em manutenção a 08/11/2026). <https://apd.ao/ao/catalogo/formularios-apd/tratamento-de-dados-pessoais/>

**Reproduções não oficiais de texto legal**
- AngoLEX — Lei n.º 9/26, Lei da Cibersegurança (articulado). <https://angolex.com/paginas/leis/lei-ciberseguranca-9a-26a.html>
- AngoLEX — DP n.º 60/21, com o Anexo (Tabela de Taxas da APD). <https://angolex.com/paginas/decreto-presidencial/regulamento-das-taxas-a-cobrar-pela-agencia-de-proteccao-de-dados-60a-21a.html>

**Secundárias (prática e contexto)**
- Lusa / Ver Angola, *Agência de Protecção de Dados multou duas empresas em mais de 600 mil dólares*, 24/06/2026. <https://www.verangola.net/va/pt/062026/Sociedade/49239/Agência-de-Protecção-de-Dados-multou-duas-empresas-em-mais-de-600-mil-dólares.htm>
- PLMJ Colab / RVA Advogados, *Dados Pessoais e Ciber-segurança em Angola*, agosto de 2024. <https://plmj.com/xms/files/03_Novidades_legislativas/2024/N_Colab_RVA-PLMJ_Dados_Pessoais_e_Ciber-seguranca_em_Angola.pdf>
- Afriwise / VdA, *New Cybersecurity Law*, 15/10/2026. <https://www.afriwise.com/blog/new-cybersecurity-law>
- Expansão, *Taxas para tratamento e protecção de dados vão de 4 mil a 350 mil Kz*, 23/03/2021. <https://expansao.co.ao/legislacao/interior/taxas-para-tratamento-e-proteccao-de-dados-vao-de-4-mil-a-350-mil-kz-101459.html>
- DLA Piper, *Data Protection Laws of the World — Angola* (revisto em 2021; sem lista de países adequados). <https://www.dlapiperdataprotection.com/index.html?c=AO&t=law>
- Ver Angola, notícias sobre o Data Center e Nuvem Nacional (abril de 2026), sem norma de localização. <https://www.verangola.net/va/pt/042026/Tecnologia/48622/Novo-centro-de-dados-do-Governo-reforça-soberania-digital-do-país.htm>
