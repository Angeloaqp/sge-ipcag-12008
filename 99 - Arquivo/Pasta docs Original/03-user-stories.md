# Documento 03: User Story Mapping, Épicos, Histórias de Utilizador e Critérios de Aceitação (BDD)

**Projeto:** Sistema de Gestão Escolar (SGE) — Ensino Secundário Técnico-Profissional (II Ciclo)  
**Instituição Alvo:** Instituto Politécnico Católico de Administração e Gestão (IPCAG) N.º 12008 / BGO – *"Nossa Senhora do Rosário"*  
**Referências Base:** [01-dominio-e-regras.md](file:///c:/Users/aqp/Desktop/sge/docs/01-dominio-e-regras.md) (`RN-01` a `RN-10`, RBAC DP n.º 93/21, 7 Máquinas de Estado) e [02-fluxos-de-trabalho.md](file:///c:/Users/aqp/Desktop/sge/docs/02-fluxos-de-trabalho.md) (`Fluxo 01` a `Fluxo 08`)

---

## Visão Geral do User Story Mapping (MVP IPCAG N.º 12008 / BGO)

| Código do Épico | Nome do Épico / Domínio Funcional | Perfis RBAC Principais | Histórias de Utilizador (`US`) | Regras de Negócio Cobertas |
| :---: | :--- | :--- | :---: | :---: |
| **`EP-GOV`** | **Épico 01:** Governação, Configuração do Ano Letivo, Matrizes Curriculares e Auditoria de Exceção | `DIR_GERAL`, `SUB_PED`, `SUB_ADM` | `US-GOV-01` a `US-GOV-04` (4 US) | `RN-01`, `RN-02`, `RN-03`, `RN-06`, `RN-10` |
| **`EP-ADM`** | **Épico 02:** Concurso de Admissão à 10ª Classe e Gestão de Anonimato (DE n.º 361/26) | `OP_PED`, `CHEFE_SEC_PED`, `OP_TES`, `SUB_PED`, `DIR_GERAL` | `US-ADM-01` a `US-ADM-04` (4 US) | `RN-01`, `RN-08`, `RN-09`, `RN-10` |
| **`EP-MAT`** | **Épico 03:** Matrículas, Confirmações, Chamada Congelada e Transcrição de Histórico Externo | `OP_PED`, `CHEFE_SEC_PED`, `SUB_PED`, `OP_TES` | `US-MAT-01` a `US-MAT-04` (4 US) | `RN-02`, `RN-05`, `RN-06`, `RN-07`, `RN-08` |
| **`EP-PED`** | **Épico 04:** Gestão Pedagógica Trimestral, Mini-Pauta *Offline-First*, Faltas, `DISP`, Substituição Docente e Conselho de Notas | `COORD_DISC`, `PROF`, `DIR_TURMA`, `SUB_PED`, `DIR_GERAL` | `US-PED-01` a `US-PED-06` (6 US) | `RN-01`, `RN-02`, `RN-03`, `RN-04`, `RN-05`, `RN-10` |
| **`EP-DEF-13`** | **Épico 05:** Gestão de Cadeiras em Atraso (Exame Extraordinário) e Regime Especial da 13ª Classe (Estágio + PAP + `MFC`) | `OP_PED`, `CHEFE_SEC_PED`, `COORD_CURSO`, `PROF`, `SUB_PED`, `DIR_GERAL` | `US-DEF-01` a `US-13C-02` (4 US) | `RN-01`, `RN-02`, `RN-06`, `RN-08`, `RN-10` |
| **`EP-TES`** | **Épico 06:** Tesouraria Anti-Fraude (Borderô por Saldo), Motor de Bolsas, Notas de Estorno AGT e Fecho de Caixa por Turno | `SUB_ADM`, `DIR_GERAL`, `OP_TES`, `CHEFE_SEC_GER` | `US-TES-01` a `US-TES-05` (5 US) | `RN-07`, `RN-08`, `RN-09`, `RN-10` |
| **`EP-DOC-AUD`** | **Épico 07:** Emissão Documental Oficial, Semáforo Financeiro, `Livro/Folha/Termo`, QR Code, RH e Estatísticas GEPE/MED | `OP_PED`, `CHEFE_SEC_PED`, `CHEFE_SEC_GER`, `COORD_TURNO`, `DIR_GERAL` | `US-DOC-01` a `US-DOC-05` (5 US) | `RN-05`, `RN-08`, `RN-10` |

---

## ÉPICO 01 (`EP-GOV`): Governação, Configuração do Ano Letivo, Matrizes Curriculares e Auditoria de Exceção

---

### `US-GOV-01`: Configurar e Homologar Ano Letivo e Calendário dos 3 Trimestres Letivos
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **criar o Ano Letivo e parametrizar as janelas temporais do I, II e III Trimestres e das épocas de Exame de Recurso e Exame Extraordinário**, *para* **garantir que todas as operações de matrícula e avaliação respeitem estritamente o Calendário Escolar Nacional do MED**.
- **Rastreabilidade:** `RN-01`, `RN-05`, `RN-10` | `Fluxo 01` e `Fluxo 04`.
- **Pré-condições:** Utilizador autenticado com perfil `SUB_PED` ou `DIR_GERAL`; inexistência de outro Ano Letivo com o mesmo código (ex.: `2026/2027`).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Criação e Homologação do Ano Letivo):**
    - **Dado** que o `SUB_PED` preenche o código `2026/2027`, data de início `01/09/2026`, data de fim `31/07/2027` e os intervalos do I, II e III Trimestres sem sobreposição de datas,
    - **Quando** submete a configuração e o `DIR_GERAL` aciona a homologação,
    - **Então** o Ano Letivo é criado com os 3 trimestres no estado `Planeado`, permitindo abrir apenas o `I Trimestre` inicialmente.
  - **Cenário 2 (Bloqueio — Tentativa de Abrir o II ou III Trimestre sem Fechar o Anterior):**
    - **Dado** que o `I Trimestre` ainda se encontra no estado `Aberto / Em Curso` ou `Em Conselho de Notas`,
    - **Quando** o `SUB_PED` tenta alterar o estado do `II Trimestre` para `Aberto / Em Curso`,
    - **Então** o sistema bloqueia a operação com erro `HTTP 422 Unprocessable Entity`: *"Não é permitido abrir o II Trimestre enquanto o I Trimestre não estiver no estado Fechado / Homologado"*.
  - **Cenário 3 (Segurança RBAC):**
    - **Dado** um utilizador com perfil `CHEFE_SEC_PED`, `OP_PED` ou `PROF`,
    - **Quando** tenta criar ou alterar datas de trimestres,
    - **Então** a API rejeita a requisição com `HTTP 403 Forbidden`.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `anos_letivos` e `trimestres_letivos`; evento `ANO_LETIVO_HOMOLOGADO` registado em `audit_logs`.

---

