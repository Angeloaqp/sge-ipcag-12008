---
title: "Síntese das Respostas da Fase B (Entrevistas G-01 a G-14)"
aliases:
  - "Sintese Respostas Fase B"
  - "DESC-RESP"
created: 2026-11-02
updated: 2026-11-02
status: rascunho
version: "0.1"
doc_id: "DESC-RESP"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - descoberta
  - validacao
---

# Síntese das Respostas da Fase B — Entrevistas G-01 a G-14

> [!abstract] Navegação
> - **Fonte:** `SGE - IPCAG N.º 12008_BGO _ Dossiê Consolidado de Respostas da Fase B (DSC-01) (1).pdf` (23 páginas, nesta pasta), que responde ao [[Guiao de Entrevistas por Cargo]].
> - **Relacionado:** [[Achados dos Documentos Reais - Lote 1]] · [[12 - Registo de Decisoes e Questoes em Aberto]] · [[Plano de Validacao de Pautas]] · [[00.1 - Plano de Engenharia de Requisitos]]

> [!warning] Grau de confiança das respostas
> O dossiê consolida as entrevistas, mas várias respostas **repetem as hipóteses e conclusões que nós próprios escrevemos** (por exemplo, citações a `COR-LEG-xx`, ao DP n.º 71/25 e a nomes de campos da base de dados) em vez de relatarem só a prática. Essas partes **não contam como validação independente**. Tratamos como confirmadas pela escola apenas as descrições da prática atual. As fórmulas continuam a precisar do **recálculo de pautas preenchidas** (Fase D) antes de alterar a RN-01.
> Também faltam os números da Parte B por cargo e o detalhe das Partes C e D: o dossiê só os resume.

---

## 1. Avaliação — o que a escola descreve

| Elemento | Resposta da escola | Estado |
| :--- | :--- | :---: |
| Média trimestral (I e II) | `M = (MTP + PP + PT) / 3`, arredondada às unidades | ✅ Descrito por G-02 e G-12 |
| III Trimestre | Só `MTP` e `PP` formam `M3`; a prova do III Trimestre é a **Prova Global (`PG`)** | 🟡 Falta a fórmula de `M3`: `(MTP + PP) / 2`? |
| Classificação de Frequência | `CF` = média dos três trimestres (`M1`, `M2`, `M3`) | ✅ |
| Classificação Anual | **`CA = CF × 0,6 + PG × 0,4`**. O "MT3" impresso na mini-pauta é a `CF` | ✅ |
| Arredondamento | `M1`, `M2`, `M3`, `CF` e `CA` arredondados às unidades; decimal ≥ 0,5 sobe | ✅ Coincide com `round_med` |
| Aprovação | `CA ≥ 10` | ✅ |
| Exame de Recurso | Alunos com `CA < 10` e `CF ≥ 7`; realizado em julho | 🟡 Falta a fórmula da nota depois do recurso |
| Transição com deficiência (10ª e 11ª) | Até **2 disciplinas** com nota de 7 a 9, desde que não reprove ao mesmo tempo Língua Portuguesa e uma disciplina nuclear | ✅ |
| 12ª Classe | Sem Língua Portuguesa e sem transição com deficiência: aprova a todas e tem 0 cadeiras em atraso para passar à 13ª | ✅ |
| Cadeiras em atraso | Eliminam-se em Exame Extraordinário (nota ≥ 10), em maio, até concluir a 12ª; taxa paga por disciplina | ✅ |
| Retenção | O aluno retido repete a classe inteira | ✅ |
| Prova de 2.ª chamada | Quem falta a uma prova por motivo justificado (validado por DT + Coordenação Pedagógica) faz 2.ª chamada; a célula fica pendente até lá | 🆕 Não existe na especificação |
| Provas unificadas | `PT` e `PG` elaboradas pelo Coordenador de Disciplina, com variante A (Manhã), B (Tarde) e uma de 2.ª chamada; visto do Coordenador Pedagógico | 🆕 |
| Comportamento | Nota ou menção de comportamento por trimestre, confirmada no conselho de notas | 🆕 |
| Nomenclatura | `MTP` ≡ `MAC`, `PP` ≡ `NPP`, `PT` ≡ `NPT`. O modelo do Gabinete Provincial usa `MTP`/`PP`/`PT`, o da escola `MAC`/`NPP`/`NPT` | ✅ Um só campo, rótulo configurável |
| 13ª Classe — `MFC` | Hoje junta as médias anuais da 10ª, 11ª e 12ª (Média do Plano Curricular), a nota de Estágio, a de Projecto Tecnológico e a da defesa da PAP | 🟡 **Faltam os pesos** |

---

## 2. Organização da escola

