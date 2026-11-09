---
title: "Questionário por Cargo — Subdireção Pedagógica (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Subdireção Pedagógica"
  - "DSC-05-SUB-PED"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-05-SUB-PED"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - subdirecao-pedagogica
---

# Questionário de Parametrização: Subdireção Pedagógica

**Finalidade:** Recolher os parâmetros regulamentares, fórmulas de avaliação e regras de gestão pedagógica da escola para calibrar os módulos de Horários e Distribuição de Serviço (`C04`), Gestão de Faltas e Sumários (`C05`), Avaliação e Pautas (`C06`), Exames Extraordinários e Recursos (`C07`), Painéis de Gestão (`C15`) e Passagem de Ano (`C16`), em conformidade com a `DEC-009` (Pontos de Controlo PC-E1 e PC-E2).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Subdirector Pedagógico / Coordenador da Área Pedagógica (`SUB_PED`)  
**Como as suas respostas serão usadas:** As respostas serão configuradas nas tabelas de parâmetros pedagógicos (`parametros_avaliacao`, `parametros_frequencia`, `turnos`, `anos_letivos`), assegurando que as fórmulas e regras automáticas refletem a prática real da escola sem alterações de código.

## Contexto

A arquitetura do SGE assegura rigor e integridade nos cálculos académicos (médias trimestrais, prova global, classificação anual, deliberações de pauta e limites de faltas). Conforme fixado na `DEC-009`, as fórmulas reais de avaliação e as regras do regulamento interno são parametrizáveis. Este questionário reúne 43 questões estruturadas em torno do calendário letivo, grelha horária, critérios de avaliação e circuito de pautas.

## Como responder

- **Prazo sugerido:** Entrega antes da validação de pautas do I Trimestre (Pontos de Controlo PC-E1 para horários/matrículas e PC-E2 para notas/avaliações).
- Responda com base na prática efetiva adotada nas reuniões pedagógicas e conselhos de notas.
- Se algum ponto necessitar de confirmação da Comissão de Gestão ou de deliberação coletiva, assinale com `Em debate`.

---

## 1. Calendário Escolar e Grelha Horária dos Turnos

### [Q-005] Quais são as datas oficiais previstas para o calendário escolar de 2027/2028 (matrículas, início das aulas, fim de cada trimestre, exames)?
_Por que importa: Configura os períodos letivos e bloqueios temporais no registo de matrículas e notas (`C01`)._
> 

### [Q-C04-01] Qual é a duração exata do tempo letivo (45 ou 50 minutos) e o intervalo entre tempos em cada turno?
_Por que importa: Modela a grelha de horários e a contagem de cargas horárias (`RN-12.1`)._
> 

### [Q-C04-02] As atividades letivas decorrem de segunda a sexta-feira, ou há aulas regulares ao sábado?
_Por que importa: Configura a matriz de dias letivos semanais no motor de horários (`RN-12.1.5`)._
> 

### [Q-C04-18] Como se compatibilizam as 32 horas curriculares dos planos de estudo com as janelas horárias dos dois turnos diurnos?
_Por que importa: Calibra o teto semanal de tempos letivos por turma (`RN-12.2`)._
> 

### [Q-C04-15] Com que antecedência mínima devem ser comunicadas e aprovadas as alterações pontuais ao horário semanal?
_Por que importa: Configura a antecedência de publicação e histórico de versões do horário (`RN-12.11`)._
> 

### [Q-C04-16] Qual é o modelo oficial de documento utilizado pela escola para afixação do horário de turma e mapa de distribuição docente?
_Por que importa: Modela o leiaute de impressão dos documentos `DOF-C04`._
> 

---

## 2. Alocação Docente, Substituições e Reposições

### [Q-C04-06] É permitida a alocação de um professor a uma disciplina fora da sua área específica de formação académica?
_Por que importa: Configura se a compatibilidade de habilitações atua como bloqueio rígido ou aviso (`RN-12.5`)._
> 

### [Q-C04-11] Em caso de ausência justificada do docente, qual é o prazo regulamentar para marcação e realização da aula de reposição?
_Por que importa: Parametriza o temporizador de reposições pendentes no livro de sumários (`RN-12.15`)._
> 

### [Q-C04-12] Qual é o prazo máximo concedido ao professor para registar o sumário da aula após o seu término?
_Por que importa: Define o limite para fecho de lições e emissão de alertas de sumário em atraso (`RN-12.13.7`)._
> 

### [MIG-Q07] Quantas versões da matriz curricular existem em vigor em simultâneo na escola para os quatro cursos?
_Por que importa: Permite associar a matriz correta a cada turma histórica e coorte ativa (`MIG-F01`)._
> 

---

## 3. Avaliação das Aprendizagens, Fórmulas e Pautas

