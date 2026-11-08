---
title: "Investigação — Regras fiscais: contingência, anulação, numeração, arquivo e DE n.º 683/25 (ticket 33)"
created: 2026-11-08
status: rascunho
tags: [sge, ipcag-12008, investigacao, agt]
---

# Investigação — Regras fiscais (ticket 33)

> [!info] Âmbito e limites
> Esta nota responde à issue #33 e **continua** a [[Investigacao - Faturacao AGT (Q-001)|investigação do #19]] (ramo `research/faturacao-agt`). Não repete o que lá está (obrigação de faturar, regimes de IVA, isenção, RUPE). **Não é parecer jurídico nem fiscal.**
>
> Fontes lidas a 2026-11-08:
> - DP n.º 71/25 e Código Geral Tributário (CGT) e a sua alteração, no **lex.ao** (reprodução do Diário da República);
> - **DE n.º 683/25**: o fac-símile do **Diário da República, I Série, n.º 159, de 22/08/2025**, numa cópia alojada pela EY Angola. O lex.ao não tem este diploma.
>
> Do DE n.º 683/25 foram lidos o articulado (art. 1.º–6.º), o Anexo II, o início do Anexo III e as páginas do Anexo I sobre o documento, a anulação e as séries (pp. 19164–19169, 19184–19187 e 19193–19195). **O resto do Anexo I e as tabelas finais não foram lidos.**
>
> Legenda: **Confirmado** = lido no texto da fonte primária · **Inferido** = conclusão nossa a partir do texto · **Não confirmado** = não encontrado numa fonte primária.
>
> Siglas: **DP** = Decreto Presidencial · **DE** = Decreto Executivo · **CIVA** = Código do IVA · **NC** = nota de crédito.

## 1. Pergunta

Segundo a lei fiscal angolana, como deve o SGE tratar:

| Id | Pergunta |
| :--- | :--- |
| `Q08-06`, `MIG-Q31` | A **contingência**, quando o servidor local ou a ligação à AGT falham. |
| `MIG-Q14` | A **anulação** de um recibo emitido antes do SGE. |
| `MIG-Q15` | A **numeração**: por ano civil ou por ano letivo? Abre-se uma série nova a meio do ano quando se muda de software? |
| `Q09-17` | O **documento fiscal impresso que se perdeu**, sem reutilizar o número. |
| `MIG-Q37` | Por **quanto tempo** se guarda o arquivo antigo. |
| `Q-LEG-20` | O **texto oficial do DE n.º 683/25** e as regras de certificação do software. |

## 2. Resposta curta por questão

**`Q08-06` / `MIG-Q31` — Contingência.** A lei prevê dois casos (DP n.º 71/25, art. 18.º):
- **Sem ligação à AGT, mas com o computador a funcionar.** O software certificado continua a emitir *offline*. O documento entregue ao aluno leva a menção «emitido em contingência, pendente de autorização» e é enviado à AGT depois. A escola tem de **avisar logo a AGT** de que está em contingência.
- **Sem luz ou com o equipamento avariado.** A escola usa **blocos de faturas impressos por tipografia certificada**, com **autorização da AGT** e por **45 dias corridos, no máximo** (art. 7.º, n.º 6).

Há ainda um limite: se o software ficar **mais de 60 dias sem comunicar**, bloqueia a emissão (art. 17.º, n.º 5). Um documento que a AGT rejeite "não existe" para efeitos fiscais e tem de ser corrigido (DE n.º 683/25, Anexo II). A lei **não fixa** o prazo para enviar os documentos de contingência depois de a ligação voltar.

**`MIG-Q14` — Anular um recibo de antes do SGE.** A lei só traz duas formas de anular:
- **por nota de crédito**, com o motivo, a palavra «anulação», o número do documento original e a prova de que o pagador soube (DP n.º 71/25, art. 8.º, n.º 4–7);
- **anulação no próprio software, sem nota de crédito**, só quando o adquirente está mal identificado ou o documento nunca foi entregue (art. 8.º, n.º 8–9).

A lei **não diz** como se anula um documento emitido noutro software ou em papel. **Inferido:** a correção faz-se com um documento novo no software em uso (nota de crédito ou "estorno"), que cita o número do documento antigo. O original fica no arquivo, com a nota de que foi substituído (CIVA, art. 39.º, n.º 2). O tipo **RE – "Estorno ou Recibo de Estorno"** existe na lista de documentos do DE n.º 683/25. Falta saber como a AGT o quer usar para recibos.