### `US-GOV-02`: Configurar Cursos Técnicos, Classes (10ª–13ª) e Matrizes Curriculares do MED
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **configurar os Cursos Técnicos e as respetivas Matrizes Curriculares da 10ª à 13ª classe (classificando componentes, disciplinas nucleares, tempos letivos semanais e pesos da `MFC`)**, *para* **assegurar o cumprimento automático das regras de retenção por faltas (`RN-03`), veto de transição (`RN-02`) e cálculo da Média Final do Curso (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-02`, `RN-03`, `RN-06` | `Fluxo 01`, `Fluxo 03`, `Fluxo 04`, `Fluxo 06`.
- **Pré-condições:** Curso Técnico ativo no catálogo do IPCAG N.º 12008 / BGO (Administração, Contabilidade e Gestão, Finanças, Informática de Gestão, Recursos Humanos ou Serviços).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Definição de Matriz Curricular da 10ª à 12ª Classe):**
    - **Dado** que o `SUB_PED` seleciona o curso *Técnico de Informática de Gestão* — `10ª Classe`,
    - **Quando** adiciona as disciplinas classificando cada uma na componente `SOCIO_CULTURAL`, `CIENTIFICA` ou `TECNICA_TECNOLOGICA_PRATICA`, define `is_nuclear = TRUE` para as cadeiras específicas, `permite_dispensa_medica = TRUE` para *Educação Física*, e informa `tempos_letivos_semanais` (ex.: `4` tempos/semana) e o fator multiplicador de faltas,
    - **Então** o sistema calcula e armazena automaticamente o `limite_max_faltas_injustificadas` anual de cada disciplina e ativa a matriz após homologação do `DIR_GERAL`.
  - **Cenário 2 (Sucesso — Configuração do Regime Especial da 13ª Classe):**
    - **Dado** que o `SUB_PED` configura a `13ª Classe` de um Curso Técnico,
    - **Quando** define a obrigatoriedade de `Estágio Curricular Supervisionado` e `Prova de Aptidão Profissional (PAP)` com os respetivos pesos para a fórmula da `MFC`,
    - **Então** o sistema desativa a geração de Mini-Pautas trimestrais comuns para a 13ª classe e habilita exclusivamente o módulo de Estágio e PAP.
  - **Cenário 3 (Bloqueio — Alteração de Matriz com Notas Já Lançadas):**
    - **Dado** que uma Matriz Curricular já possui turmas com avaliações registadas no Ano Letivo corrente,
    - **Quando** o `SUB_PED` tenta remover uma disciplina ou alterar o flag `is_nuclear`,
    - **Então** o sistema bloqueia a edição direta (`HTTP 409 Conflict`), exigindo a criação de uma nova versão de matriz para o próximo Ano Letivo.
- **Pós-condições e Efeitos Colaterais:** Tabelas `cursos_tecnicos`, `matrizes_curriculares` e `matriz_disciplinas` populadas e versionadas.

---

### `US-GOV-03`: Configurar e Abrir Turmas por Turno (Manhã/Tarde) nas 12 Salas e Laboratórios
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) ou Subdirector Pedagógico (`SUB_PED`)**, *quero* **criar as Turmas de cada Curso e Classe associando-as a um Turno (`Manhã` ou `Tarde`), a uma das 12 salas de aula físicas e a um Director de Turma (`DIR_TURMA`)**, *para* **organizar a capacidade de +1.120 alunos sem conflitos de ocupação de salas**.
- **Rastreabilidade:** `RN-04`, `RN-05` | `Fluxo 01` e `Fluxo 02`.
- **Pré-condições:** Ano Letivo e Matrizes Curriculares criados; cadastro das 12 salas e laboratórios disponível.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Criação de Turma e Geração Automática de Mini-Pautas):**
    - **Dado** que o `CHEFE_SEC_PED` cria a turma `CG11A-M` (Contabilidade e Gestão, 11ª Classe, Turno Manhã, Sala 04, lotação máxima `45` alunos) e nomeia o docente titular como `DIR_TURMA`,
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
- **Pré-condições:** Pauta no estado `Fechado / Homologado`; utilizador autenticado exclusivamente como `SUB_PED` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Reabertura com Despacho e Gravação de `old_value` / `new_value`):**
    - **Dado** que a Mini-Pauta de *Matemática* da turma `IG10A-M` (I Trimestre) está `Fechada / Homologada`,
    - **Quando** o `SUB_PED` seleciona *"Reabrir por Ordem da Direção"*, informa o `N.º do Despacho = DESP-PED-014/2026`, a justificativa detalhada (mínimo 30 caracteres), o aluno/disciplina alvo e o prazo de `4 horas`, e corrige a `NPT` do aluno de `11` para `14` (inclusive avocando o lançamento caso o professor titular já tenha saído da escola — `RN-04.1`),
    - **Então** apenas aquela Mini-Pauta (`turma_disciplina_id`) muda para `Reaberto Temporariamente` (sem reabrir as restantes turmas da escola), recalcula `MT` e `MFD` via `round_med`, grava em `audit_logs` um registo imutável contendo `usuario_id`, `ip_origem`, `despacho_num`, `justificativa`, `valor_antigo_jsonb: {"npt": 11, "mt": 12}` e `valor_novo_jsonb: {"npt": 14, "mt": 13}`, e ao clicar em *"Trancar"* (ou expirar as 4 horas) retorna ao estado `Fechado / Homologado` incrementando `versao_pauta`.
  - **Cenário 2 (Bloqueio — Tentativa de Reabertura sem Justificativa ou por Cargo Não Autorizado):**
    - **Dado** que um `CHEFE_SEC_PED`, `DIR_TURMA` ou `PROF` tenta reabrir ou editar uma pauta fechada (ou o `SUB_PED` omite o número do despacho),
    - **Então** o sistema bloqueia a operação (`HTTP 403 Forbidden` ou `HTTP 422 Unprocessable Entity`) e regista a tentativa negada no log de segurança.
- **Pós-condições e Efeitos Colaterais:** Pauta atualizada para nova versão (`versao_pauta + 1`), médias recalculadas e entrada permanente gravada em `audit_logs`.

---

## ÉPICO 02 (`EP-ADM`): Concurso de Admissão à 10ª Classe e Gestão de Anonimato (DE n.º 361/26)

---

### `US-ADM-01`: Inscrever Candidato ao Teste de Admissão da 10ª Classe e Emitir Guia de Emolumento
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **registar a inscrição de candidatos ao Teste de Seleção da 10ª classe validando o Bilhete de Identidade e a conclusão da 9ª classe**, *para* **iniciar o processo seletivo oficial nos termos do Decreto Executivo n.º 361/26 e 136/24**.
- **Rastreabilidade:** `RN-08`, `RN-09` | `Fluxo 01`.
- **Pré-condições:** Concurso de Admissão do Ano Letivo aberto; tabela de emolumentos configurada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Inscrição de Candidato):**
    - **Dado** que o `OP_PED` insere o nome completo, data de nascimento, género (`M`/`F`), número de BI/Cédula Pessoal único, média final da 9ª classe (`>= 10` valores), dados do Encarregado de Educação e o Curso Técnico/Turno pretendido,
    - **Quando** confirma a inscrição,
    - **Então** o sistema cria a candidatura no estado `Inscrito` e emite a Guia de Pagamento da Taxa de Inscrição para liquidação na Tesouraria.
  - **Cenário 2 (Bloqueio — Candidato Duplicado no Mesmo Ano Letivo):**
    - **Dado** que já existe uma candidatura no Ano Letivo corrente com o mesmo número de BI,
    - **Quando** o `OP_PED` tenta submeter nova ficha com esse BI,
    - **Então** o sistema rejeita com erro `HTTP 409 Conflict`: *"O candidato portador do BI informado já possui inscrição registada neste concurso de admissão"*.
- **Pós-condições e Efeitos Colaterais:** Registo criado na tabela `candidaturas` (estado `Inscrito`) e débito de emolumento gerado para pagamento no Caixa.

---

### `US-ADM-02`: Confirmar Pagamento de Inscrição, Gerar Código de Anonimato e Alocar nas 12 Salas
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **que o sistema gere automaticamente o Código de Anonimato e aloque o candidato numa das 12 salas de exame assim que a Tesouraria emitir o recibo da taxa de inscrição**, *para* **garantir a lisura e imparcialidade na correção das provas de seleção (DE n.º 361/26)**.
- **Rastreabilidade:** `RN-08`, `RN-09`, `RN-10` | `Fluxo 01`.
- **Pré-condições:** Candidatura no estado `Inscrito`; recibo da Taxa de Inscrição emitido pelo `OP_TES`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transição Automática e Geração de Anonimato):**
    - **Dado** que o `OP_TES` emite o Recibo Oficial da Taxa de Exame de Admissão para um candidato `Inscrito`,
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
- **Pré-condições:** Provas de seleção realizadas; candidaturas no estado `Apto para Exame`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Lançamento Cego de Notas):**
    - **Dado** que o `CHEFE_SEC_PED` acede à grelha de correção anónima,
    - **Quando** pesquisa pelo código `IPCAG-26-491B` e insere `Nota_LP = 14` e `Nota_Mat = 15`,
    - **Então** o sistema apresenta apenas o `codigo_anonimato` (ocultando 100% dos dados pessoais), calcula a média da prova via `round_med((14 + 15) / 2) = 15` e transita o registo para `Avaliado (Código Anonimato)`.
  - **Cenário 2 (Bloqueio — Nota Inválida Fora de 0 a 20):**
    - **Dado** que o operador tenta inserir `-1` ou `21` valores,
    - **Quando** submete o campo,
    - **Então** o sistema bloqueia o registo com erro de validação: *"A nota deve estar compreendida entre 0 e 20 valores"*.
- **Pós-condições e Efeitos Colaterais:** Notas associadas ao `codigo_anonimato` e candidatura no estado `Avaliado (Código Anonimato)`.

---

### `US-ADM-04`: Descodificar Anonimato, Aplicar Critérios de Desempate do MED e Publicar Pauta de Admitidos
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`) em conjunto com o Director Geral (`DIR_GERAL`)**, *quero* **executar a descodificação oficial do anonimato e o apuramento automático dos candidatos `Admitidos` e `Não Admitidos` por Curso e Turno**, *para* **publicar as listas finais respeitando rigorosamente o limite de vagas e os critérios legais de desempate do MED**.
- **Rastreabilidade:** `RN-01`, `RN-10` | `Fluxo 01`.
- **Pré-condições:** 100% dos candidatos `Aptos para Exame` avaliados ou marcados como `Faltou ao Exame`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Descodificação e Ranking até ao Limite de Vagas):**
    - **Dado** que o curso *Informática de Gestão — Manhã* possui `90` vagas configuradas e todas as provas estão avaliadas,
    - **Quando** o `SUB_PED` e o `DIR_GERAL` confirmam a **Descodificação e Homologação da Pauta de Seleção**,
    - **Então** o sistema revela os nomes reais, ordena os candidatos por média decrescente, aplica em caso de empate na última vaga a regra estrita: *(1.º Maior nota na disciplina nuclear/LP $\rightarrow$ 2.º Maior média da 9ª classe $\rightarrow$ 3.º Candidato mais jovem por data de nascimento)*, marca os primeiros 90 com média elegível como `Admitido` e os restantes como `Não Admitido`, e gera o PDF oficial com QR Code.
  - **Cenário 2 (Bloqueio — Tentativa de Descodificar com Provas Pendentes):**
    - **Dado** que ainda existem 3 códigos de anonimato sem nota lançada nem marcação de falta,
    - **Quando** o `SUB_PED` tenta executar a descodificação,
    - **Então** o sistema bloqueia a ação listando os códigos pendentes de lançamento.