### [Q-025] Quais são as fórmulas exatas de cálculo da Avaliação Contínua nos três trimestres e da Classificação Anual (`CA`)?
_Por que importa: Modela o motor de cálculo da mini-pauta e da pauta geral (`RN-01`, `RN-02`). Favor indicar se `CA = CF × 0,6 + PG × 0,4` se aplica a todas as disciplinas e como é calculada a Prova Global (`PG`)._
> 

### [Q-LEG-02] Na conversão das médias com casas decimais para classificação inteira na pauta geral, qual é a regra de arredondamento (arredondamento simétrico a partir de 0,5)?
_Por que importa: Assegura paridade exata entre o cálculo automático do SGE e o valor homologado na pauta impressa._
> 

### [Q-LEG-03] Quais são as condições de acesso ao Exame de Recurso (nota mínima de `CF`, número máximo de disciplinas e fórmula da nota final de recurso)?
_Por que importa: Modela a lista de admitidos a recurso no encerramento do ano letivo (`C07`)._
> 

### [MIG-Q38] Na migração dos anos anteriores, é necessário digitar as avaliações parcelares (`MTP`/`PP`/`PT`) ou basta carregar as Classificações Finais anuais (`CFD`/`CA`)?
_Por que importa: Define o esforço de digitação da equipa de transição histórica._
> 

---

## 4. Assiduidade, Faltas e Justificações

### [Q-C04-13] As faltas por indisciplina e as faltas por não comparência acumulam para o mesmo limite máximo legal de reprovação por faltas (`RN-03`)?
_Por que importa: Configura o cálculo do total de faltas na perda de frequência do aluno._
> 

### [Q-LEG-04] Qual é o limite máximo regulamentar de faltas injustificadas permitido por trimestre e no acumulado do ano letivo?
_Por que importa: Modela o disparo de alerta de risco de retenção por faltas (`RN-03.5`)._
> 

### [Q-C15-03] Qual é o prazo regulamentar concedido ao encarregado para entregar a justificação de faltas do estudante na Secretaria?
_Por que importa: Configura a data limite para aceitação de justificações no sistema (`RN-15.8`)._
> 

### [Q-C12-05] Em que patamares de faltas a Subdireção Pedagógica pretende disparar avisos automáticos aos encarregados (ex.: a 50% e a 80% do limite legal)?
_Por que importa: Configura os gatilhos da Central de Avisos (`RN-14.5`)._
> 

### [Q-C15-02] A Subdireção Pedagógica pretende receber alertas imediatos quando um aluno atinge 50% do limite de faltas de uma disciplina?
_Por que importa: Parametriza o painel de alerta precoce de abandono escolar (`C15`)._
> 

---

## 5. Disciplina e Comportamento dos Alunos

### [Q-C13-02] Qual é a escala oficial de avaliação do comportamento trimestral dos estudantes (Excelente/Bom/Suficiente/Mau, ou escala numérica)?
_Por que importa: Configura a lista de valores admissíveis na pauta e boletim (`RN-15.7`)._
> 

### [Q-C13-03] O registo de falta disciplinar na aula deve exigir obrigatoriamente a abertura de processo disciplinar ou pode ser apenas anotado no boletim?
_Por que importa: Modela a gradação entre ocorrência sumária e processo disciplinar formal (`C13`)._
> 

### [Q-APD-32] Quem tem permissão para visualizar o histórico de ocorrências disciplinares de anos letivos anteriores e qual o prazo de conservação dessa informação?
_Por que importa: Garante a conformidade com as regras de confidencialidade e eliminação da Lei n.º 22/11 da APD._
> 

---

## 6. Passagem de Ano Letivo, Turmas e Exames Extraordinários

### [Q-C16-01] Qual é o prazo concedido aos alunos transitados para confirmarem a matrícula antes de a vaga ser disponibilizada para novo ingresso?
_Por que importa: Configura a libertação automática de vagas no motor de passagem de ano (`RN-18.6.3`)._
> 

### [Q-C16-03] Na transição de ano letivo, as turmas mantêm a mesma coorte e letra (ex.: 10ª A passa em bloco para 11ª A) ou é feita redistribuição de repetentes?
_Por que importa: Parametriza a distribuição automática de alunos do motor de turmas (`RN-18.7.3`)._
> 

### [Q-C16-04] O estudante pode requerer mudança de turno ou de curso na passagem de ano letivo? Em que condições?
_Por que importa: Modela o fluxo de transferência interna de turma na passagem de ano (`RN-18.5`)._
> 

### [Q-C16-07] Em que meses decorre a época de exames extraordinários para eliminação de cadeiras em atraso e quantas épocas existem por ano?
_Por que importa: Modela a abertura de pautas de exame extraordinário no calendário (`RN-18.1.5`)._
> 

