---
title: "Investigação — Plataforma Nacional de Certificação (ticket 26)"
created: 2026-11-08
status: rascunho
tags: [sge, ipcag-12008, investigacao, med]
---

# Investigação — Plataforma Nacional de Certificação (ticket #26)

> Junta `Q-020`, `Q-LEG-14` e `Q09-18` ([#26](https://github.com/Angeloaqp/sge-ipcag-12008/issues/26)). Estende `COR-LEG-18` a `COR-LEG-20` da [[Verificacao das Referencias Legais]]; não repete o que lá está. Pesquisa feita em 2026-11-08, só com fontes públicas na Internet. **Ninguém do MED, do INADE nem da Direção Provincial foi contactado.**

## Pergunta

1. A Plataforma Nacional de Certificação (DP n.º 227/25) já está em funcionamento?
2. Como se registam os certificados e os pedidos de diploma (quem, que dados, que prazo)?
3. Há integração (API, importação de ficheiro) ou só registo manual?
4. O QR oficial dos títulos substitui o QR próprio do SGE?
5. O que isto implica para o SGE (exportação manual ou integração)?

## Resposta curta por questão

| Id | Resposta curta | Confiança |
| :--- | :--- | :--- |
| `Q09-18` / `Q-LEG-14` (funciona?) | **Não confirmado.** O DP n.º 227/25 está em vigor desde 14/11/2025, mas não marca data de arranque da plataforma nem tem disposição transitória. Não se encontrou nenhum portal público com o nome "Plataforma Nacional de Certificação". O único sinal de funcionamento é o **Decreto Executivo n.º 81/26** (exames nacionais 2025-2026), que manda emitir certificados e diplomas "através da **PGDEN**" — a Plataforma de Gestão de Dados dos Exames Nacionais, gerida pelo INADE. Esse decreto só cobre a 6.ª, 9.ª e 12.ª classes do **Ensino Secundário Geral** e a EJA; **não cobre o ensino técnico-profissional nem a 13.ª classe**. | Média (sobre a lei); baixa (sobre o funcionamento real) |
| `Q-020` / `Q-LEG-14` (como se regista?) | **Quem:** a instituição de ensino acreditada (art. 13.º, n.º 1–2 do Regulamento). A lei não diz que cargo dentro da escola. **Que dados:** "todo o histórico avaliativo dos alunos" e a informação sobre os alunos com atestados, certificados e diplomas (art. 13.º, n.º 2); os elementos obrigatórios do título estão no art. 8.º, n.º 1 (inclui **identificador único do aluno**, n.º do BI, nacionalidade, filiação, disciplinas e notas, média final, nível do QNQ). **Prazo:** até 30 dias após o fim do ano letivo (art. 13.º, n.º 2). **Pedido do diploma:** a lei só regula o pedido do aluno/encarregado ao Director da escola ou "através da plataforma de gestão de dados" (art. 10.º, n.º 1), formalizado após pagamento por RUPE (art. 10.º, n.º 4). **Não há** procedimento escola → Ministério para o diploma. | Alta (texto da lei); o pedido escola → Ministério fica sem resposta |
| `Q-020` (integração?) | **Não há** API, formato de ficheiro, nem especificação técnica publicada. A lei fala só em "sistema informático" de verificação em tempo real (art. 3.º, f)), "ferramentas digitais e sistemas online" (art. 3.º, h)) e "livro de registo e/ou base de dados" (art. 13.º, n.º 1). O n.º do documento pode vir "da plataforma de gestão de dados **ou** de outro sistema de controle" da escola (art. 4.º, l)). | Alta quanto à ausência nos textos lidos; não se sabe se existe documentação interna do MED/INADE |
| `Q-020` / `RN-10.3` (QR) | **Sim, para os títulos.** Atestados, certificados e diplomas devem ter n.º sequencial, código alfanumérico e o **código QR disponibilizado pela Plataforma Nacional de Certificação** (art. 8.º, n.º 3). As **declarações** não aparecem nesse número; boletins, guias e restantes documentos também não são títulos. Aí o QR próprio do SGE continua possível. | Alta (texto); a forma como a plataforma entrega o QR não é conhecida |
| Implicações | Partir de **registo e exportação manuais**, com campos para guardar o n.º, o código e o QR que a plataforma der; a **integração (C18) fica condicional** até haver especificação oficial. Detalhe em §Impacto. | Inferido |

## Evidência