- **Pós-condições e Efeitos Colaterais:** Candidaturas transitadas para `Admitido` ou `Não Admitido`; registo de homologação gravado em `audit_logs`.

---

## ÉPICO 03 (`EP-MAT`): Matrículas, Confirmações, Chamada Congelada e Transcrição de Histórico Externo

---

### `US-MAT-01`: Converter Candidato Admitido em Aluno Vitalício (`N.º de Processo Individual`) e Matricular na 10ª Classe
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **converter um candidato `Admitido` num registo vitalício de `Aluno` com atribuição automática do `N.º de Processo Individual` único**, *para* **efetivar a sua matrícula na 10ª classe sem redigitação de dados**.
- **Rastreabilidade:** `RN-05`, `RN-07`, `RN-08` | `Fluxo 02`.
- **Pré-condições:** Candidato com estado `Admitido` no Ano Letivo corrente.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Conversão e Geração do N.º de Processo Vitalício):**
    - **Dado** que o candidato `Admitido` comparece para matrícula com os documentos originais conferidos,
    - **Quando** o `OP_PED` seleciona a turma da 10ª classe (dentro da lotação da sala) e aciona *"Converter em Matrícula"*,
    - **Então** o sistema cria a entidade `Aluno` com um `num_processo` sequencial vitalício (ex.: `PROC-2026-00412`), cria a `Matrícula` no estado `Pendente (Aguardando Pagamento Inicial)`, atualiza a candidatura para `Convertido em Matrícula` e, assim que o recibo da Taxa de Matrícula + 1ª Propina (ou Bolsa 100%) é confirmado, muda a matrícula para `Ativa` e gera as prestações mensais na Conta Corrente.
  - **Cenário 2 (Bloqueio — Candidato Não Admitido):**
    - **Dado** um candidato com estado `Não Admitido` ou `Inscrito`,
    - **Quando** o `OP_PED` tenta convertê-lo em matrícula,
    - **Então** o botão encontra-se desativado e a API retorna `HTTP 422 Unprocessable Entity`: *"Apenas candidatos com estado ADMITIDO podem ser convertidos em matrícula da 10ª classe"*.
- **Pós-condições e Efeitos Colaterais:** Registo vitalício criado em `alunos`; matrícula criada em `matriculas`; plano financeiro gerado em `propinas_mensais`.

---

### `US-MAT-02`: Confirmar Matrícula Anual de Alunos Internos (11ª, 12ª e 13ª Classes)
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **realizar a Confirmação de Matrícula anual dos alunos internos preservando o seu `N.º de Processo Individual` e respeitando a deliberação do Conselho de Notas do ano anterior**, *para* **alocar o aluno na classe correta (transição limpa, transição com cadeiras em atraso ou repetência)**.
- **Rastreabilidade:** `RN-02`, `RN-05`, `RN-08` | `Fluxo 02`.
- **Pré-condições:** Aluno já registado no IPCAG; Pauta Geral do ano letivo anterior no estado `Fechado / Homologado`; Conta Corrente do ano anterior sem dívidas vencidas.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Confirmação na Classe Seguinte com Preservação de Processo):**
    - **Dado** que o aluno `PROC-2025-00108` obteve na 10ª classe a deliberação `Transita (Aprovado)` ou `Transita com Deficiência` (com 2 cadeiras em atraso) e está financeiramente adimplente,
    - **Quando** o `OP_PED` executa a Confirmação de Matrícula para o novo Ano Letivo,
    - **Então** o sistema mantém inalterado o `num_processo = PROC-2025-00108`, posiciona automaticamente a confirmação na `11ª Classe` do mesmo Curso Técnico e mantém visíveis no Processo Individual as eventuais `Cadeiras em Atraso` da 10ª classe para inscrição futura em Exame Extraordinário.
  - **Cenário 2 (Bloqueio — Aluno Inadimplente no Ano Anterior ou Bloqueado para a 13ª Classe):**
    - **Dado** que o aluno possui propinas vencidas do ano anterior **ou** pretende confirmar matrícula na `13ª Classe` tendo ainda $\ge 1$ Cadeira em Atraso não eliminada,
    - **Quando** o `OP_PED` tenta confirmar a matrícula,
    - **Então** o sistema bloqueia a operação (`HTTP 403` por dívida financeira ou `HTTP 422` por deficiência curricular pendente).
- **Pós-condições e Efeitos Colaterais:** Nova matrícula anual vinculada ao mesmo `aluno_id` e `num_processo`.

---

### `US-MAT-03`: Registar e Homologar Transcrição de Histórico Externo de Alunos Transferidos de Entrada
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **transcrever e vincular ao Processo Individual do aluno as médias finais (`MFD`) da 10ª, 11ª ou 12ª classe trazidas através de Guia de Transferência/Certificado de outra escola**, *para* **garantir que o histórico curricular fique completo e viabilize o cálculo exato da Média Final do Curso (`MFC`) na 13ª classe (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-06`, `RN-10` | `Fluxo 02` e `Fluxo 06`.
- **Pré-condições:** Matrícula por transferência de entrada na 11ª, 12ª ou 13ª classe; Guia de Transferência Oficial e Certificado Parcial digitalizados.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transcrição e Homologação pelo Subdirector Pedagógico):**
    - **Dado** que um aluno ingressa por transferência externa na `12ª Classe` do curso de *Finanças*,
    - **Quando** o `CHEFE_SEC_PED` informa a escola de origem, número da Guia de Transferência, anexa o PDF comprovativo e preenche as notas finais (`MFD` de `10` a `20` ou `DISP`) de todas as disciplinas da Matriz Curricular da `10ª Classe` e da `11ª Classe` (ou as médias trimestrais parciais `MT1`/`MT2` em caso de transferência no decurso do ano — `RN-06.1`), e o `SUB_PED` homologa o registo,
    - **Então** as notas transcritas passam a integrar a vista `vw_curriculo_consolidado_aluno` do aluno para cálculo de $MA_{10}$ e $MA_{11}$ na futura `MFC`.
  - **Cenário 2 (Bloqueio — Tentativa de Fechar 12ª/13ª Classe com Transcrição Externa Pendente):**
    - **Dado** um aluno admitido na 11ª ou 12ª classe por transferência externa cuja transcrição da 10ª classe ainda não foi preenchida ou homologada pelo `SUB_PED`,
    - **Quando** o sistema valida a aptidão do aluno para a `13ª Classe` ou para emissão de Certificado/Diploma,
    - **Então** o sistema bloqueia a progressão exibindo a lista exata das disciplinas da 10ª/11ª classe cujas notas de origem estão em falta.
- **Pós-condições e Efeitos Colaterais:** Registos criados em `historico_externo_transcricoes` e `historico_externo_notas`; homologação gravada em `audit_logs`.

---

### `US-MAT-04`: Gerir N.º de Ordem na Turma, Congelar Lista de Chamada pós-I Trimestre e Processar Entradas Tardias/Saídas
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) ou Sistema Automático**, *quero* **ordenar alfabeticamente os alunos da turma (`1..N`) no início do ano e congelar perpetuamente o `N.º de Ordem na Turma` após o fecho do I Trimestre**, *para* **garantir que alunos transferidos/desistentes não alterem os números de chamada dos colegas seguintes e que matrículas tardias entrem exclusivamente no fim da lista (`N + 1`) (`RN-05`)**.
- **Rastreabilidade:** `RN-05` | `Fluxo 02`, `Fluxo 04` e `Fluxo 08`.
- **Pré-condições:** Turma ativa no Ano Letivo corrente.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Ordenação Alfabética Antes do Congelamento e Trancamento no Fecho do I Trimestre):**
    - **Dado** que uma turma possui 40 alunos matriculados antes do fecho do I Trimestre,
    - **Quando** o `I Trimestre` da turma é homologado (ou o `CHEFE_SEC_PED` aciona *"Congelar Lista de Chamada"*),
    - **Então** os alunos ficam numerados de `1` a `40` por ordem alfabética rigorosa e a flag `lista_chamada_congelada` passa a `TRUE`, bloqueando qualquer renumeração dos números `1` a `40`.
  - **Cenário 2 (Sucesso — Aluno Transferido ou Anulado Pós-Congelamento Mantém a Linha Fixa):**
    - **Dado** que a lista da turma está congelada (`1` a `40`) e o aluno `N.º 15` pede Transferência Externa ou Anulação de Matrícula no II Trimestre,
    - **Quando** a transferência/anulação é homologada,
    - **Então** o aluno `N.º 15` permanece na linha `15` da Mini-Pauta e da Pauta Geral com estado `TRANSFERIDO` (ou `ANULADO`), e o aluno `N.º 16` **continua sendo o `N.º 16`** até ao fim do ano letivo.
  - **Cenário 3 (Sucesso — Matrícula Tardia / Transferência de Entrada Pós-Congelamento Vai para `N + 1`):**
    - **Dado** que a lista da turma está congelada (`1` a `40`) e um novo aluno chamado *"Abel António"* (letra A) ingressa na turma por transferência no início do II Trimestre,
    - **Quando** a sua matrícula é ativada na turma,
    - **Então** o sistema atribui-lhe obrigatoriamente o **`N.º de Ordem = 41`** (`max(num_ordem_turma) + 1`), posicionando-o no fim da pauta sem deslocar nenhum dos 40 alunos anteriores.
- **Pós-condições e Efeitos Colaterais:** Coluna `num_ordem_turma` imutável para todos os registos existentes após `lista_chamada_congelada = TRUE`.

---

## ÉPICO 04 (`EP-PED`): Gestão Pedagógica Trimestral, Mini-Pauta Offline-First, Faltas, Dispensas (`DISP`), Substituição Docente e Conselho de Notas

---

### `US-PED-01`: Registar Dosificação Trimestral e Matriz da Prova Trimestral Unificada (`NPT`)
- **História:** *Como* **Coordenador de Disciplina (`COORD_DISC`)**, *quero* **registar o plano de dosificação trimestral e os parâmetros da Prova Trimestral Unificada (`NPT`) para todas as turmas de uma mesma Classe/Disciplina**, *para* **padronizar o ensino e a avaliação trimestral conforme o Decreto Presidencial n.º 93/21**.
- **Rastreabilidade:** `RN-01` | `Fluxo 03`.
- **Pré-condições:** Utilizador autenticado como `COORD_DISC` vinculado à disciplina; trimestre `Aberto / Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Publicação de Dosificação e Matriz `NPT`):**
    - **Dado** que o `COORD_DISC` de *Contabilidade Geral* seleciona a `11ª Classe` — `I Trimestre`,
    - **Quando** submete as unidades temáticas semanais e anexa a matriz/critérios da prova unificada `NPT`,
    - **Então** todos os professores (`PROF`) alocados a *Contabilidade Geral* na 11ª classe visualizam a dosificação no seu painel e ficam habilitados a lançar a coluna `NPT` na data calendada.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `dosificacoes_trimestrais` e homologado pelo `SUB_PED`.

