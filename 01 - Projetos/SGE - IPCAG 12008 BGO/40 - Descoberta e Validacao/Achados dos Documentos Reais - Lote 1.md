---
title: "Achados dos Documentos Reais da Escola — Lote 1 (2026-11-02)"
aliases:
  - "Achados Documentos Reais Lote 1"
  - "DESC-L1"
created: 2026-11-02
updated: 2026-11-02
status: rascunho
version: "0.1"
doc_id: "DESC-L1"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - descoberta
  - validacao
---

# Achados dos Documentos Reais da Escola — Lote 1

> [!abstract] Navegação
> - **Plano:** [[00.1 - Plano de Engenharia de Requisitos]] (Fase B — Descoberta; lacuna L2)
> - **Especificação afetada:** [[01 - Dominio e Regras]] | [[02 - Fluxos de Trabalho]] | [[04 - Telas e Documentos]] | [[05 - Modelagem de Dados]]
> - **Origem:** 21 fotografias na pasta `imagen_de_doc_da_escola/` (raiz do vault), recebidas a 2026-11-02 — **15 documentos distintos** (há fotografias repetidas).

> [!important] Conclusão principal
> Os documentos reais confirmam o risco central do plano: **a especificação foi escrita a partir da lei e não corresponde à prática da escola em pontos críticos**, sobretudo nas **fórmulas de avaliação** (existe uma *Prova Global* e uma *Classificação Anual* `CA = MT3 × 0,6 + PG × 0,4` que a especificação desconhece), na **estrutura de direção** (Comissão de Gestão) e na **lista de cursos**. Estes pontos têm de ser validados com a escola **antes** de qualquer outra alteração às regras RN-01 e RN-02.

---

## 1. Inventário dos documentos recebidos

| # | Ficheiro(s) `WhatsApp Image 2026-11-02 at …` | Documento | N.º IPCAG no cabeçalho | Corresponde a | Estado |
| :---: | :--- | :--- | :---: | :--- | :--- |
| 1 | `10.07.48` | Boletim de Nota do Estudante — II Trimestre (colunas `MTP`, `PP`, `PT`, `MT`), modelo do Gabinete Provincial com código `DEE-PEEP-001-ACE` | 8009 | `DOF-06` | Modelo em branco |
| 2 | `10.07.51 (3)`, `10.07.52` | Boletim de Notas — II Trimestre (colunas `MAC`, `NPP`, `NPT`, `MT2`) + Faltas por indisciplina, Faltas por não comparência, Comportamento | 8009 | `DOF-06` | Modelo em branco |
| 3 | `10.07.51 (1)`, `10.07.51 (2)` | **Mini Pauta do Professor** (Subdirecção Pedagógica), 45 linhas, com legenda das fórmulas | 8009 | `DOF-04` | Modelo em branco |
| 4 | `10.07.50` | **Pauta de Aproveitamento Geral** (10ª A, Contabilidade e Gestão, Tarde, 2025/2026), 37 linhas, com estatística | 12008 | `DOF-05` | Modelo em branco |
| 5 | `10.07.48 (2)` | Boletim de Matrícula N.º __/2026-2027 + Comprovativo de Matrícula destacável | 12008 | `DOF-03` | Modelo em branco |
| 6 | `10.07.52 (1)` | Boletim de Confirmação de Matrícula N.º __/2026-2027 + Comprovativo destacável | 12008 | `DOF-03` | Modelo em branco |
| 7 | `10.07.48 (3)` | Declaração de Estudante N.º __/IPCAG/2026 (minuta com campos "xxx") | 8009 | `DOF-09` | Minuta |
| 8 | `10.07.49 (3)` | Requerimento de Declaração (à Coordenadora da Comissão de Gestão) + Recibo de Pedido de Declaração destacável | 8009 | Fluxo 08 (pedido) | Modelo em branco |
| 9 | `10.07.48 (1)` | Justificação de Faltas N.º __/IPCAG N.º 8009 BGO/2025 | 8009 | Fluxo 03 / RN-03 | Modelo em branco |
| 10 | `10.07.50 (1)` | Plano Curricular — Técnico de **Contabilidade e Gestão** (MED / DNESTP) | — | Matriz curricular (C01) | Oficial |
| 11 | `10.07.50 (2)` | Plano Curricular (Regular) — Técnico de **Gestão de Recursos Humanos** | — | Matriz curricular (C01) | Oficial, com anotações manuscritas |
| 12 | `10.07.50 (3)` | Plano Curricular — Técnico de **Gestão Empresarial** | — | Matriz curricular (C01) | Oficial |
| 13 | `10.07.51` | Plano Curricular — Técnico de **Estatística e Planeamento** | — | Matriz curricular (C01) | Oficial |
| 14 | `10.07.48 (4)`, `10.07.49` | Ficha de Pedido de Declaração de Serviço — **Secretaria-Geral do Gabinete Provincial da Educação** (pessoal: N.º de Agente, salário, N.º da RUPE) | — | RH (C11) | Modelo do GPE |
| 15 | `10.07.49 (1)`, `10.07.49 (2)` | Avaliação de Desempenho de funcionário (10 indicadores, classificação quantitativa e qualitativa, homologação do GPE) | — | RH (C11) | **Preenchido — contém dados pessoais** (ver §5) |