- **Direção:** Comissão de Gestão com uma **Coordenadora Geral** (assina declarações, certificados, guias, atas da PAP, mapas GEPE, despachos de bolsas; dá o visto nas pautas gerais) e um **Coordenador para a Área Pedagógica** (substitui a Coordenadora no expediente pedagógico corrente; **não** pode assinar certificados, pautas gerais finais nem despachos financeiros). Existe também a figura do **Coordenador GIVA** (inserção na vida ativa), ou a sua acumulação pelo Coordenador de Curso.
- **Número da instituição:** a escola usa os dois números (12008 e 8009). A explicação dada para a diferença não é conclusiva. **Continua por confirmar com o Gabinete Provincial** qual é o oficial; o sistema deve guardar ambos e escolher o número por tipo de documento.
- **Cursos:** Contabilidade e Gestão, Gestão de Recursos Humanos, Gestão Empresarial e Estatística e Planeamento, todos da área "Administração e Serviços", especialidade `ADM_GESTÃO`.
- **Prestação de contas:** ao Gabinete Provincial (início do ano, fim de cada trimestre, fim do ano, em papel assinado e em Excel) e à **Diocese de Caxito** (balancetes mensais e trimestrais, fundo social, lista nominal de bolseiros diocesanos).

---

## 3. Calendário real do ano letivo

| Mês | O que acontece |
| :--- | :--- |
| Agosto | Inscrições, exame de admissão à 10ª, confirmações de matrícula, turmas e horários |
| Setembro | Início do I Trimestre (ajustes de horário durante o mês) |
| Novembro–Dezembro | Provas trimestrais e conselhos do I Trimestre; a lista de chamada fica fixa |
| Janeiro–Março/Abril | II Trimestre, provas e conselhos |
| Maio | Exames extraordinários (11ª e 12ª) |
| Maio–Junho | III Trimestre e Prova Global |
| Julho | Exames de recurso, defesas de Projecto Tecnológico e PAP da 13ª, encerramento |

O arranque do SGE tem de acontecer **antes das inscrições e matrículas (agosto/setembro)**, nunca durante as provas ou os conselhos. Isto é coerente com a `DEC-007`.

---

## 4. Requisitos novos ou confirmados pelas entrevistas