---

### `US-PED-02`: Registar Faltas Diárias, Justificar Faltas pelo Director de Turma e Aplicar Retenção Automática por Excesso de Faltas
- **História:** *Como* **Professor (`PROF`) e Director de Turma (`DIR_TURMA`)**, *quero* **que o professor registe as faltas em cada tempo letivo e que apenas o Director de Turma possa justificar faltas mediante comprovativo, acionando automaticamente a retenção por faltas quando o limite legal for excedido**, *para* **cumprir a regra de assiduidade proporcional à carga horária semanal (`RN-03`)**.
- **Rastreabilidade:** `RN-03` | `Fluxo 03`.
- **Pré-condições:** Turma e trimestre `Abertos / Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Registo pelo Professor e Justificação pelo Director de Turma):**
    - **Dado** que o `PROF` marcou 2 faltas ao aluno `N.º 08` na aula de *Física* (que possui `3` tempos letivos semanais e limite anual de `12` faltas injustificadas),
    - **Quando** o Encarregado entrega atestado e o `DIR_TURMA` seleciona essas 2 faltas, informa o motivo e clica em *"Justificar Faltas"*,
    - **Então** as 2 faltas passam para o contador de `Faltas Justificadas` e são abatidas do contador de `Faltas Injustificadas`.
  - **Cenário 2 (Sucesso — Disparo Automático de Retenção por Faltas `RF`):**
    - **Dado** que o limite máximo de faltas injustificadas da disciplina é `12` e o aluno já acumula `12` faltas injustificadas,
    - **Quando** o `PROF` regista a `13ª` falta injustificada,
    - **Então** o sistema altera imediatamente a situação do aluno naquela disciplina para **`Retido por Faltas (RF)`**, bloqueia a aprovação por frequência e impede o acesso ao Exame de Recurso nessa disciplina.
  - **Cenário 3 (Bloqueio RBAC — Professor Comum Tenta Justificar Falta):**
    - **Dado** um utilizador `PROF` que não é o `DIR_TURMA` daquela turma,
    - **Quando** tenta alterar o estado de uma falta de `Injustificada` para `Justificada`,
    - **Então** o sistema nega a operação com `HTTP 403 Forbidden`: *"Apenas o Director de Turma ou a Subdireção Pedagógica têm competência legal para justificar faltas"*.
- **Pós-condições e Efeitos Colaterais:** Contadores `faltas_justificadas` e `faltas_injustificadas` atualizados na Mini-Pauta; flag `retido_por_faltas` atualizado em tempo real.

---

### `US-PED-03`: Conceder e Homologar Dispensa Médica (`DISP`) com Ajuste Neutro no Denominador da Média
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **homologar o estado `Dispensado (DISP)` por junta/atestado médico em disciplinas elegíveis (como Educação Física)**, *para* **que o aluno fique isento de avaliação prática sem sofrer reprovação nem redução da sua média geral (`RN-01`)**.
- **Rastreabilidade:** `RN-01`, `RN-06` | `Fluxo 03`.
- **Pré-condições:** Disciplina marcada na Matriz Curricular com `permite_dispensa_medica = TRUE`; Atestado Médico anexado pelo `CHEFE_SEC_PED`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Homologação de `DISP` e Recálculo do Denominador):**
    - **Dado** que um aluno da 10ª classe possui `10` disciplinas na matriz curricular e apresenta Atestado Médico válido para *Educação Física*,
    - **Quando** o `SUB_PED` homologa a Dispensa Médica,
    - **Então** as células de `MAC`, `NPP`, `NPT`, `MT` e `MFD` de *Educação Física* para esse aluno ficam bloqueadas exibindo `'DISP'`, a disciplina é considerada regularizada e a Média Anual da 10ª classe desse aluno passa a dividir o somatório das notas por **`9` disciplinas** (em vez de `10`).
  - **Cenário 2 (Bloqueio — Tentativa de Dispensar Disciplina Nuclear ou Científica):**
    - **Dado** uma disciplina com `permite_dispensa_medica = FALSE` (ex.: *Língua Portuguesa*, *Matemática* ou *Contabilidade*),
    - **Quando** o operador tenta registar uma Dispensa Médica `DISP`,
    - **Então** o sistema bloqueia a operação (`HTTP 422 Unprocessable Entity`): *"Esta disciplina é de avaliação obrigatória pelo MED e não admite regime de Dispensa Médica (DISP)"*.
- **Pós-condições e Efeitos Colaterais:** Estado da disciplina do aluno marcado como `DISP`; registo de homologação gravado em `audit_logs`.

---

### `US-PED-04`: Lançar Notas (`MAC`, `NPP`, `NPT`) na Mini-Pauta com Persistência *Offline-First* e Arredondamento MED
- **História:** *Como* **Professor (`PROF`)**, *quero* **lançar as notas parcelares (`MAC`, `NPP`, `NPT`) na Mini-Pauta da minha turma com funcionamento contínuo mesmo sem internet (*Offline-First*) e cálculo automático de `MT` segundo a regra de arredondamento do MED (`>= 0.5` para cima)**, *para* **cumprir os prazos de lançamento sem perder trabalho durante falhas de energia ou internet no Panguila (`RN-01`, `RN-10`)**.
- **Rastreabilidade:** `RN-01`, `RN-04`, `RN-10` | `Fluxo 03`.
- **Pré-condições:** Professor com alocação ativa na `turma_disciplina_id`; trimestre no estado `Aberto / Em Curso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Cálculo Automático de `MT` com Regra `round_med`):**
    - **Dado** que o `PROF` digita para o aluno `N.º 01` as notas `MAC = 13`, `NPP = 14` e `NPT = 14` (média exata $= 41 / 3 = 13,666...$), e para o aluno `N.º 02` digita `MAC = 9`, `NPP = 10` e `NPT = 9,5` (média exata $= 28,5 / 3 = 9,50$),
    - **Quando** o motor calcula a Média Trimestral (`MT`),
    - **Então** o sistema aplica `round_med` (`decimal >= 0.5` arredonda para o inteiro superior), exibindo e gravando **`MT = 14`** para o aluno `N.º 01` e **`MT = 10`** para o aluno `N.º 02`.
  - **Cenário 2 (Sucesso — Persistência *Offline-First* e Sincronização Automática):**
    - **Dado** que a ligação à internet cai enquanto o `PROF` preenche as notas de 42 alunos na Mini-Pauta,
    - **Quando** o `PROF` clica em *"Guardar Rascunho Local"*,
    - **Então** os dados ficam persistidos localmente no `IndexedDB` cifrado com indicador visual `Pendente de Sincronização (42 registos)` e, assim que a rede LAN/Internet regressa, são sincronizados automaticamente em lote idempotente com o servidor, gravando `lancado_por_usuario_id`.
  - **Cenário 3 (Bloqueio — Professor Tenta Aceder a Mini-Pauta de Outra Turma/Disciplina):**
    - **Dado** que o `PROF` não possui vínculo ativo em `alocacoes_docentes` para a turma `IG12B-T`,
    - **Quando** tenta ler ou editar a Mini-Pauta dessa turma,
    - **Então** o servidor retorna `HTTP 403 Forbidden`.