### [Q-C16-10] Como se processa a avaliação extraordinária de um aluno que tem em atraso uma disciplina que deixou de existir na nova matriz curricular?
_Por que importa: Define se o SGE deve manter o exame associado à matriz histórica arquivada (`RN-18.9.4`)._
> 

### [Q-C16-13] O reingresso de um antigo estudante desistente exige despacho formal de autorização e em que classe é enquadrado?
_Por que importa: Modela o formulário de reingresso escolar com anexo de despacho (`RN-18.13`)._
> 

### [Q-C16-15] A Direção Provincial exige uma Ata ou Mapa de Encerramento com formato específico no termo das atividades letivas?
_Por que importa: Modela o documento de fecho pedagógico anual `DOF-C16-01`._
> 

### [Q-C16-17] Qual é o limite regulamentar máximo de cadeiras em atraso com que um aluno pode transitar na 10ª e 11ª classes (até 2 disciplinas)?
_Por que importa: Valida o parâmetro da deliberação `TRANSITA_COM_DEFICIENCIA` (`RN-02.3`)._
> 

### [MIG-Q40] Na migração histórica, prefere-se manter o Número de Processo original dos estudantes ou renumerar de acordo com nova sequência?
_Por que importa: Configura o tratamento de chave primária e aliases legados (`AJ-05`)._
> 

---

## 7. Políticas Pedagógicas de Acesso e Gestão

### [Q-C14-04] Os professores utilizam telemóvel pessoal para registo de sumários ou a escola disponibiliza postos na sala dos professores?
_Por que importa: Dimensiona os postos de trabalho e a política de segurança móvel (`RN-16`)._
> 

### [Q-C14-06] O Coordenador de Turno é necessariamente um professor em exercício nesse turno?
_Por que importa: Configura o escopo de atuação do papel `COORD_TURNO` no controlo de acesso RBAC._
> 

### [Q-C14-07] Quando um professor entra em licença médica prolongada ou de parto, o seu acesso ao sistema deve ser suspenso temporariamente?
_Por que importa: Configura o estado operacional da conta docente em `usuarios_sistema`._
> 

### [Q-C12-04] Os alunos com idade igual ou superior a 18 anos devem receber as notificações pedagógicas diretamente, em alternativa ao encarregado?
_Por que importa: Configura a regra de notificação de maiores de idade sob a Lei n.º 22/11 (`RN-14.2`)._
> 

### [Q-C15-05] Os Coordenadores de Curso e Directores de Turma devem ter visibilidade da média geral da escola ou apenas das suas turmas?
_Por que importa: Configura a política de privacidade e agregação dos painéis (`RN-17.2.3`)._
> 

### [Q-C15-06] Quem deve ser o destinatário dos alertas automáticos quando uma turma apresenta mais de 30% de negativas numa avaliação?
_Por que importa: Configura os destinatários da notificação de risco pedagógico (`alertas_gestao`)._
> 

### [Q-C15-11] Os painéis estatísticos pedagógicos da Subdireção devem exibir as notas em tempo real à medida que são digitadas ou apenas após o fecho formal da mini-pauta?
_Por que importa: Configura se os indicadores usam dados provisórios ou definitivos (`RN-17.4`)._
> 

### [Q-APD-05] O atestado médico apresentado pelo estudante é arquivado em pasta confidencial restrita ou fica no processo pedagógico geral?
_Por que importa: Garante a segregação física e lógica do compartimento de saúde (`APD-11`)._
> 

### [Q-APD-10] Que medidas de segurança pedagógica são adotadas se os professores acederem ao SGE a partir de equipamentos próprios em casa?
_Por que importa: Define as regras de política de utilização aceitável de dispositivos pessoais._
> 

### [MIG-Q25] Existe alguma plataforma digital da Direção Provincial ou do Ministério com dados de alunos que possa ser usada para pré-carregar turmas?
_Por que importa: Identifica eventuais pontes de integração direta na migração inicial._
> 

### [MIG-Q27] A escola pretende manter no processo digital do SGE uma cópia digitalizada de todas as peças ou basta o registo da existência do documento?
_Por que importa: Dimensiona a volumetria de armazenamento no servidor local._
> 

### [Q-033] Confirma-se a utilização oficial das designações "Turno" (e não Período) e "Disciplina" (e não Cadeira) na terminologia do sistema?
_Por que importa: Consolida o vocabulário ubíquo do SGE nos relatórios impressos._
> 

---

## Observações Adicionais

Existe alguma particularidade pedagógica ou norma interna do IPCAG que considere essencial para o funcionamento do sistema e que não esteja refletida nas questões acima?

> 