**`MIG-Q15` — Numeração.** A numeração é "sequencial e cronológica por tipo de documento e o respectivo ano económico", com uma ou mais séries (DP n.º 71/25, art. 10.º, n.º 1, b)). Na fatura eletrónica:
- as séries são **geradas pela AGT** (DE n.º 683/25, art. 4.º);
- o código da série tem de conter o **ano de emissão**;
- só se criam séries para o **ano do sistema**; a partir de 15 de Dezembro, também para o ano seguinte;
- a série **fecha quando acaba o ano de emissão**.

Ou seja, a série segue o **ano civil (Janeiro a Dezembro)**, não o ano letivo. **Uma série nova a meio do ano é possível e, ao mudar de software, inevitável:** a série nova é pedida à AGT e comunicada **antes** de se emitir (DP n.º 71/25, art. 24.º, n.º 1, c) e n.º 2). Faturas com séries não comunicadas contam como **não emitidas** (art. 35.º, n.º 4).

**`Q09-17` — Documento impresso perdido.** O número **nunca se reutiliza**. O documento continua no software. Se a cópia em papel se perder, **reimprime-se** com a menção «2.ª via, em conformidade com a original» (DP n.º 71/25, art. 7.º, n.º 5). Com fatura eletrónica, o documento também pode ser consultado pelo QR code no Portal do Contribuinte (DE n.º 683/25, Anexo III). A lei **não tem regra própria** para a perda de um original de bloco em papel. **Inferido:** registar a ocorrência e manter o número no arquivo, sem o reutilizar.

**`MIG-Q37` — Por quanto tempo se guarda o arquivo.** O mínimo legal é de **5 anos**:
- o DP n.º 71/25 manda arquivar faturas, documentos fiscais e registos informáticos "nos prazos estabelecidos no Código Geral Tributário" (art. 26.º, n.º 1);
- o CGT manda conservar "todos os documentos e registos relativos às operações efectuadas nos últimos 5 (cinco) anos" (art. 62.º, n.º 7);
- a alteração de 2020 repete: "por um período de 5 anos" (art. 220.º, n.º 3).

O direito de liquidar imposto pode ir até **10 anos** se houver crime tributário (art. 62.º, n.º 3). **Inferido:** guardar 10 anos é a opção prudente. O arquivo tem de estar íntegro e legível até ao fim desse prazo (DP n.º 71/25, art. 19.º, n.º 1; art. 27.º). Se se usaram sistemas diferentes nesse período, a documentação técnica de cada um tem de continuar acessível (art. 22.º, n.º 5). Isto vale para o arquivo antigo em papel e para o software anterior. Os **registos escolares** (pautas, termos, processos) têm outras regras, que não estão nesta nota.

**`Q-LEG-20` — DE n.º 683/25.** O **texto oficial foi lido** (DR I Série n.º 159, de 22/08/2025, p. 19164 e seguintes).
- Tem 6 artigos: objeto; Anexos I a III; atualizações técnicas publicadas pela AGT; **séries geradas pela AGT**; dúvidas resolvidas pela Ministra das Finanças; entrada em vigor **30 dias após a publicação**.
- **Anexo I:** estrutura de dados da API REST/JSON. Inclui os tipos de documento, os estados do documento (incluindo **A – Anulado** e **C – Correção de documento rejeitado**), os motivos de anulação, a assinatura JWS e os campos do software (nome, versão, número de certificação).
- **Anexo II:** modelo de **validação *a posteriori***.
- **Anexo III:** serviços web (`registarFactura`, `obterEstado`, `listarFacturas`, `consultarFactura`, `solicitarSerie`, `listarSeries`, `validarDocumento`) e especificação do QR code.

O DE **não regula o processo de certificação ou validação do software**: quem pede, requisitos, testes, prazos. Esse processo **não foi encontrado** numa fonte primária.

## 3. Evidência