- **Pós-condições e Efeitos Colaterais:** Registos gravados em `avaliacoes_trimestrais` vinculados a `(matricula_id, turma_disciplina_id, trimestre)`.

---

### `US-PED-05`: Executar Substituição Docente a Meio do Ano Letivo Mantendo a Mini-Pauta Intacta
- **História:** *Como* **Subdirector Pedagógico (`SUB_PED`)**, *quero* **substituir um professor titular por outro professor a meio do ano letivo numa disciplina/turma sem que nenhuma nota ou falta já lançada se perca**, *para* **garantir continuidade pedagógica total através do desacoplamento estrutural entre Professor e Notas (`RN-04`)**.
- **Rastreabilidade:** `RN-04`, `RN-10` | `Fluxo 03`.
- **Pré-condições:** `Professor A` alocado à `turma_disciplina_id` com notas já lançadas no I Trimestre e/ou parcialmente no II Trimestre; `Professor B` registado e ativo no RH.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Transição de Titularidade sem Perda de Dados):**
    - **Dado** que o `Professor A` lançou todas as notas do I Trimestre e o `MAC` do II Trimestre na turma `FIN11A-M`,
    - **Quando** o `SUB_PED` encerra a alocação do `Professor A` (`data_fim = hoje`, `motivo = Licença Médica`) e cria nova alocação para o `Professor B` (`data_inicio = hoje`) na mesma `turma_disciplina_id`,
    - **Então** o `Professor A` perde imediatamente permissão de escrita na Mini-Pauta, o `Professor B` passa a ver a mesma Mini-Pauta com 100% das notas do I Trimestre e o `MAC` do II Trimestre intactos (preservando nos metadados que aqueles campos foram originalmente lançados pelo `Professor A`), podendo lançar `NPP` e `NPT` normalmente.
- **Pós-condições e Efeitos Colaterais:** Atualização em `alocacoes_docentes`; evento `SUBSTITUICAO_DOCENTE` registado em `audit_logs`.

---

### `US-PED-06`: Fechar Conselho de Notas, Calcular Exame de Recurso (40%/60%) e Deliberar Transição/Retenção com Veto `LP + Nuclear`
- **História:** *Como* **Director de Turma (`DIR_TURMA`) e Subdirector Pedagógico (`SUB_PED`)**, *quero* **consolidar a Pauta Geral da turma no Conselho de Notas, calcular a `MFD` e o `Exame de Recurso` (`40% MFD + 60% Exame`) e executar o motor de deliberação anual do MED**, *para* **determinar com exatidão matemática quem Aprova, quem Retém e quem Transita com Deficiência respeitando o Veto Absoluto de Língua Portuguesa + Disciplina Nuclear (`RN-01`, `RN-02`)**.
- **Rastreabilidade:** `RN-01`, `RN-02`, `RN-03`, `RN-05` | `Fluxo 04`.
- **Pré-condições:** Todas as Mini-Pautas da turma sem células em branco no trimestre.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Cálculo de `MFD` e Ponderação 40%/60% em Exame de Recurso):**
    - **Dado** um aluno com $MT_1 = 8$, $MT_2 = 9$ e $MT_3 = 9$ ($MFD = \text{round\_med}(26/3) = 9$ valores) que vai a Exame de Recurso e obtém `Nota_Exame = 11` valores,
    - **Quando** o sistema calcula a classificação final pós-exame,
    - **Então** aplica $CF_{\text{Exame}} = \text{round\_med}((9 \times 0,40) + (11 \times 0,60)) = \text{round\_med}(3,6 + 6,6) = \text{round\_med}(10,2) = \mathbf{10\text{ valores}}$, deliberando o aluno como **`Aprovado em Exame`** na disciplina.
  - **Cenário 2 (Sucesso — Transição com Deficiência Permitida na 10ª e 11ª Classes):**
    - **Dado** um aluno da `10ª Classe` que no final do ano (pós-recurso) reprovou a **2 disciplinas** com notas finais de `8` valores (*Física* e *Informática Aplicada* — nuclear), mas **aprovou a Língua Portuguesa (`CFD >= 10`)**,
    - **Quando** o motor do Conselho de Notas executa a deliberação anual,
    - **Então** o aluno recebe a deliberação **`Transita com Deficiência`** para a 11ª classe e as 2 disciplinas reprovadas são gravadas automaticamente em `cadeiras_em_atraso`.
  - **Cenário 3 (Bloqueio / Veto Legal — Reprovação Simultânea a Língua Portuguesa E a uma Disciplina Nuclear):**
    - **Dado** um aluno da `10ª` ou `11ª Classe` que reprovou a apenas **2 disciplinas** (ambas com nota `8` valores), sendo uma delas **Língua Portuguesa** (`CFD = 8`) e a outra uma **Disciplina Nuclear do curso** (`is_nuclear = TRUE`, `CFD = 8`),
    - **Quando** o motor do Conselho de Notas executa a deliberação anual,
    - **Então** o sistema aplica o **Veto Absoluto (`RN-02`)** e atribui obrigatoriamente a deliberação **`Não Transita (Retido por LP + Nuclear)`**, proibindo a transição com deficiência.
  - **Cenário 4 (Bloqueio — Proibição de Transição com Deficiência na 12ª Classe):**
    - **Dado** um aluno da `12ª Classe` que após o Exame de Recurso permanece com $\ge 1$ disciplina reprovada ($CFD < 10$),
    - **Quando** o motor executa a deliberação anual,
    - **Então** o aluno fica **`Retido na 12ª Classe`** e impedido de transitar para a 13ª classe.
- **Pós-condições e Efeitos Colaterais:** Pauta Geral trancada em `Fechado / Homologado`; deliberações anuais gravadas; no I Trimestre dispara `lista_chamada_congelada = TRUE`; no III Trimestre alimenta automaticamente a tabela `cadeiras_em_atraso` e os mapas do GEPE.

---

## ÉPICO 05 (`EP-DEF-13`): Gestão de Cadeiras em Atraso (Exame Extraordinário) e Regime Especial da 13ª Classe (Estágio + PAP + `MFC`)

---

### `US-DEF-01`: Inscrever Aluno em Exame Extraordinário para Eliminação de Cadeiras em Atraso (10ª e 11ª Classes)
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **inscrever alunos da 11ª ou 12ª classe na época de Exame Extraordinário para eliminarem as suas disciplinas no estado `Transitado com Deficiência`**, *para* **que regularizem a sua situação curricular antes da conclusão da 12ª classe (`RN-02`)**.
- **Rastreabilidade:** `RN-02`, `RN-08` | `Fluxo 05`.
- **Pré-condições:** Época de Exame Extraordinário aberta pelo `SUB_PED`; aluno com registo pendente em `cadeiras_em_atraso`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Inscrição após Validação do Semáforo Financeiro):**
    - **Dado** que o aluno possui a disciplina *Matemática (10ª Classe)* no estado `Transitado com Deficiência`, está com as propinas em dia e pagou na Tesouraria o recibo do Emolumento de Exame Extraordinário,
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
- **Pré-condições:** Aluno no estado `Inscrito em Exame Extraordinário`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Aprovação `>= 10` e Eliminação da Deficiência):**
    - **Dado** que o aluno obteve nota `12` valores no Exame Extraordinário de *Matemática (10ª Classe)*,
    - **Quando** o `CHEFE_SEC_PED` lança a nota `12`, preenche `Livro n.º 04, Folha n.º 18, Termo n.º 092` e o `SUB_PED` homologa,
    - **Então** a cadeira em atraso transita para **`Deficiência Eliminada`**, a nota `12` substitui a nota reprobatória anterior no cálculo de $MA_{10}$, e a pendência deixa de bloquear o aluno.
  - **Cenário 2 (Bloqueio Crítico — Tentativa de Fechar 12ª Classe / Ingressar na 13ª com Deficiência Não Eliminada):**
    - **Dado** um aluno da 12ª classe que aprovou a todas as disciplinas da 12ª classe, mas obteve nota `8` (`< 10`) no Exame Extraordinário de uma cadeira em atraso da 10ª ou 11ª classe,
    - **Quando** o sistema avalia a conclusão da 12ª classe ou tenta abrir o processo da `13ª Classe`,
    - **Então** a cadeira em atraso retorna a `Transitado com Deficiência` e o processo da 13ª classe fica **estritamente bloqueado** no estado `Bloqueado (Possui Cadeiras em Atraso da 10ª-12ª)`.
- **Pós-condições e Efeitos Colaterais:** Atualização em `cadeiras_em_atraso` e `termos_exame`; recálculo automático da média anual da classe de origem.