---

## 2. Divergências com a especificação (por gravidade)

### A1 — Fórmulas de avaliação diferentes do RN-01 (crítico)

**O que os documentos mostram** (Mini Pauta do Professor, legenda impressa):
- Componentes por trimestre: `MTP` = Média de Trabalho Prático, `PP` = Prova do Professor, `PT` = Prova Trimestral; médias trimestrais `M1`, `M2`.
- No **III Trimestre não há `PT`**: as colunas são `MTP`, `PP`, `M3/CF`, seguidas de `PG` = **Prova Global** e `CA` = **Classificação Anual**.
- Fórmula impressa: **`CA = MT3 × 0,6 + PG × 0,4`**.
- A Pauta Geral tem, por disciplina, as colunas `FALT`, `CF`, `PG`, `CA`.

**O que a especificação diz** ([[01 - Dominio e Regras]] RN-01): `MT = (MAC + NPP + NPT) / 3` em todos os trimestres, `MFD = (MT1 + MT2 + MT3) / 3`, e exame de recurso com 40% `MFD` + 60% exame. **Não existem Prova Global, `CF` nem `CA`** em nenhuma das notas DOC-01 a DOC-05.

**Por confirmar com a Subdirecção Pedagógica:**
1. `MT3` na fórmula da `CA` é a média do III Trimestre (`M3`) ou a classificação de frequência anual (`CF`, por exemplo a média de `M1`, `M2` e `M3`)? A coluna chama-se `M3/CF`.
2. Como se calcula `M1`/`M2`/`M3` a partir de `MTP`, `PP` e `PT` (média simples? pesos?) e qual é o arredondamento aplicado.
3. A Prova Global aplica-se a **todas** as disciplinas e classes, ou só às disciplinas que terminam nesse ano (por exemplo, Língua Portuguesa na 11ª)?
4. Continua a existir exame de recurso? Com que fórmula, e como se relaciona com a `CA`?
5. Qual é a nota mínima de aprovação na `CA` e qual o critério de "transita com deficiência"?

**Impacto:** RN-01 e RN-02, máquina de estado 3.4, Fluxos 03–05, `US-PED-04` e `US-PED-06`, `DOF-04`/`DOF-05`/`DOF-06`, tabelas `avaliacoes_trimestrais` e `resultados_anuais_disciplina`. É a **prioridade n.º 1 do Plano de Validação de Pautas**.

### A2 — Duas nomenclaturas em uso para as mesmas notas

Os dois modelos de boletim usam nomes diferentes para as mesmas colunas: `MTP`/`PP`/`PT`/`MT` (modelo do Gabinete Provincial) e `MAC`/`NPP`/`NPT`/`MT2` (modelo da escola). A especificação só conhece `MAC`/`NPP`/`NPT`.
**Decidir:** qual é a nomenclatura oficial a impor na linguagem ubíqua (o Gabinete Provincial parece usar `MTP`/`PP`/`PT`), e se `MAC` ≡ `MTP`.

### A3 — Número da instituição: 12008 ou 8009?

Os documentos de matrícula e a Pauta Geral dizem **N.º 12008**; boletins, mini-pauta, declarações, requerimentos e justificações dizem **N.º 8009**. A especificação inteira usa 12008.
**Confirmar** qual é o número oficial atual, se um substituiu o outro, e qual deve aparecer nos documentos emitidos pelo SGE. É um parâmetro da instituição, não um texto fixo.