| Ponto | Fonte | Estado |
| :--- | :--- | :--- |
| DP n.º 227/25 aprova o Regulamento sobre a Atribuição e Emissão de Títulos Escolares; DR I Série n.º 216, de 14/11/2025; entra em vigor na data da publicação; sem disposições transitórias | [lex.ao — DP n.º 227/25](https://lex.ao/docs/presidente-da-republica/2025/decreto-presidencial-n-o-227-25-de-14-de-novembro/) (consultado 2026-11-08) | Confirmado |
| QR Code "disponibilizado por uma Plataforma Nacional de Certificação concebida pelo Departamento Ministerial", "para solicitação, emissão, verificação e armazenamento seguro de dados escolares"; obrigatório em atestados, certificados e diplomas | DP n.º 227/25, Regulamento, art. 8.º, n.º 3 | Confirmado |
| Elementos obrigatórios do título (al. a) a q)), incluindo identificador único do aluno e nível do QNQ | DP n.º 227/25, Regulamento, art. 8.º, n.º 1 | Confirmado |
| Livro de registo e/ou base de dados; inserir na plataforma o histórico avaliativo e os dados dos titulados até 30 dias após o fim do ano letivo | DP n.º 227/25, Regulamento, art. 13.º, n.º 1–2 | Confirmado |
| Pedido feito pelos pais/encarregados ou pelo aluno maior, ao Director ou pela "plataforma de gestão de dados"; formalizado após pagamento RUPE | DP n.º 227/25, Regulamento, art. 10.º, n.º 1 e 4 | Confirmado |
| Títulos emitidos e registados pela escola, em formato físico ou digital; emissão no período do Calendário Escolar Nacional | DP n.º 227/25, Regulamento, art. 9.º, n.º 4–5 | Confirmado |
| N.º do documento atribuído "pela plataforma de gestão de dados ou por outro sistema de controle" da escola | DP n.º 227/25, Regulamento, art. 4.º, l) | Confirmado |
| Sem menção a API, interoperabilidade ou formato de ficheiro | DP n.º 227/25 (texto integral em lex.ao) | Confirmado (ausência no texto) |
| Diploma assinado pelo Titular do Departamento Ministerial da Educação | DP n.º 227/25, Regulamento, art. 4.º, h); já em `COR-LEG-18` | Confirmado |
| Modelos e elementos de segurança dos títulos a aprovar por "acto próprio" do Ministro | DP n.º 227/25, Regulamento, art. 7.º e 8.º, n.º 2, 5 e 7 | Confirmado (o ato) · Não encontrado (o ato publicado) |
| "Compete às instituições de ensino [...] a emissão dos certificados e diplomas através da PGDEN e a respectiva assinatura, nos termos [...] do DP n.º 227/25" | [AngoLEX — Decreto Executivo n.º 81/26](https://angolex.com/paginas/decreto-executivo/regulamento-dos-exames-nacionais-para-o-ano-lectivo-2025a-2026a-81a-26a.html), art. 23.º (data de publicação não visível na página; não indexado no lex.ao) | Confirmado (texto na AngoLEX, fonte secundária do DR) |
| PGDEN = "Plataforma de Gestão de Dados dos Exames Nacionais"; concebida e gerida pelo INADE com o Júri dos Exames Nacionais | DE n.º 81/26, art. 3.º, r) e art. 24.º, c) | Confirmado |
| Âmbito do DE n.º 81/26: 6.ª, 9.ª e 12.ª classes do Ensino Secundário Geral, Módulo 3 e 2.º ano da EJA; sem ensino técnico-profissional | DE n.º 81/26, art. 1.º e 2.º | Confirmado |
| A PGDEN é a "Plataforma Nacional de Certificação" do DP n.º 227/25 | Nenhuma fonte o diz; o DE n.º 81/26 liga a emissão à PGDEN e cita o DP n.º 227/25 | Inferido (plausível, não confirmado) |
| Portal público da PGDEN mostra escolas selecionadas e calendário 2025/2026; não mostra verificação de QR, emissão de certificados, API nem ensino técnico-profissional | [examenacional.ao](https://www.examenacional.ao/) (consultado 2026-11-08) | Confirmado (o que a página pública mostra) |
| INADE: inscrição na PGDEN obrigatória; objetivo "certificar alunos da 6.ª, 9.ª e 12.ª classes"; sem menção à Plataforma Nacional de Certificação | [INADE — Exames Nacionais](https://inade.gov.ao/exames-nacionais) (consultado 2026-11-08) | Confirmado |
| A plataforma está a ser usada pelas escolas do ESTP (13.ª classe) | — | Não confirmado |
| Antecedente: SIUGEP (2018), sistema do MED para emitir certificados nas escolas públicas, com código de barras | [Observador, 12/12/2018](https://observador.pt/2018/12/12/escolas-publicas-angolanas-com-sistema-integrado-para-certificacao-de-documentos/) (imprensa) | Confirmado como notícia; estado atual não confirmado |

## O que não foi possível confirmar

- **Se a Plataforma Nacional de Certificação existe com esse nome e está aberta às escolas.** Não se encontrou portal, notícia do MED nem ato ministerial que a ponha em funcionamento.
- **Se a PGDEN é essa plataforma.** O DE n.º 81/26 manda emitir certificados "através da PGDEN", mas não usa a expressão "Plataforma Nacional de Certificação".
- **Se a PGDEN (ou outra plataforma) cobre o ensino técnico-profissional e a 13.ª classe.** O DE n.º 81/26 não cobre o ESTP. Não se encontrou regulamento equivalente para o ESTP.
- **A data e o DR do DE n.º 81/26.** A página da AngoLEX não os mostra e o índice do lex.ao não o lista. Falta conferir no Diário da República.
- **O ato do Ministro com os modelos e os elementos de segurança** (art. 7.º e 8.º do Regulamento). Não encontrado.
- **Como a escola pede o diploma ao Ministério** (canal, formulário, prazo). Nem o DP n.º 227/25 nem o DP n.º 167/23 o regulam (`Q-021`).
- **Que cargo da escola faz o registo** e se é por digitação, por importação de ficheiro ou por API.
- **Como a plataforma entrega o QR e o código alfanumérico** (gerado por título, por lote, impresso pela plataforma?).
- O portal do MED (med.gov.ao) não devolveu nada sobre o tema nas pesquisas feitas.

**Quem pode confirmar:** Direção Provincial da Educação do Bengo e INADE (contacto no portal examenacional.ao). Perguntas sugeridas: (1) a plataforma do art. 8.º, n.º 3 já está aberta às escolas do ESTP?; (2) é a PGDEN?; (3) como se inserem os dados (formulário, ficheiro, API) e quem na escola tem conta?; (4) como se pede o diploma da 13.ª classe?

## Impacto na especificação

> Só implicações. As decisões ficam para a revisão da C09/C18 e para a homologação em E1 (`DEC-009`).

- **C09 (documentos oficiais):**
  - O `DOF-10A` (Certificado) é título escolar: deve ter n.º sequencial, código alfanumérico e o **QR da Plataforma Nacional de Certificação** (art. 8.º, n.º 3). O SGE precisa de **campos para guardar** esse n.º/código/QR quando vierem de fora, e de reservar o lugar do QR no modelo.
  - Enquanto a plataforma não estiver disponível para o ESTP, o QR próprio (`RN-10.3`, HMAC) é o único meio de verificação, mas não cumpre sozinho o art. 8.º, n.º 3. Convém marcar no documento qual QR foi usado.
  - Declarações (`DOF-09A/B`), boletins e guias não são títulos: o QR próprio mantém-se aí.
  - O art. 4.º, l) permite que o n.º do documento venha "de outro sistema de controle" da escola: a numeração própria do Livro de Certificados (`RN-10.2`) é compatível com a lei.
- **C18 (integrações):** não há API nem formato publicado. Uma integração com a plataforma nacional **não pode ser especificada agora**; fica como item condicional, dependente de documentação do MED/INADE. O que se pode especificar já é uma **exportação** do histórico avaliativo e dos titulados (por aluno, com identificador único do aluno e os elementos do art. 8.º, n.º 1), em PDF e num formato tabular, para digitação ou carregamento manual.
- **`DOF-10` (`DOF-10A` e `DOF-10B`):**
  - `DOF-10A`: o registo na plataforma nacional (até 30 dias após o fim do ano letivo) é uma **obrigação da escola**, não do SGE. O SGE pode ajudar com um alerta de prazo e um estado "registado na plataforma: sim/não, data, quem".
  - `DOF-10B`: o canal do pedido do Diploma continua desconhecido (`Q-021`). Se a PGDEN vier a servir o ESTP, o diploma pode passar a ser pedido/emitido por ela (como no DE n.º 81/26 para o ensino geral), e o `DOF-10B` passa a ser só uma ficha de conferência interna.
  - O **identificador único do aluno** (art. 8.º, n.º 1) é atribuído fora da escola: o SGE precisa de um campo para ele.
- **E4:** a entrega que traz títulos e documentos deve contar com **registo e exportação manuais** como base. A integração só entra se, até lá, houver especificação oficial; caso contrário, passa para depois.

## Fontes

- Decreto Presidencial n.º 227/25, de 14 de Novembro — Regulamento sobre a Atribuição e Emissão de Títulos Escolares. DR I Série n.º 216, de 14/11/2025. <https://lex.ao/docs/presidente-da-republica/2025/decreto-presidencial-n-o-227-25-de-14-de-novembro/> (consultado 2026-11-08).
- Decreto Executivo n.º 81/26 — Regulamento dos Exames Nacionais para o Ano Lectivo 2025-2026 (texto na AngoLEX; data e DR por confirmar). <https://angolex.com/paginas/decreto-executivo/regulamento-dos-exames-nacionais-para-o-ano-lectivo-2025a-2026a-81a-26a.html> (consultado 2026-11-08).
- PGDEN — Plataforma de Gestão de Dados dos Exames Nacionais (MED/INADE). <https://www.examenacional.ao/> (consultado 2026-11-08).
- INADE — Exames Nacionais. <https://inade.gov.ao/exames-nacionais> (consultado 2026-11-08).
- lex.ao — índice de diplomas de 2026 (sem atos sobre títulos escolares ou a plataforma). <https://lex.ao/llms/2026.txt> (consultado 2026-11-08).
- Observador, 12/12/2018 — SIUGEP (contexto histórico, imprensa). <https://observador.pt/2018/12/12/escolas-publicas-angolanas-com-sistema-integrado-para-certificacao-de-documentos/>
- Notas do vault: [[Verificacao das Referencias Legais]] (`COR-LEG-18` a `20`); [[04 - Telas e Documentos]] (`DOF-10`); [[12.1 - Indice de Questoes em Aberto]] (`Q-020`, `Q-LEG-14`, `Q09-18`).