---

### `US-13C-01`: Validar Aptidão para a 13ª Classe e Alocar Estágio Supervisionado e Orientador de PAP
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`)**, *quero* **alocar para cada aluno apto da 13ª classe a Empresa Parceira, o Supervisor Externo e o Tutor Interno do Estágio Curricular, bem como o Tema e o Professor Orientador da PAP**, *para* **gerir o regime especial da 13ª classe nos termos do Decreto Presidencial n.º 167/23**.
- **Rastreabilidade:** `RN-02`, `RN-06` | `Fluxo 06`.
- **Pré-condições:** Aluno com matrícula ativa na 13ª classe, 100% das disciplinas da 10ª à 12ª aprovadas (incluindo transcrição externa homologada, se transferido) e `0` Cadeiras em Atraso.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Alocação de Estágio e Projeto de PAP):**
    - **Dado** que o aluno se encontra no estado `Apto para 13ª Classe`,
    - **Quando** o `COORD_CURSO` associa a empresa parceira, o nome/contacto do Supervisor de Empresa, o docente Tutor Interno, o título do Tema da PAP e o docente Orientador,
    - **Então** o processo da 13ª classe muda para **`Em Estágio / Elaboração de PAP`** e o sistema habilita a emissão da **Carta Oficial de Apresentação de Estágio**.
  - **Cenário 2 (Bloqueio — Aluno com Histórico Externo da 10ª/11ª Incompleto):**
    - **Dado** um aluno transferido de outra escola na 11ª ou 12ª classe cuja `Transcrição de Histórico Externo` não possui todas as disciplinas da matriz preenchidas e homologadas,
    - **Quando** tenta avançar no processo da 13ª classe,
    - **Então** o sistema bloqueia a transição exibindo alerta de `Histórico Curricular Incompleto (RN-06)`.
- **Pós-condições e Efeitos Colaterais:** Registo atualizado em `processos_13_classe` no estado `Em Estágio / Elaboração de PAP`.

---

### `US-13C-02`: Homologar Nota de Estágio, Constituir Banca de Júri da PAP, Registar Ata e Calcular a `MFC`
- **História:** *Como* **Coordenador de Curso (`COORD_CURSO`) e Subdirector Pedagógico (`SUB_PED`)**, *quero* **registar a nota do Estágio Supervisionado, constituir a Banca de Júri da PAP (Presidente + 2 Vogais), emitir a Ata Oficial de Defesa e calcular automaticamente a Média Final do Curso (`MFC`)**, *para* **habilitar a emissão do Certificado e Diploma de Técnico Médio sem erros humanos de cálculo (`RN-06`)**.
- **Rastreabilidade:** `RN-01`, `RN-06`, `RN-08`, `RN-10` | `Fluxo 06`.
- **Pré-condições:** Processo da 13ª classe em `Em Estágio / Elaboração de PAP`; Conta Corrente do aluno sem propinas vencidas e Emolumento de Defesa de PAP pago na Tesouraria.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Constituição de Banca, Defesa e Cálculo Automático da `MFC`):**
    - **Dado** que o aluno possui `Nota_Estagio = 15` homologada, Semáforo Financeiro Verde (propina em dia + taxa de defesa paga), e Banca de Júri constituída com 3 docentes distintos (Presidente, 1.º Vogal Arguente e 2.º Vogal Orientador),
    - **Quando** o aluno realiza a defesa obtendo `Nota_PAP = 16`, e o `COORD_CURSO`, `SUB_PED` e `DIR_GERAL` homologam a Ata de Defesa,
    - **Então** o sistema calcula automaticamente:
      1. $MA_{10}$, $MA_{11}$ e $MA_{12}$ (excluindo disciplinas `DISP` do denominador e integrando notas de transcrição externa ou exames extraordinários);
      2. $MPC = \text{round\_med}((MA_{10} + MA_{11} + MA_{12}) / 3)$;
      3. A **`MFC`** arredondada via `round_med` segundo a ponderação da matriz do curso, transitando o processo para **`Defendido e Homologado`** e gerando o PDF da **Ata de Defesa da PAP**.
  - **Cenário 2 (Bloqueio — Inadimplência Financeira ou Falta de Nota de Estágio):**
    - **Dado** que o aluno ainda não tem `Nota_Estagio >= 10` lançada **ou** possui propina vencida / taxa de defesa não paga,
    - **Quando** o `COORD_CURSO` tenta transitar o aluno para `Apto para Defesa` e agendar a banca,
    - **Então** o sistema bloqueia a operação (`HTTP 403` / `HTTP 422`) indicando o requisito pendente.
- **Pós-condições e Efeitos Colaterais:** Ata de defesa gerada; `MFC` gravada de forma imutável no processo do aluno; estado atualizado para `Defendido e Homologado`.

---

## ÉPICO 06 (`EP-TES`): Tesouraria Anti-Fraude (Borderô por Saldo), Motor de Bolsas, Notas de Estorno AGT e Fecho de Caixa por Turno

---

### `US-TES-01`: Parametrizar Tabelas de Propinas, Multas por Mora e Emolumentos em Kwanzas (`AOA`)
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **configurar para cada Ano Letivo os valores das Propinas mensais por Curso/Classe, o dia limite de vencimento, a regra de multa por atraso e a tabela de Emolumentos em Kwanzas (`AOA`)**, *para* **padronizar toda a faturação e cobrança da Tesouraria sem valores arbitrários**.
- **Rastreabilidade:** `RN-07`, `RN-08`, `RN-09` | `Fluxo 01` e `Fluxo 07`.
- **Pré-condições:** Utilizador autenticado como `SUB_ADM` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Configuração e Homologação da Tabela Anual em `AOA`):**
    - **Dado** que o `SUB_ADM` define a propina mensal em `15.000,00 Kz` (10 prestações de Setembro a Junho), dia de vencimento `10` de cada mês, multa de mora configurada e os preços dos emolumentos (Taxa de Admissão, Matrícula, Declaração, Exame Extraordinário, Defesa de PAP, Certificado/Diploma),
    - **Quando** o `DIR_GERAL` homologa a tabela,
    - **Então** os valores ficam ativos e trancados para todas as operações de Conta Corrente daquele Ano Letivo.
- **Pós-condições e Efeitos Colaterais:** Registos criados em `tabelas_precos_ano_letivo` e `catalogo_emolumentos`.

---

### `US-TES-02`: Conceder e Homologar Bolsas de Estudo (50%/100%), Isenções Diocesanas e Descontos de Irmãos
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`) e Director Geral (`DIR_GERAL`)**, *quero* **associar bolsas de estudo (`50%`, `100%`, quotas sociais da Diocese de Caxito, descontos de irmãos ou filhos de funcionários) à matrícula do aluno**, *para* **que o sistema abata automaticamente o benefício na geração das propinas mensais (`RN-07`)**.
- **Rastreabilidade:** `RN-07`, `RN-08`, `RN-10` | `Fluxo 02`.
- **Pré-condições:** Matrícula do aluno criada; documento comprovativo da bolsa/parentesco registado.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Aplicação de Bolsa de 50% ou Desconto Familiar):**
    - **Dado** que a propina base é `15.000,00 Kz` e o `DIR_GERAL` homologa uma `BOLSA_50` para o aluno,
    - **Quando** o motor gera as prestações mensais na Conta Corrente,
    - **Então** cada prestação armazena `valor_bruto = 15.000,00 Kz`, `valor_desconto = 7.500,00 Kz` e `valor_liquido_a_pagar = 7.500,00 Kz` no estado `A Vencer`.
  - **Cenário 2 (Sucesso — Bolseiro Integral 100% com Semáforo Financeiro Sempre Verde):**
    - **Dado** um aluno órfão assistido pela Diocese de Caxito com `BOLSA_100` homologada,
    - **Quando** as prestações mensais são geradas,
    - **Então** nascem automaticamente no estado **`Isenta (Bolseiro 100%)`** (`valor_liquido = 0,00 Kz`), mantendo o Semáforo Financeiro de propinas permanentemente verde.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `beneficios_bolsas_matricula`; evento `CONCESSAO_BOLSA` gravado em `audit_logs`.

---