| # | Requisito | Origem | Capacidade |
| :---: | :--- | :--- | :---: |
| R1 | Uma falta em tempo duplo conta 2 faltas; tolerância de 10–15 min no 1.º tempo, depois falta nesse tempo | G-02, G-10, G-12 | C05 |
| R2 | Faltas por indisciplina vs. por não comparência; ocorrências disciplinares (advertência, repreensão, suspensão) registadas pelo Coordenador de Turno, com convocatória ao encarregado | G-10, Lote 1 | C05, C13 |
| R3 | A justificação aprovada (DT + Coordenador Pedagógico) **abate a falta automaticamente em todas as disciplinas afetadas**. Hoje o aluno tem de a mostrar a cada professor | G-11, G-14 | C05 |
| R4 | Quem reprova por faltas injustificadas perde a confirmação automática de matrícula (reingresso por despacho) | G-02 | C16 |
| R5 | Confirmação de matrícula pré-gerada para os aprovados, `Pendente` até entregarem documentos; anulada automaticamente 60 dias após o início do ano | G-05 | C03, C16 |
| R6 | Lista da turma por ordem alfabética do **nome completo como no BI**; 40–45 alunos por turma | G-05 | C03 |
| R7 | Alerta de documentos em falta no processo individual (tolerância de 60 dias) | G-05 | C03 |
| R8 | "Problema de saúde" visível só à Direção, à Secretaria Pedagógica e ao Director de Turma | G-04 | C19 |
| R9 | 10 prestações (setembro a junho); setembro pago na matrícula; vencimento fixo (dia 10 ou 15) com multa por mora | G-03 | C10 |
| R10 | Excedente de um talão fica como **crédito** do aluno para o mês seguinte; talão com valor a menos não quita o mês | G-03, G-07 | C10 |
| R11 | Dívidas transitam para o ano seguinte ("Dívida de Exercício Anterior"); um **plano de pagamento** autorizado suspende o bloqueio enquanto estiver em dia | Dossiê §3 | C10, C16 |
| R12 | Boletins de alunos com dívida ficam retidos na reunião de entrega | G-11 | C10 |
| R13 | Fecho de caixa por turno e por canal (TPA, depósito/transferência, Multicaixa Express, RUPE quando aplicável), conferido pela Secretaria Geral e homologado pelo Subdirector Administrativo | G-03, G-06, G-07 | C10 |
| R14 | Documentos fiscais: Fatura, Fatura-Recibo, Recibo e Nota de Crédito (DP n.º 71/25) | G-03 (confirmar com contabilista) | C10 |
| R15 | Emolumentos estatais pagos por RUPE; comparticipações e emolumentos internos nas contas da escola | Dossiê §1 | C10 |
| R16 | Pedido de declaração: requerimento numerado + talão destacável → declaração numerada, prazo até 5 dias úteis; um único balcão que já sabe se o aluno deve | G-04, G-13 | C09 |
| R17 | Livros separados de Termos de Exame, Certificados e Atas da PAP; código e QR da Plataforma Nacional de Certificação | G-04 | C09 |
| R18 | A escola emite o Certificado; o Diploma é do Ministério da Educação (o SGE exporta os dados) | G-01 | C09 |
| R19 | Resposta rápida a pedidos de autenticidade de universidades e empregadores (hoje leva dias) | G-01 A5 | C09 |
| R20 | Defesa da PAP só com estágio concluído, parecer positivo do orientador, 0 cadeiras em atraso e propinas e taxa de defesa pagas | G-08 | C08 |
| R21 | Júri da PAP com membros externos (empresas); tutor interno e supervisor na empresa; lista de empresas parceiras e cartas de apresentação | G-08 | C08 |
| R22 | 6 tempos letivos por turno (45/50 min); sala fixa por turma; laboratórios em escala; reservas pontuais de laboratório | G-10 | C04 |
| R23 | Mais de metade dos professores leciona noutra escola: o horário tem de respeitar a indisponibilidade de cada professor | G-02, G-12 | C04 |
| R24 | Faltas dos professores por tempo letivo registadas pelo Coordenador de Turno; mapa mensal de efetividade exportado para os descontos (salários fora do SGE) | G-06, G-10 | C11 |
| R25 | Registo de correspondência (entrada e saída), `Ofício N.º [seq]/IPCAG.SG/ano` | G-06 | 🆕 Expediente geral (não está no mapa C01–C20) |
| R26 | Avisos por SMS/WhatsApp: 50% e 80% do limite de faltas, propina vencida, notas publicadas, convocatórias; 20–30% dos telefones estão errados | G-11, G-13 | C12 |
| R27 | Boletim e recibo descarregáveis com QR; pautas afixadas sem dados sensíveis | G-13, Dossiê §3 | C12, C19 |
| R28 | Painel semanal da Direção: receita vs. dívida, assiduidade docente e aulas não dadas, alunos em risco por faltas, pedidos pendentes há mais de 3 dias, estado das mini-pautas | G-01 A2 | C15 |
| R29 | Cartão de estudante com fotografia, n.º de processo, curso, classe, turno e QR | G-14, Dossiê §3 | C03 |
| R30 | Backup diário cifrado para a nuvem e para disco externo, no fecho do turno da tarde | Dossiê §3 | C18 |
| R31 | Professores lançam notas no telemóvel sem internet ou em 1–2 PCs da Sala de Professores na rede local | G-12 | C06 |

---

## 5. Números recolhidos

| Indicador | Valor | Fonte |
| :--- | :--- | :--- |
| Alunos | mais de 1.120 | G-01 |
| Alunos por turma | 40–45 | G-05, G-12 |
| Mini-pautas por trimestre | mais de 250 | G-02 |
| Pautas gerais por época | 24–30 | G-01 |
| Turmas por professor | 4–7 | G-12 |
| Duração do conselho de notas | 45–90 min por turma; 3–5 dias no total | G-02 |
| Atendimentos por operador da Secretaria | 25–40/dia normal; 120–200/dia em agosto e setembro | G-05 |
| Pico na Tesouraria | dias 1–15 de cada mês, 08h00–11h00 | G-07 |
| Espera em época alta | 1h30–3h | G-13 |
| Prazo atual de uma declaração | 3–5 dias úteis (mais de uma semana em época alta) | G-04 |
| Assinaturas da Coordenadora Geral | 2–3 h por dia em época de fecho | G-01 |

Faltam ainda: alunos por curso, classe e período; número de professores e funcionários; pagamentos por dia; inventário de equipamentos e rede ([[Questionario de Volumetria e Infraestrutura]]).

---

## 6. O que continua em aberto

1. Fórmula de `M3` (só `MTP` e `PP`) e fórmula da nota depois do Exame de Recurso.
2. Pesos da `MFC` da 13ª Classe (Média do Plano Curricular, Estágio, Projecto Tecnológico, PAP).
3. Qual é o número oficial da instituição (12008 ou 8009), confirmado pelo Gabinete Provincial.
4. Escala do comportamento (qualitativa ou numérica) e se conta para alguma decisão.
5. Validar todas as fórmulas com **pautas preenchidas** do ano anterior ([[Plano de Validacao de Pautas]]).
6. Fazer homologar as decisões `DEC-001`–`DEC-008` pela Comissão de Gestão.
7. Números da Parte B e inventário de infraestrutura.