### A4 — Estrutura de direção real ≠ cargos do DP n.º 93/21

Os documentos são assinados por: **Coordenadora Geral da Comissão de Gestão** (declarações, "visto" na Pauta Geral; destinatária dos requerimentos), **Coordenador para a Área Pedagógica** (boletins, justificações de faltas, Pauta Geral), **Chefe da Secretaria Pedagógica** (Mini Pauta), **Director de Turma** (chamado "Coordenador de turma" num dos boletins) e "Subdirecção Pedagógica" no cabeçalho da Mini Pauta.
A especificação assume `DIR_GERAL`, `SUB_PED` e `SUB_ADM`.
**Confirmar:** a escola é dirigida, atualmente, por uma Comissão de Gestão (transitória?); que cargos existem de facto e quem assina e homologa cada documento. **Proposta:** separar *papel no sistema* (permissões RBAC) de *título do cargo impresso* (configurável), para que o sistema sobreviva a mudanças de estrutura.

### A5 — Cursos e áreas de formação

Planos curriculares recebidos (todos da **Área de Formação "Administração e Serviços"**): Contabilidade e Gestão, Gestão de Recursos Humanos, Gestão Empresarial, Estatística e Planeamento. A Pauta Geral mostra também um campo **"Especialidade"** (`ADM_GESTÃO`).
O glossário do DOC-01 lista Contabilidade e Gestão, **Informática de Gestão**, **Finanças**, Gestão de RH e **Administração e Serviços** (que é, afinal, a área e não um curso). Gestão Empresarial e Estatística e Planeamento não aparecem.
**Impacto:** criar a entidade **Área de Formação** e o atributo **Especialidade**; corrigir a lista de cursos; confirmar que cursos a escola oferece realmente.

### A6 — 13ª Classe: "Projecto Tecnológico", não "PAP"

Nos quatro planos curriculares, a 13ª Classe tem **uma disciplina, Projecto Tecnológico (8 h/semana), mais o Estágio Curricular Supervisionado (20 h/semana)**. O Projecto Tecnológico começa já na 12ª Classe (2 h/semana). A especificação chama-lhe "PAP" (Prova de Aptidão Profissional).
**Confirmar** a terminologia oficial (PAP é a defesa do Projecto Tecnológico?), como se avalia o Projecto Tecnológico na 12ª e na 13ª, e a fórmula da `MFC`.

### A7 — Língua Portuguesa só existe na 10ª e 11ª Classes

Em todos os planos, Língua Portuguesa (e as outras disciplinas da componente sócio-cultural) só existem na 10ª e 11ª. O **veto "Língua Portuguesa + disciplina nuclear"** da RN-02 só pode aplicar-se nessas classes. **Confirmar** a regra de transição e conclusão na 12ª Classe.

### A8 — Faltas, comportamento e justificação

- O boletim regista **"Faltas por indisciplina"**, **"Faltas por não comparência"** e **"Comportamento"**. A especificação só distingue faltas justificadas e injustificadas e não tem avaliação do comportamento (liga-se à capacidade C13 Disciplina).
- A justificação de faltas é um **formulário numerado** (`N.º __/IPCAG/ano`) preenchido pelo estudante ou encarregado, com intervalo de dias, mês, motivo, documentos em anexo e a lista de professores e cadeiras afetados. É assinado pelo **Director de Turma e pelo Coordenador para a Área Pedagógica**. A RN-03 atribui a justificação apenas ao Director de Turma.

### A9 — Termos usados pela escola

- **"Período"** (Manhã/Tarde) é o termo usado em quase todos os documentos; "Turno" aparece só na Mini Pauta. A especificação usa só "Turno".
- **"Cadeira"** é usado como sinónimo de disciplina ("Disciplinas ou cadeiras").
- "Ano Lectivo" (grafia pré-acordo) aparece nos documentos impressos.

**Proposta:** registar estes termos no glossário como sinónimos aceites nos documentos impressos, mantendo um único termo no sistema.

### A10 — Estatísticas impressas nos documentos

- Mini Pauta, por trimestre: `MT` (matriculados), `AV` (avaliados), `AP` (aprovados), `RP` (reprovados), `NV` (não avaliados). *Hipótese a confirmar:* `MT` aqui significa "matriculados", não "média trimestral".
- Pauta Geral: n.º e % de positivas e de negativas por disciplina; alunos que **transitam**, **transitam com deficiência**, **desistentes** e **não transitam**; coluna **Género**; colunas Observação e Resultado; linhas destacadas a cor (significado por confirmar).