### `US-TES-03`: Registar Borderô/Talão Bancário `UNIQUE` e Liquidar Propinas de Irmãos/Múltiplos Meses com Controlo de Saldo
- **História:** *Como* **Operador de Caixa / Tesouraria (`OP_TES`)**, *quero* **registar comprovativos bancários (`Borderô / Talão / Multicaixa Express`) validando a unicidade do número de operação e controlando o `valor_total_talao` vs. `saldo_utilizado`**, *para* **permitir que um Encarregado de Educação pague legitimamente vários meses ou as propinas de 2 ou mais irmãos com um único talão verdadeiro, bloqueando o talão assim que o saldo disponível atingir `0,00 Kz` (`RN-09`)**.
- **Rastreabilidade:** `RN-08`, `RN-09`, `RN-10` | `Fluxo 07`.
- **Pré-condições:** Sessão de caixa do turno aberta pelo `OP_TES`; aluno(s) com propinas ou emolumentos a pagar.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Pagamento de 2 Irmãos com um Único Talão Bancário Verdadeiro):**
    - **Dado** que o Encarregado apresenta um talão bancário do banco `BAI` com número de operação `OP-2026-778899` no valor total de **`30.000,00 Kz`** para pagar a propina de Outubro dos seus dois filhos (`Irmão 1 = 15.000,00 Kz` e `Irmão 2 = 15.000,00 Kz`),
    - **Quando** o `OP_TES` regista o borderô `OP-2026-778899` (`valor_total_talao = 30.000,00 Kz`) e emite o **Recibo 1** para o `Irmão 1` alocando `15.000,00 Kz`,
    - **Então** o borderô assume o estado **`Parcialmente Utilizado`** com `saldo_utilizado = 15.000,00 Kz` e `saldo_disponivel = 15.000,00 Kz`;
    - **E quando** a seguir o `OP_TES` abre a conta do `Irmão 2`, informa o mesmo código `OP-2026-778899` e emite o **Recibo 2** alocando os restantes `15.000,00 Kz`,
    - **Então** o sistema emite o segundo recibo com sucesso e transita imediatamente o borderô `OP-2026-778899` para o estado **`Esgotado / Trancado`** (`saldo_utilizado = 30.000,00 Kz`, `saldo_disponivel = 0,00 Kz`).
  - **Cenário 2 (Bloqueio Anti-Fraude — Tentativa de Reutilizar um Borderô Esgotado para outro Aluno):**
    - **Dado** que o borderô `OP-2026-778899` já se encontra no estado `Esgotado / Trancado` (`saldo_disponivel = 0,00 Kz`),
    - **Quando** alguém tenta utilizar o código `OP-2026-778899` para quitar propina ou emolumento de um 3º aluno (ou outro mês),
    - **Então** o sistema bloqueia a operação com alerta crítico `HTTP 409 Conflict — ALERTA ANTI-FRAUDE`: *"Este comprovativo bancário (OP-2026-778899) já foi 100% consumido nos Recibos RC 2026/00105 e RC 2026/00106. Saldo disponível: 0,00 Kz"*, e grava a tentativa em `audit_logs`.
  - **Cenário 3 (Bloqueio — Tentativa de Alocar Valor Superior ao Saldo Remanescente do Talão):**
    - **Dado** que um borderô possui `saldo_disponivel = 10.000,00 Kz`,
    - **Quando** o `OP_TES` tenta emitir um recibo de `15.000,00 Kz` usando apenas esse borderô,
    - **Então** o sistema impede a emissão com erro `HTTP 422`: *"O valor a liquidar (15.000,00 Kz) excede o saldo disponível neste borderô (10.000,00 Kz)"*.
- **Pós-condições e Efeitos Colaterais:** Recibo(s) sequencial(is) emitido(s) em `AOA`; propinas atualizadas para `Paga`; `borderos_bancarios` atualizado atomicamente (`SELECT ... FOR UPDATE`).

---

### `US-TES-04`: Emitir Nota de Estorno Contabilístico ou Declarar Fraude de Borderô sem `DELETE`/`UPDATE` em Recibos (Padrão AGT)
- **História:** *Como* **Subdirector Administrativo (`SUB_ADM`)**, *quero* **corrigir erros de faturação ou invalidar talões fraudulentos exclusivamente através da emissão de uma Nota de Estorno/Anulação sequencial**, *para* **cumprir a proibição fiscal de apagar ou editar recibos emitidos (Decreto Presidencial n.º 292/18 — AGT) (`RN-09`)**.
- **Rastreabilidade:** `RN-08`, `RN-09`, `RN-10` | `Fluxo 07`.
- **Pré-condições:** Recibo emitido na base de dados; utilizador autenticado como `SUB_ADM` ou `DIR_GERAL`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Bloqueio Absoluto de `DELETE` / `UPDATE` na Tabela de Recibos):**
    - **Dado** qualquer recibo emitido no sistema,
    - **Quando** qualquer utilizador (ou instrução SQL direta na aplicação) tenta executar `DELETE` ou `UPDATE` de valores sobre a linha do recibo,
    - **Então** a *trigger* `trg_prevent_recibo_mutation` do PostgreSQL aborta a transação com exceção de violação de imutabilidade fiscal AGT.
  - **Cenário 2 (Sucesso — Emissão de Nota de Estorno por Erro Operacional):**
    - **Dado** que o recibo `RC 2026/00150` foi emitido por engano no aluno errado,
    - **Quando** o `SUB_ADM` aprova a emissão da **Nota de Estorno `NE 2026/00012`** informando a justificativa formal,
    - **Então** o recibo original mantém-se registado com referência à `NE 2026/00012`, a propina do aluno volta ao estado `A Vencer` (ou `Em Atraso com Multa`), e o saldo correspondente retorna ao `saldo_disponivel` do borderô para ser aplicado no aluno correto.
  - **Cenário 3 (Sucesso — Invalidação de Borderô Falso/Adulterado em Cascata):**
    - **Dado** que a conferência bancária deteta que um borderô utilizado em 2 recibos era um comprovativo falsificado,
    - **Quando** o `SUB_ADM` aciona *"Declarar Borderô Invalidado por Fraude"*,
    - **Então** o borderô muda permanentemente para **`Invalidado por Fraude`**, o sistema emite automaticamente Notas de Estorno para todos os recibos vinculados a esse borderô, reabre as dívidas com multa nas Contas Correntes dos alunos beneficiados (acionando imediatamente o **Semáforo Financeiro Vermelho**) e grava alerta de fraude em `audit_logs`.
- **Pós-condições e Efeitos Colaterais:** Registo criado em `notas_estorno`; reabertura automática de débitos na Conta Corrente; trilha gravada em `audit_logs`.

---

### `US-TES-05`: Executar e Homologar o Fecho de Caixa Diário por Turno Segregado por Canal de Pagamento
- **História:** *Como* **Operador de Tesouraria (`OP_TES`) e Subdirector Administrativo (`SUB_ADM`)**, *quero* **emitir no final de cada turno (Manhã e Tarde) o Mapa Diário de Fecho de Caixa separando os recebimentos em `TPA`, `Transferência/Depósito Bancário` e `Multicaixa Express`**, *para* **conferência física dos talões, assinatura e trancamento contabilístico diário (`RN-09`)**.
- **Rastreabilidade:** `RN-09`, `RN-10` | `Fluxo 07`.
- **Pré-condições:** Sessão de caixa do turno aberta com movimentos no dia.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Emissão e Homologação do Mapa de Fecho de Caixa por Turno):**
    - **Dado** que o `OP_TES` concluiu o atendimento do `Turno da Manhã`,
    - **Quando** aciona *"Fechar Caixa do Turno"*,
    - **Então** o sistema consolida todos os recibos e notas de estorno do turno, apresenta os subtotais exatos de **`TPA`**, **`Transferência / Depósito Bancário`** e **`Multicaixa Express`**, gera o PDF oficial com campos de assinatura para o `OP_TES` e para o `SUB_ADM`, e após a homologação do `SUB_ADM` impede qualquer lançamento retroativo naquela sessão de caixa.
- **Pós-condições e Efeitos Colaterais:** Sessão de caixa trancada no estado `Fechado e Homologado`.

---

## ÉPICO 07 (`EP-DOC-AUD`): Emissão Documental Oficial, Semáforo Financeiro, Livro/Folha/Termo, QR Code, RH e Estatísticas GEPE/MED

---

### `US-DOC-01`: Emitir Boletins, Declarações e Guias de Transferência Protegidos pelo Semáforo Financeiro Automático
- **História:** *Como* **Operador da Secretaria Pedagógica (`OP_PED`)**, *quero* **que o sistema valide automaticamente a adimplência de propinas e o pagamento do emolumento antes de liberar a impressão de Boletins, Declarações ou Guias de Transferência**, *para* **garantir que nenhum documento oficial seja emitido para alunos com dívidas vencidas (`RN-08`)**.
- **Rastreabilidade:** `RN-05`, `RN-08`, `RN-10` | `Fluxo 08`.
- **Pré-condições:** Aluno registado; pauta do trimestre/ano homologada.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Bloqueio Automático pelo Semáforo Financeiro — `HTTP 403`):**
    - **Dado** um aluno que possui a propina do mês anterior no estado `Em Atraso (com Multa)` **ou** que ainda não pagou o emolumento de *Declaração com Notas*,
    - **Quando** o `OP_PED` ou `CHEFE_SEC_PED` tenta gerar/imprimir a Declaração,
    - **Então** a função `fn_verificar_aptidao_financeira` bloqueia a emissão com `HTTP 403 Forbidden`: *"Emissão Bloqueada pela Tesouraria: O aluno possui propinas em atraso e/ou emolumento do documento não liquidado"*.
  - **Cenário 2 (Sucesso — Emissão de Guia de Transferência de Saída com Cancelamento de Propinas Futuras e Chamada Congelada):**
    - **Dado** que o aluno está 100% adimplente até ao mês corrente e pagou o emolumento de *Guia de Transferência*,
    - **Quando** o `CHEFE_SEC_PED` e o `SUB_PED` homologam a transferência externa de saída no II Trimestre,
    - **Então** o sistema emite a Guia de Transferência com QR Code, muda a matrícula para `Transferida (Externa)`, altera todas as propinas dos meses futuros (ainda a vencer) para **`Cancelada`** e mantém a linha do aluno fixa no seu `N.º de Ordem` original na pauta com a marcação `TRANSFERIDO`.