| # | Ponto | Fonte | Estado |
| :--- | :--- | :--- | :--- |
| F1 | Contingência *offline* no software eletrónico quando falta a comunicação com a Plataforma (art. 18.º, n.º 1, a)). Menção «emitido em contingência, pendente de autorização» (n.º 2). Envio posterior para validação (n.º 3). Aviso imediato à AGT (n.º 4). | DP n.º 71/25, de 20/03/2025, DR I Série n.º 52 — [lex.ao](https://lex.ao/docs/presidente-da-republica/2025/decreto-presidencial-n-o-71-25-de-20-de-marco/) | Confirmado |
| F2 | Sem energia, com avaria ou sem acesso ao equipamento: blocos impressos por tipografia, "mediante autorização da Administração Geral Tributária, e num prazo não superior a 45 dias corridos" (art. 7.º, n.º 6, aplicado pelo art. 18.º, n.º 1, b)). | DP n.º 71/25 | Confirmado |
| F3 | "Em caso de falha na comunicação superior a 60 dias, o sistema deve bloquear a emissão de novas facturas" (art. 17.º, n.º 5). O produtor comunica a atividade de dois em dois meses (n.º 4). | DP n.º 71/25 | Confirmado |
| F4 | Fatura rejeitada pela AGT: "para efeitos fiscais, uma determinada factura ou conjunto de facturas não existem". A correção é um documento com estado **C**, que cita `rejectedDocumentNo`. | DE n.º 683/25, Anexo II (p. 19193) e Anexo I (p. 19168) | Confirmado |
| F5 | **Prazo para submeter** os documentos de contingência depois de a ligação voltar; **forma** de avisar a AGT. | — | Não confirmado |
| F6 | Anulação ou retificação por NC com motivo, «anulação»/«rectificação», o documento anulado e a prova de conhecimento do adquirente (art. 8.º, n.º 4–7). Anulação no software, sem NC, se o adquirente estiver mal identificado ou o documento não tiver sido enviado (n.º 8–9). | DP n.º 71/25 | Confirmado |
| F7 | Motivos de anulação na fatura eletrónica: **I** (identificação incorreta do adquirente) e **N** (documento não enviado ao adquirente), com o estado **A – Anulado**. | DE n.º 683/25, Anexo I, `documentCancelReason` (p. 19168) | Confirmado |
| F8 | Os tipos de documento eletrónico incluem **RE – Estorno ou Recibo de Estorno**, **RC – Recibo Emitido**, **RG – Recibo/Outros Recibos**, **NC**, **ND**, **FT**, **FR** e **FG**, entre outros. Estado **R** – "Documento de resumo de outros documentos criados noutras aplicações". | DE n.º 683/25, Anexo I (p. 19168–19169) | Confirmado |
| F9 | Manter por ordem os duplicados e "todos os exemplares dos que tiverem sido anulados ou rectificados, com os averbamentos indispensáveis à identificação daqueles que os substituíram" (art. 39.º, n.º 2). | CIVA (Lei n.º 14/23, de 28/12/2023) — [lex.ao](https://lex.ao/docs/assembleia-nacional/2023/lei-n-o-14-23-de-28-de-dezembro/) | Confirmado |
| F10 | Anular um recibo emitido **antes do SGE** com um documento do software novo que cita o número antigo. | Inferência sobre F6, F8, F9 | Inferido |
| F11 | Numeração "sequencial e cronológica por tipo de documento e o respectivo ano económico, podendo ser utilizadas uma ou mais séries devidamente identificadas" (art. 10.º, n.º 1, b)). | DP n.º 71/25 | Confirmado |
| F12 | "As séries utilizadas pelos contribuintes que emitem facturas em softwares de facturação electrónica são geradas pela Administração Geral Tributária" (art. 4.º). | DE n.º 683/25, de 22/08/2025, DR I Série n.º 159, p. 19164 | Confirmado |
| F13 | `seriesCode` tem de "conter na sua composição o ano de emissão" (2 ou 4 dígitos). Pelo `seriesYear`, de 1 de Janeiro a 15 de Dezembro só se criam séries para o ano do sistema; depois, também para o ano seguinte. `firstDocumentNumber` "normalmente será o número 1". | DE n.º 683/25, Anexo I, serviço `solicitarSerie` (p. 19184) | Confirmado |
| F14 | Estados da série: A – aberta, U – em utilização, **F – "fechada (após expirado o respectivo ano de emissão)"**. | DE n.º 683/25, Anexo I (p. 19187) | Confirmado |
| F15 | **A série segue o ano civil** e não o ano letivo. Uma série por ano letivo (ex.: 2027/2028) não cabe neste modelo. | Inferência sobre F13–F14 | Inferido |
| F16 | Comunicar à AGT "cada série usada e não usada" (art. 24.º, n.º 1, c)) e atualizar "previamente à emissão" sempre que mude (n.º 2). Comunicar também os softwares de cada estabelecimento (n.º 1, b)). | DP n.º 71/25 | Confirmado |
| F17 | "Consideram-se ainda não emitidas as facturas cujas séries não tenham sido comunicadas" (art. 35.º, n.º 4), com coima de 7% ou 15% do valor (n.º 1). | DP n.º 71/25 | Confirmado |
| F18 | Ao mudar de software a meio do ano, começa uma série nova (gerada pela AGT) e a antiga deixa de se usar. Não se continua a numeração do sistema antigo. | Inferência sobre F12, F16 | Inferido |
| F19 | 1.ª impressão com a menção «original»; reimpressão com «2.ª via, em conformidade com a original» (art. 7.º, n.º 4–5). | DP n.º 71/25 | Confirmado |
| F20 | QR code no documento impresso, ligado a `portaldocontribuinte.minfin.gov.ao/consultar-fe?documentNo`. | DE n.º 683/25, Anexo III (p. 19194) | Confirmado |
| F21 | Regra própria para o **original perdido** (de bloco em papel ou impresso). | — | Não confirmado |
| F22 | Arquivar faturas, documentos fiscais e "registos relativos à análise, programação e execução dos tratamentos informáticos" "nos prazos estabelecidos no Código Geral Tributário" (art. 26.º, n.º 1). As cópias digitais ficam disponíveis para consulta imediata (n.º 2). | DP n.º 71/25 | Confirmado |
| F23 | "devem conservar todos os documentos e registos relativos às operações efectuadas nos últimos 5 (cinco) anos" (art. 62.º, n.º 7). Caducidade da liquidação: 5 anos (n.º 1), ou 10 anos em caso de infração (n.º 3). | CGT, Lei n.º 21/14, de 22/10/2014, DR I Série n.º 192, p. 4660 — [lex.ao](https://lex.ao/docs/assembleia-nacional/2014/lei-n-o-21-14-de-22-de-outubro/) | Confirmado |
| F24 | Novo art. 220.º (Conservação de Documentos), n.º 3: "organizar e conservar a sua informação contabilística e fiscal, por um período de 5 anos". Art. 62.º, n.º 3 alterado: 10 anos "quando o retardamento da liquidação tiver resultado de crime tributário". | Lei n.º 21/20, de 09/07/2020, DR I Série n.º 101, p. 3776 — [lex.ao](https://lex.ao/docs/assembleia-nacional/2020/lei-n-o-21-20-de-09-de-julho/) | Confirmado (o lex.ao mostra os números não alterados como "[...]") |
| F25 | Integridade e legibilidade "até ao final do período legal do arquivamento" (art. 19.º, n.º 1). Se houve vários sistemas no prazo de conservação, a documentação de cada um continua acessível (art. 22.º, n.º 5). Cópias de segurança (art. 22.º, n.º 6). | DP n.º 71/25 | Confirmado |
| F26 | Guardar **10 anos** por prudência; contar o prazo a partir do fim do ano civil da operação. | Inferência sobre F23–F24 | Inferido |
| F27 | DE n.º 683/25: assinado a 15/08/2025 pela Ministra das Finanças; publicado a 22/08/2025; "entra em vigor 30 (trinta) dias após a data da sua publicação" (art. 6.º). Os Anexos I a III fazem parte do diploma (art. 2.º). | DR I Série n.º 159, pp. 19164–19165 — fac-símile em [EY Angola](https://www.ey.com/content/dam/ey-unified-site/ey-com/pt-ao/technical/tax-alerts/documents/define-a-estrutura-de-dados-de-software-modelo-de-facturacao-electronica-e-respectivas-especificacoes-tecnicas.pdf) | Confirmado (fac-símile do DR alojado por terceiro) |
| F28 | A AGT inclui o DE n.º 683/25 na sua *Resenha Legislativa* de Janeiro a Agosto de 2025. | AGT, Resenha Legislativa Jan–Ago 2025 — [minfin.gov.ao](https://www.ucm.minfin.gov.ao/cs/groups/public/documents/document/aw40/otkw/~edisp/minfin4990676.pdf) | Confirmado |
| F29 | Modelo de validação *a posteriori*: envio individual ou em lotes (até 30 documentos); validação assíncrona; o adquirente pode validar um documento em 2 meses. Serviços REST/JSON; todos os eventos, erros e alterações são registados. | DE n.º 683/25, Anexos I–III (pp. 19167, 19193–19194) | Confirmado |
| F30 | O DE n.º 683/25 **não tem** regras sobre o processo de certificação ou validação do software. Só exige o campo `softwareValidationNumber` e a assinatura do produtor. | Leitura do articulado (art. 1.º–6.º) | Confirmado (para o articulado) |

## 4. O que não foi possível confirmar

1. **Prazo e forma de envio dos documentos de contingência** à AGT, e o meio de avisar que se está em contingência (F5). Fontes secundárias falam em 40 ou 45 dias, mas os 45 dias da lei são os dos **blocos em papel** (art. 7.º, n.º 6), não os da contingência *offline*.
2. **O resto do Anexo I e as tabelas finais do DE n.º 683/25** (pp. 19170–19183, 19188–19192 e 19196 em diante) **não foram lidos**. Podem conter um campo ou uma regra de contingência, a tabela dos códigos de isenção ou a tabela de erros.
3. **Como a AGT quer anular ou estornar um recibo emitido por outro software ou em papel** (o uso do tipo RE e do estado R). Não há norma explícita (F10).
4. **Regra para o original perdido** (F21) e para os **blocos em papel não usados** do sistema antigo (devolução ou inutilização).
5. **Processo de certificação ou validação do software** pela AGT (requisitos, testes, custos, prazos). Não está no DP n.º 71/25 nem no DE n.º 683/25. Não se identificou o diploma ou o procedimento da AGT que o regula.
6. **Se "ano económico" significa sempre o ano civil** para escolas sem fins lucrativos. O DE n.º 683/25 liga a série ao ano civil na fatura eletrónica, mas não define "ano económico".
7. **Prazos de conservação dos registos escolares não fiscais** (Lei Geral dos Arquivos, Lei n.º 14/17; normas do MED). Estão fora do âmbito desta nota.
8. **Texto consolidado atual do CGT** depois de 2020. Não se encontrou alteração posterior ao art. 62.º ou ao art. 220.º, mas não foi verificado em todas as leis do OGE.
9. **O PDF oficial do DR** foi lido numa cópia alojada pela EY, não no site da Imprensa Nacional.

## 5. Impacto na especificação (implicações, sem decisão)

| Ponto | Onde toca | Implicação |
| :--- | :--- | :--- |
| Contingência (F1–F5) | `RN-09.5`, `RN-10.4`, `RF-C10-10`, `COR-LEG-06`, `DEC-002` | Distinguir os dois casos: (a) *offline* com o software a funcionar — menção «emitido em contingência, pendente de autorização», fila de envio, aviso à AGT, contador para os 60 dias; (b) sem equipamento — blocos em papel autorizados até 45 dias e lançamento posterior. Com a `DEC-002` (b), a contingência é do software certificado e o SGE tem de aceitar documentos "pendentes" e rejeitados (estado C). |
| Anulação de documentos antigos (F6–F10) | `RN-09.1`, `COR-LEG-03`, plano de migração (`MIG-Q14`) | Prever um documento de anulação ou estorno que cite o **número de um documento externo** (de outro software ou de papel), sem o recriar no SGE. Pode ser preciso **matizar a `COR-LEG-03`**: "Nota de Estorno" não existe no DP n.º 71/25, mas o tipo **RE – Estorno ou Recibo de Estorno** existe no DE n.º 683/25. |
| Numeração (F11–F18) | `RF-C10-06`, `RF-C09-06`, `series_numeracao_documental`, `COR-LEG-04`, `Q-004`, `MIG-Q15` | Para os documentos fiscais, a chave da série é **tipo + ano civil**, e não o ano letivo. O código da série vem da AGT ou do software certificado. Os documentos **não fiscais** (matrícula `nnn/AAAA-AAAA`, declarações) podem manter a série por ano letivo. A migração a meio do ano exige uma **série nova comunicada antes** da primeira emissão, e o fecho da série antiga. |
| Documento perdido (F19–F21) | `Q09-17`, `RN-09`, `DOF-11` | Reimpressão com «2.ª via, em conformidade com a original»; nunca reutilizar o número; registar quem reimprimiu e quando. |
| Arquivo (F22–F26) | `MIG-Q37`, `Q08-05`, `09 - Integracoes, Infraestrutura e Operacao`, `10 - Migracao de Dados e Implantacao` | Guardar **pelo menos 5 anos** (10 por prudência) o arquivo em papel, os dados e a documentação técnica do sistema antigo, legíveis e com cópia de segurança. Isto afeta o plano de desligar o sistema antigo e a política de retenção do SGE. |
| DE n.º 683/25 (F27–F30) | `Q-LEG-20`, `DEC-001`, `DEC-002`, LEG-VER §4.5 | A LEG-VER pode passar o DE n.º 683/25 de "fonte secundária" para **texto lido**. Com a opção (a) da `DEC-002`, o SGE teria de implementar a API do Anexo I/III (JWS, séries, QR code). Mesmo assim, o processo de validação do software continua sem fonte. Com a opção (b), o adaptador tem de guardar o `documentNo`, o estado de validação e o QR code devolvidos. |

## 6. Fontes

**Primárias (texto lido):**
1. Decreto Executivo n.º 683/25, de 22 de Agosto (Ministério das Finanças) — Estrutura de dados de *software*, modelo de faturação eletrónica e especificações técnicas e procedimentais. **DR I Série n.º 159, de 22/08/2025, p. 19164 e seguintes.** Fac-símile do DR alojado pela EY Angola: [PDF](https://www.ey.com/content/dam/ey-unified-site/ey-com/pt-ao/technical/tax-alerts/documents/define-a-estrutura-de-dados-de-software-modelo-de-facturacao-electronica-e-respectivas-especificacoes-tecnicas.pdf) (consultado em 2026-11-08). Lidos: art. 1.º–6.º; Anexo I, pp. 19166–19169 e 19184–19187; Anexo II; Anexo III, pp. 19194–19195.
2. Decreto Presidencial n.º 71/25, de 20 de Março — Regime Jurídico das Facturas. DR I Série n.º 52. [lex.ao](https://lex.ao/docs/presidente-da-republica/2025/decreto-presidencial-n-o-71-25-de-20-de-marco/) (2026-11-08). Artigos 7.º, 8.º, 10.º, 17.º–27.º, 35.º–37.º.
3. Lei n.º 21/14, de 22 de Outubro — Código Geral Tributário. DR I Série n.º 192, p. 4660. [lex.ao](https://lex.ao/docs/assembleia-nacional/2014/lei-n-o-21-14-de-22-de-outubro/) (2026-11-08). Artigos 62.º–63.º.
4. Lei n.º 21/20, de 9 de Julho — altera o Código Geral Tributário. DR I Série n.º 101, p. 3776. [lex.ao](https://lex.ao/docs/assembleia-nacional/2020/lei-n-o-21-20-de-09-de-julho/) (2026-11-08). Artigos 62.º e 220.º.
5. Lei n.º 14/23, de 28 de Dezembro — Código do IVA republicado. DR I Série n.º 246. [lex.ao](https://lex.ao/docs/assembleia-nacional/2023/lei-n-o-14-23-de-28-de-dezembro/) (2026-11-08). Artigos 37.º e 39.º.
6. AGT — *Resenha Legislativa, Janeiro a Agosto de 2025*. [minfin.gov.ao](https://www.ucm.minfin.gov.ao/cs/groups/public/documents/document/aw40/otkw/~edisp/minfin4990676.pdf) (2026-11-08).

**Secundárias (só contexto; não sustentam conclusões):**
- EY Angola, *Estrutura de dados do software e do modelo de Faturação Electrónica*, 08/09/2025 — [ey.com](https://www.ey.com/pt_ao/technical/tax-alerts/estrutura-de-dados-do-software-e-do-modelo-de-faturacao-electronica).
- KPMG Angola, *Estrutura de dados do software* — [kpmg.com](https://kpmg.com/ao/pt/insights/tax-news/estrutura-dados-software.html).

**Ligações no cofre:** [[Investigacao - Faturacao AGT (Q-001)|Investigação #19]] · [[Verificacao das Referencias Legais|LEG-VER]] §4 (`COR-LEG-03`, `-04`, `-06`) · [[12.1 - Indice de Questoes em Aberto|IDX-12]] (`Q-LEG-20`, `Q08-06`, `Q09-17`, `MIG-Q14`, `MIG-Q15`, `MIG-Q31`, `MIG-Q37`).