Estes cálculos têm de existir no sistema e alimentam o `DOF-12` (GEPE).

### A11 — Pedido e emissão de declarações

O fluxo real é: **Requerimento numerado** (`Requerente N.º __/IPCAG/ano`) dirigido à Coordenadora da Comissão de Gestão → **Recibo de Pedido de Declaração** destacável, entregue ao estudante → **Declaração de Estudante numerada** (`N.º __/IPCAG/ano`), assinada pela Coordenadora Geral e "autenticada com o carimbo a óleo". A declaração inclui filiação, estado civil, idade, naturalidade, BI e data de emissão, residência, classe, turma, sala, período, curso e o efeito a que se destina.
**Não há campo de pagamento de emolumento** nos formulários. **Confirmar** se há taxa e como se paga.

### A12 — Matrícula e confirmação de matrícula

Campos reais: nome, filiação (pai e mãe), data de nascimento, naturalidade, sexo, n.º do bilhete e data de emissão, **dois telefones do encarregado**, ocupação ou local de trabalho do pai, residência e município, **escola, classe, ano e resultado final anteriores**, **problema de saúde** (dado sensível, ver nota APD), classe, curso e período pretendidos. A confirmação de matrícula pede ainda a turma e sala do ano anterior e **até duas cadeiras em atraso**. Ambas têm **numeração anual** (`N.º __/2026-2027`) e um **comprovativo destacável a conservar "para efeito de reclamação"**.
Serve de entrada direta para a capacidade C03 (processo individual) e para o DOC-05 (`alunos`, `encarregados_educacao`, `matriculas_anuais`).

### A13 — Numeração documental anual por tipo

Quase todos os documentos usam o padrão **`N.º ___/IPCAG N.º <n.º> BGO/<ano>`**, com uma série por tipo de documento e por ano. O sistema tem de gerir séries de numeração configuráveis por tipo de documento.

### A14 — Cabeçalho e rodapé reais

Cabeçalho real: insígnia da República + logótipo da escola; "República de Angola / Governo da Província do Bengo / Gabinete Provincial da Educação / Instituto…". **Não aparecem** "Ministério da Educação" nem "Diocese de Caxito", ao contrário do padrão do `DOC-04`.
Rodapé: endereço (Sector 9, Tecto Vermelho, Panguila), marca "Governo de Angola / gpebengo.gov.ao" e um código de documento (`IPCAG.SG-ACE`, `DEE-PEEP-001-ACE`).
**Confirmar** o modelo oficial a usar e o significado dos códigos.

### A15 — Recursos humanos

- **Avaliação de desempenho anual do pessoal:** 10 indicadores com peso 0,1 cada, nota 0–20 por indicador, classificação quantitativa e qualitativa (por exemplo "Muito Bom"), apreciação do avaliador, concordância do avaliado e homologação pelo Gabinete Provincial. Não está prevista na especificação: alarga a capacidade C11.
- **Ficha de Pedido de Declaração de Serviço** do Gabinete Provincial: o pessoal tem **N.º de Agente** (agentes públicos) e os pedidos usam a **RUPE** (Referência Única de Pagamento ao Estado). **Confirmar** se taxas e emolumentos dos alunos também são pagos por RUPE; isso é relevante para a decisão D5.

### A16 — Dimensão das turmas

A Mini Pauta tem 45 linhas e a Pauta Geral 37; a estatística da Mini Pauta mostra 40 matriculados. Turmas de cerca de 37–45 alunos: um dado útil para os requisitos não funcionais (tempo de abertura da mini-pauta).

---

## 3. Perguntas prioritárias para a escola