- **Pós-condições e Efeitos Colaterais:** Documento registado em `documentos_emitidos` consumindo o `recibo_item_id` (uso único).

---

### `US-DOC-02`: Emitir Certificados de Habilitações e Diplomas da 13ª Classe com Controlo de `Livro, Folha e Termo` e QR Code
- **História:** *Como* **Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`)**, *quero* **emitir Certificados de Habilitações e Diplomas de Técnico Médio exigindo obrigatoriamente o preenchimento único de `Livro n.º X, Folha n.º Y, Termo n.º Z` e gerando assinatura QR Code**, *para* **cumprir as exigências de arquivo físico do MED e blindar o IPCAG contra falsificação de diplomas (`RN-10`)**.
- **Rastreabilidade:** `RN-06`, `RN-08`, `RN-10` | `Fluxo 06` e `Fluxo 08`.
- **Pré-condições:** Processo da 13ª classe no estado `Defendido e Homologado` com `MFC` calculada; Semáforo Financeiro Verde (0 propinas em atraso + emolumento de Certificado/Diploma pago).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Emissão com `Livro, Folha e Termo` e Hash `HMAC-SHA256`):**
    - **Dado** um finalista da 13ª classe com `MFC = 15` valores e emolumento pago,
    - **Quando** o `CHEFE_SEC_PED` informa `Livro n.º 02`, `Folha n.º 45`, `Termo n.º 178` e aciona a emissão do Certificado/Diploma,
    - **Então** o sistema valida que a tripla `(Livro, Folha, Termo)` é única, gera o `codigo_verificacao_hash` (`HMAC-SHA256`), imprime no PDF o cabeçalho oficial da República de Angola / MED / IPCAG N.º 12008 / BGO, as notas curriculares, a nota de Estágio, a nota da PAP, a `MFC`, a referência `Livro 02, Folha 45, Termo 178` e o **QR Code** de verificação.
  - **Cenário 2 (Bloqueio — Ausência ou Duplicidade de `Livro, Folha e Termo`):**
    - **Dado** que o operador deixa em branco o campo `Termo n.º` ou informa uma combinação `(Livro, Folha, Termo)` já atribuída a outro aluno,
    - **Quando** tenta emitir o Certificado ou Diploma,
    - **Então** o sistema rejeita com erro `HTTP 422` / `HTTP 409`: *"É obrigatório informar uma numeração física única de Livro, Folha e Termo para emitir Certificados ou Diplomas"*.
- **Pós-condições e Efeitos Colaterais:** Processo da 13ª classe atualizado para `Diploma/Certificado Emitido`; registo imutável criado em `documentos_emitidos`.

---

### `US-DOC-03`: Consultar Autenticidade Pública de Documento Oficial via Leitura de QR Code / Hash Criptográfico
- **História:** *Como* **Entidade Externa (Inspector do MED, Universidade ou Empresa Empregadora)**, *quero* **ler o QR Code impresso em qualquer Declaração, Boletim, Recibo, Certificado ou Diploma emitido pelo IPCAG N.º 12008 / BGO**, *para* **verificar instantaneamente se o documento e as notas apresentadas em papel são autênticos ou falsificados (`RN-10`)**.
- **Rastreabilidade:** `RN-10` | `Fluxo 08`.
- **Pré-condições:** Documento emitido pelo SGE contendo `codigo_verificacao_hash`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Documento Autêntico Confirmado):**
    - **Dado** um Certificado genuíno emitido pelo sistema,
    - **Quando** o validador lê o QR Code ou digita o código de verificação no portal público,
    - **Então** o sistema exibe os dados oficiais inalteráveis (`Estado: VÁLIDO`, Nome abreviado/completo conforme política APD, `N.º de Processo`, `Curso Técnico`, `Tipo de Documento`, `Média Final / MFC`, `Livro/Folha/Termo` e `Data de Emissão`), sem expor dados internos sensíveis da base de dados.
  - **Cenário 2 (Alerta — Código Inexistente ou Documento Anulado):**
    - **Dado** um QR Code forjado ou pertencente a um recibo/documento anulado por Nota de Estorno,
    - **Quando** o código é consultado,
    - **Então** o portal exibe destaque vermelho: **`DOCUMENTO INVÁLIDO, ANULADO OU NÃO RECONHECIDO PELO IPCAG N.º 12008 / BGO`**.
- **Pós-condições e Efeitos Colaterais:** Registo de consulta pública gravado no log de acessos de verificação.

---

### `US-DOC-04`: Gerir Cadastro e Assiduidade (Ponto) de Docentes e Funcionários Administrativos
- **História:** *Como* **Chefe da Secretaria Geral (`CHEFE_SEC_GER`) e Coordenador de Turno (`COORD_TURNO`)**, *quero* **gerir o processo individual e o registo diário de assiduidade (ponto e faltas) dos professores e funcionários administrativos**, *para* **cumprir as competências da Secretaria Geral previstas no Decreto Presidencial n.º 93/21**.
- **Rastreabilidade:** DP n.º 93/21 | Contexto `Secretaria Geral & RH`.
- **Pré-condições:** Utilizador autenticado como `CHEFE_SEC_GER`, `COORD_TURNO` ou `SUB_ADM`.
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Registo de Ponto e Relatório Mensal de Assiduidade Laboral):**
    - **Dado** o quadro de docentes e funcionários ativos nos turnos da Manhã e da Tarde,
    - **Quando** o `COORD_TURNO` / `CHEFE_SEC_GER` regista as presenças, atrasos e faltas laborais e o `SUB_ADM` valida o mapa mensal,
    - **Então** o sistema gera o Mapa Mensal de Assiduidade Docente e Não-Docente para efeitos administrativos e de comparticipação estatal/diocesana.
- **Pós-condições e Efeitos Colaterais:** Registos gravados em `assiduidade_funcionarios`.

---

### `US-DOC-05`: Exportar Mapas Estatísticos Oficiais do GEPE/MED e Auditar Trilha Imutável (`audit_logs` - APD)
- **História:** *Como* **Director Geral (`DIR_GERAL`) ou Subdirector Pedagógico (`SUB_PED`)**, *quero* **exportar os Mapas Estatísticos Oficiais do GEPE/MED (segmentados por Curso, Classe, Turma, Turno, Género M/F, Faixa Etária e Aproveitamento) e inspecionar a trilha imutável de auditoria (`audit_logs`)**, *para* **prestar contas oficiais ao Ministério da Educação e auditar qualquer operação sensível realizada no sistema (`RN-10`)**.
- **Rastreabilidade:** `RN-10` | `Fluxo 04` e `Fluxo 08`.
- **Pré-condições:** Utilizador autenticado na Direção Executiva (`DIR_GERAL`, `SUB_PED`, `SUB_ADM`) ou `CHEFE_SEC_PED` (para mapas GEPE).
- **Critérios de Aceitação (BDD):**
  - **Cenário 1 (Sucesso — Geração dos Mapas Estatísticos do GEPE/MED):**
    - **Dado** um Ano Letivo e Trimestre (ou Final de Ano),
    - **Quando** o `SUB_PED` ou `CHEFE_SEC_PED` solicita a exportação do **Mapa Estatístico GEPE/MED**,
    - **Então** o sistema consolida os totais exatos por `Curso Técnico`, `Classe (10ª–13ª)`, `Turma`, `Turno (Manhã/Tarde)`, `Género (Masculino / Feminino)`, `Faixas Etárias`, `Matriculados Inicialmente`, `Aprovados/Transitados`, `Transitados com Deficiência`, `Retidos por Notas`, `Retidos por Faltas`, `Transferidos (Entrada/Saída)` e `Desistentes/Anulados` em PDF e Excel/CSV.
  - **Cenário 2 (Sucesso — Consulta e Imutabilidade Absoluta de `audit_logs`):**
    - **Dado** que o `DIR_GERAL` filtra o módulo de Auditoria por `Reabertura de Pauta`, `Nota de Estorno` ou `Alerta de Fraude de Borderô`,
    - **Quando** visualiza os detalhes de um evento,
    - **Então** o sistema exibe o utilizador autor, o cargo RBAC, o IP, o timestamp UTC, a justificativa/despacho e o diff completo `valor_antigo_jsonb` vs. `valor_novo_jsonb`, sendo qualquer comando `DELETE` ou `UPDATE` sobre a tabela `audit_logs` bloqueado por trigger nativa do PostgreSQL.
- **Pós-condições e Efeitos Colaterais:** Mapas estatísticos gerados com hash de integridade; conformidade plena com o GEPE/MED e a Lei n.º 22/11 (APD).