| Prioridade | Pergunta | A quem |
| :---: | :--- | :--- |
| 1 | Fórmulas completas de `M1`/`M2`/`M3`, `CF`, `PG` e `CA`, arredondamento, nota mínima e recurso (A1) | Subdirecção Pedagógica / Coordenador para a Área Pedagógica |
| 2 | Nomenclatura oficial das notas: `MTP`/`PP`/`PT` ou `MAC`/`NPP`/`NPT` (A2) | Subdirecção Pedagógica |
| 3 | Número oficial da instituição: 12008 ou 8009 (A3) | Comissão de Gestão |
| 4 | Estrutura de direção atual e quem assina e homologa cada documento (A4) | Comissão de Gestão |
| 5 | Cursos oferecidos, áreas de formação e especialidades (A5) | Secretaria Pedagógica |
| 6 | Projecto Tecnológico vs PAP, avaliação na 12ª e 13ª, `MFC` (A6) | Coordenadores de curso |
| 7 | Regra de transição na 12ª Classe sem Língua Portuguesa (A7) | Subdirecção Pedagógica |
| 8 | Faltas por indisciplina, avaliação do comportamento e circuito de justificação (A8) | Directores de turma |
| 9 | Emolumentos de declarações e uso da RUPE (A11, A15) | Secretaria Pedagógica / Tesouraria |
| 10 | Significado das linhas destacadas e da sigla `MT` na estatística (A10) | Secretaria Pedagógica |

---

## 4. Impacto na especificação (a integrar depois da validação)

| Nota | Alterações previstas |
| :--- | :--- |
| [[01 - Dominio e Regras]] | Glossário: `MTP`, `PP`, `PT`, `PG`, `CF`, `CA`, Área de Formação, Especialidade, Projecto Tecnológico, sinónimos Período/Turno e Cadeira/Disciplina. RN-01 e RN-02 reescritas após A1/A7. RBAC: papéis vs títulos configuráveis (A4). Lista de cursos (A5). |
| [[02 - Fluxos de Trabalho]] | Fluxo 03 (justificação de faltas com Coordenador Pedagógico), Fluxo 04 (Prova Global e `CA`), Fluxo 08 (requerimento → recibo de pedido → declaração). |
| [[04 - Telas e Documentos]] | Cabeçalho e rodapé reais (A14); `DOF-03`, `DOF-04`, `DOF-05`, `DOF-06` e `DOF-09` alinhados com os modelos recebidos; estatísticas impressas (A10); numeração anual por série (A13). |
| [[05 - Modelagem de Dados]] | Entidade `areas_formacao`; especialidade no curso ou na turma; colunas `PG`, `CF` e `CA`; tipos de falta (indisciplina, não comparência); comportamento; séries de numeração documental; campos reais da matrícula (A12). |
| `Capacidades Novas/` | C03 (campos da matrícula), C11/RH (avaliação de desempenho), C13 (comportamento). |

---

## 5. Proteção de dados — ação necessária

> [!warning] Dados pessoais na pasta `imagen_de_doc_da_escola/`
> As fotografias `10.07.49 (1)` e `10.07.49 (2)` são uma **avaliação de desempenho preenchida, com o nome de um funcionário, a assinatura do avaliador e comentários pessoais**. A Pauta Geral tem também o nome de uma responsável impresso. Recomenda-se **retirar do vault a avaliação de desempenho** (ou rasurar nome e assinaturas) e, nos próximos lotes, pedir apenas **modelos em branco ou cópias anonimizadas** (Lei n.º 22/11). Esta nota não reproduz nenhum desses dados.

---

## 6. Artefactos do plano (§5.2) — situação após o Lote 1

| Artefacto | Situação |
| :--- | :--- |
| Mini-pautas, pautas gerais e boletins | 🟡 **Só modelos em branco.** Para a validação das fórmulas (A1) são precisos exemplares **preenchidos e homologados** do ano anterior, anonimizados |
| Pauta e edital do concurso de admissão | ❌ Em falta |
| Ficha de matrícula e lista de documentos exigidos | 🟡 Ficha recebida; falta a lista de documentos a entregar |
| Recibos, borderôs, mapa de caixa, tabela de propinas e emolumentos | ❌ Em falta |
| Regras de bolsas, isenções e descontos | ❌ Em falta |
| Livro de termos (Livro/Folha/Termo) | ❌ Em falta |
| Modelos de declaração, certificado, diploma e guia de transferência | 🟡 Declaração recebida; faltam certificado, diploma e guia |
| Regulamento interno | ❌ Em falta |
| Matrizes curriculares | ✅ 4 cursos recebidos (confirmar se são todos) |
| Horário semanal e distribuição de serviço | ❌ Em falta |
| Último mapa estatístico GEPE | ❌ Em falta |
| Volumetria e infraestrutura | ❌ Em falta |
