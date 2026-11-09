---
title: "Questionário por Cargo — Direção Geral e Comissão de Gestão (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Direção Geral e Comissão de Gestão"
  - "DSC-08-DIR-GERAL"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-08-DIR-GERAL"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - direcao-geral
  - comissao-de-gestao
---

# Questionário de Parametrização e Governação: Direção Geral e Comissão de Gestão

**Finalidade:** Obter as decisões institucionais de topo, parâmetros regulamentares, enquadramento jurídico do estabelecimento, políticas de proteção de dados (`APD-11`), matriz de segregação de funções e metas estratégicas de expansão para configurar o SGE de acordo com a `DEC-009`, `DEC-020` e `DEC-021` (Pontos de Controlo PC-E1 a PC-E3).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Diretor Geral (`DIR_GERAL`), Membros da Comissão de Gestão e Direção da Escola  
**Como as suas respostas serão usadas:** As respostas serão inseridas em `parametros_instituicao`, nos modelos de chancelas oficiais, nas regras de controlo financeiro e na formalização da notificação do tratamento de dados junto da Agência de Proteção de Dados (APD).

## Contexto

A especificação v2.0 do SGE está estruturalmente concluída. O sistema comporta arquitetura de permissões baseada em papéis (RBAC, `DEC-012`), funcionamento do servidor nas instalações do Panguila com cópia segura em Angola (`DEC-006`), e mecanismos de contingência em caso de falhas externas. As questões reunidas neste questionário dizem respeito a atos de soberania institucional, homologações de topo e opções regulamentares da escola.

## Como responder

- **Prazo sugerido:** Sessão de validação presencial ou preenchimento até ao Ponto de Controlo PC-E1.
- Respostas diretas baseadas no Regulamento Interno da Escola e nas deliberações da Comissão de Gestão.
- Pode anexar cópia do Alvará de Autorização, Acordo de Cedência ou Regulamento Interno nos pontos indicados.

---

## 1. Identidade Institucional, Atos Legais e Chancelas Oficiais

### [MIG-Q43 / Q-027 / Q-C03-19] Qual é o número oficial definitivo da escola perante o Ministério da Educação e Gabinete Provincial: N.º 12008 ou N.º 8009?
_Por que importa: O sistema foi concebido para suportar ambos os números de forma parametrizável (`parametros_instituicao.numero_escola_secundario`). O preenchimento define o cabeçalho impresso oficial em diplomas, certificados, pautas e cartões de estudante._
> 

### [HITL / DEC-020 / DEC-021 / Q-APD-02 / Q-LEG-13] A Direção pode disponibilizar cópia simples do Alvará de Criação / Funcionamento e do Acordo de Gestão Compartilhada (Diocese de Caxito e Estado Angolano)? Indique também o tipo de enquadramento da escola (ex.: escola pública de gestão confiada à Igreja ou escola privada em parceria) e o n.º e a data do ato constitutivo.
_Por que importa: Necessário para anexar ao processo de notificação prévia obrigatória à Agência de Proteção de Dados (APD) e preencher os dados de pessoa coletiva responsável (`Q-APD-01`) e os campos **Tipo de Entidade / Enquadramento** e **Ato Constitutivo** de `parametros_instituicao` (`DEC-020`)._
> 

### [Q-009] Existe intenção da Diocese de Caxito em alargar futuramente o uso deste modelo de sistema a outras instituições de ensino sob a sua tutela?
_Por que importa: Valida a parametrização de instalação única e multi-instituição adotada na `DEC-001`._
> 

### [Q-C15-07] Que mapas estatísticos ou relatórios periódicos são formalmente exigidos pelo Gabinete Provincial da Educação do Bengo e pela Diocese de Caxito?
_Por que importa: Configura o gerador de mapas oficiais de aproveitamento e mapas de efetivos do módulo `C15`._
> 

---

## 2. Proteção de Dados Pessoais (Lei n.º 22/11) e Privacidade

### [Q-APD-01] Qual é a designação social completa da pessoa coletiva que tutela o tratamento dos dados dos alunos (ex.: IPCAG, Diocese de Caxito ou Direção Provincial) e quem detém poderes para assinar a notificação à APD?
_Por que importa: Identifica formalmente o Responsável pelo Tratamento nos termos do art. 3.º da Lei n.º 22/11 e preenche o Aviso de Privacidade do SGE._
> 

### [Q-APD-03] A escola já submeteu anteriormente à Agência de Proteção de Dados (APD) algum pedido de autorização ou notificação de ficheiros manuais ou informáticos?
_Por que importa: Permite instruir a notificação do SGE como registo novo ou como atualização de notificação existente._
> 

### [Q-APD-29] O campo "Profissão/Ocupação dos Pais" na ficha de matrícula tem utilidade pedagógica estrita ou pode ser eliminado para cumprimento do princípio da minimização de dados?
_Por que importa: Em caso de ausência de finalidade legal comprovada, o campo será inativado no formulário de matrícula (`RN-11.2`)._
> 

### [Q-C03-09] Na leitura pública por telemóvel do QR Code do Cartão de Estudante (para verificação de autenticidade por terceiros), que dados devem ser visíveis, tratando-se maioritariamente de menores de idade?
_Por que importa: A especificação propõe exibir apenas Nome, Fotografia, Número de Matrícula, Curso e Validade, ocultando filiação e morada para salvaguarda de privacidade (`APD-11 §7.3`)._
> 

### [Q-C03-16] Que funcionários e cargos têm autorização para aceder às cópias dos Bilhetes de Identidade e aos atestados médicos dos alunos arquivados digitalmente?
_Por que importa: Calibra o controlo estrito de acessos (RBAC) e o registo de auditoria de visualização de dados sensíveis (`RN-11.12`)._
> 

### [Q-APD-11] A escola possui câmaras de videovigilância em funcionamento no recinto escolar ou prevê a sua instalação?
_Por que importa: Se existirem, devem constar obrigatoriamente no Dossiê Global de Notificação à APD a submeter pela instituição._
> 

### [Q-APD-33] Qual o canal formal e seguro acordado entre a Direção da escola e a equipa de engenharia para envio de documentos administrativos com dados de teste?
_Por que importa: Garante que não sejam transmitidos dados reais de alunos e professores por aplicações de mensagens instantâneas desprovidas de canal corporativo cifrado._
> 

---

## 3. Gestão Académica, Horários e Pessoal Docente

### [Q-C04-03] Quem é a entidade competente para elaborar e homologar o horário geral dos professores: a homologação cabe unicamente ao Subdiretor Pedagógico ou exige Visto prévio do Diretor Geral?
_Por que importa: Configura o fluxo de aprovação e o bloqueio de alterações ao horário após a sua entrada em vigor (`RN-12.2`)._
> 

### [Q-C04-05] É permitida a acumulação de funções letivas ou administrativas de professores noutras escolas do Estado ou privadas? Que despacho autorizador é exigido?
_Por que importa: Parametriza o alerta de sobreposição de cargas horárias e o registo da autorização de acumulação no cadastro (`RN-12.6`)._
> 

### [Q-C04-17] Quem tem competência na escola para homologar o calendário de feriados, pausas letivas e suspensões extraordinárias de aulas?
_Por que importa: Atribui a permissão de edição do calendário escolar institucional (`RN-12.12`)._
> 

### [Q08-01] Para a meta de expansão até 1.500 alunos, a Direção prevê a construção/requisição de mais salas físicas ou o alargamento a um novo turno (noturno)?
_Por que importa: Orienta as projeções de volumetria de dados e o dimensionamento de sessões simultâneas do servidor local._
> 

### [Q-C13-05] Quando um aluno é alvo de sanção de suspensão de aulas, os dias de ausência são averbados como faltas justificadas ou injustificadas? O aluno pode realizar provas durante esse período?
_Por que importa: Configura o cálculo automático de assiduidade e a marcação de provas de recuperação no livro de turma (`RN-15.5`)._
> 

### [Q-C13-06] Qual é o procedimento de recurso das decisões disciplinares aplicadas pela Direção e onde pode ser consultada uma cópia do Regulamento Interno em vigor?
_Por que importa: Parametriza os prazos legais de recurso administrativo previstos no módulo disciplinar (`RN-15.4` e `RN-15.6`)._
> 

---

## 4. Tesouraria, Controlo Financeiro e Relação com Alunos Maiores

### [Q-C03-10] O aluno que atinge a maioridade (18 anos) passa a ser considerado o único responsável legal perante a escola e a Tesouraria, ou o encarregado de educação inicial mantém-se responsável solidário?
_Por que importa: Define quem pode assinar acordos de liquidação de dívida e receber notificações financeiras oficiais (`RN-11.9.5`)._
> 

### [Q-C10-03] A celebração de um plano de pagamento em prestações de propinas em atraso autoriza a libertação imediata de semáforo verde para emissão de boletins e certificados, ou estes só são emitidos após quitação integral?
_Por que importa: Configura o interruptor de política financeira `liberta_semaforo` (`RN-13.8`)._
> 

### [Q-C10-11] Que procedimento e prazo limite são aplicados pela Direção para declarar uma dívida de propinas de ex-aluno como "incobrável"? Quem tem competência para autorizar a anulação do saldo em dívida?
_Por que importa: Parametriza a passagem de saldos a perdas e o bloqueio de matrícula em caso de regresso do estudante (`RN-13.18`)._
> 

### [Q-C12-03] No portal web de encarregados de educação (a disponibilizar na E5), se um educando tiver propinas em atraso, deve ser bloqueada a descarga do Boletim de Notas ou o boletim deve ser visualizado com marca de água de pendência financeira?
_Por que importa: Parametriza a integração do semáforo financeiro com a visualização do aproveitamento escolar (`RN-08.2` e `RN-14.10`)._
> 

---

## 5. Governação, Utilizadores, Autenticação Forte e Operação do Sistema

### [Q-C14-01] Quem nomeia formalmente os operadores do SGE para cada cargo e qual o documento que suporta a ativação da conta (Despacho do Diretor Geral)?
_Por que importa: Garante que cada conta de utilizador esteja associada a uma referência documental legal de nomeação para efeitos de auditoria (`RN-16.2`)._
> 

### [Q-C14-02] Quem é a pessoa designada para assumir a função de Administrador Técnico Local (`ADMIN_TEC`) e quem será o seu substituto legal na guarda das credenciais mestre em cofre?
_Por que importa: Cumpre a diretriz da `DEC-012` e `DEC-017` sobre segregação de funções e custódia segura da infraestrutura._
> 

### [Q-C14-05] Existem funcionários que acumulam atualmente cargos distintos (por exemplo, Chefe de Secretaria que também ministra aulas)?
_Por que importa: Configura os perfis compostos na matriz de incompatibilidades de permissões (`RN-16.5`)._
> 

### [Q-C14-10] A Direção aprova a obrigatoriedade de assinatura física de um "Termo de Responsabilidade e Confidencialidade" no ato de entrega das credenciais de acesso ao SGE?
_Por que importa: Reforça o compromisso de sigilo profissional exigido pela Lei n.º 22/11 aos operadores do sistema._
> 

### [Q08-04 / Q-C14-11] A exigência de Segundo Fator de Autenticação (MFA via código no telemóvel) deve abranger obrigatoriamente, além da Direção Geral e Subdiretores, o Chefe da Secretaria Pedagógica e Operadores de Tesouraria?
_Por que importa: Parametriza a política de segurança de acessos críticos (`RN-16.12`)._
> 

### [Q-C14-13] Qual o prazo deliberado pela Direção para a conservação e histórico dos registos de acessos e operações (logs de auditoria): 12 meses (proposta padrão) ou prazo superior?
_Por que importa: Configura a rotina de purga automática de logs de segurança em harmonia com a Lei n.º 22/11 (`APD-11 PC-27`)._
> 

### [Q08-14] Na aplicação dos professores para sumários offline no telemóvel, as operações concluídas devem ser eliminadas imediatamente após a sincronização ou guardadas por 7 dias como histórico local?
_Por que importa: Calibra o parâmetro de retenção do armazenamento local do dispositivo móvel (`RF-C19-26`)._
> 

### [Q08-11] Quais são as janelas horárias mais adequadas para realização de rotinas de manutenção preventiva no servidor (ex.: sábados após as 14h ou domingos)?
_Por que importa: Configura os alertas e o agendamento de atualizações do servidor local sem perturbação das aulas (`RNF-MAN-02`)._
> 

### [Q09-06] Qual é a pessoa de confiança e o local físico exterior ao edifício da escola onde será depositada a cópia semanal de segurança (cópia externa offline)?
_Por que importa: Garante o cumprimento do plano de recuperação de desastres elétricos ou sinistros físicos (`RNF-BKP-04`)._
> 

### [Q09-07] Qual é o nível de dedicação de tempo acordado para o Administrador Técnico Local prestar apoio aos utilizadores durante os turnos letivos?
_Por que importa: Dimensiona a prontidão do suporte técnico de primeiro e segundo nível (`N1`/`N2`, `DEC-017`)._
> 

### [Q09-09] Qual é a empresa ou consultor que assegurará o Suporte de Nível 3 (`N3`) para atualizações complexas da base de dados e reparação especializada?
_Por que importa: Define os contactos de emergência a configurar na consola de administração do sistema._
> 

### [Q09-10] A escola ou a Diocese dispõem de domínio de internet próprio (ex.: `ipcag.ao` ou `diocesecaxito.ao`) ou será necessário proceder ao registo de um novo domínio oficial?
_Por que importa: Configura o endereço web público dos portais de validação de documentos por QR Code e portal de encarregados._
> 

### [Q09-12] Relativamente ao envio de SMS para avisos institucionais e notas aos encarregados de educação: a escola prevê suportar os custos de tráfego com o orçamento de propinas ou a comunicação será restrita ao portal e balcão?
_Por que importa: Parametriza a ativação do fornecedor de gateways de SMS na entrega E5 (`DEC-003`)._
> 

### [Q-C12-02] A Direção autoriza canais institucionais de comunicação com alunos e encarregados via WhatsApp corporativo oficial, ou proíbe a criação de grupos informais de turma?
_Por que importa: Parametriza a política de canais de notificação (`RN-14`)._
> 

### [Q09-13] Os professores utilizam os seus próprios telemóveis e pacotes de dados para sumários escolares, ou a escola disponibiliza ligação Wi-Fi institucional dedicada na sala de professores?
_Por que importa: Orienta a configuração da rede interna e a política de consumo de dados da aplicação docente._
> 

---

## 6. Planeamento do Ano Letivo 2027/2028 e Migração de Dados

### [MIG-Q30] Quais são as datas oficiais previstas para o arranque das matrículas de novos alunos e o início efetivo das aulas do ano letivo 2027/2028?
_Por que importa: Fixa os prazos de congelamento da implantação da v2.0 e o calendário de corte de dados (`DEC-007`)._
> 

### [MIG-Q35] Quem são os utilizadores-chave indicados pela Direção em cada turno e secretaria para integrarem a primeira turma de formação intensiva?
_Por que importa: Estabelece a lista nominal de formandos e planos de contingência funcional._
> 

### [MIG-Q26] Quem serão os funcionários administrativos encarregados da digitação e validação assistida dos dados dos alunos atuais durante a fase de transição?
_Por que importa: Planeia a escala de trabalho e a emissão de termos de confidencialidade adicionais para digitação de lotes de dados._
> 

### [MIG-Q06] No carregamento histórico inicial, quantos anos anteriores de antigos alunos concluintes a escola pretende arquivar no SGE para efeitos de emissão ágil de 2.ª via de certificados?
_Por que importa: Dimensiona a equipa de apoio à digitalização e o volume de fichas em papel a inventariar._
> 

### [MIG-Q02] A escola utiliza atualmente algum software de apoio (ex.: folhas de cálculo Microsoft Excel, software de faturação ou bases Access)? Quem é o responsável técnico por essas cópias?
_Por que importa: Determina a necessidade de scripts específicos de extração e conversão de ficheiros para o modelo do SGE (`C17`)._
> 

### [Q-C15-01 / Q-C15-10] Que indicadores e painéis visuais a Direção Geral pretende consultar com maior assiduidade (ex.: taxa de cobrança de propinas, ocupação de salas, faltas de professores) e através de que dispositivo (computador de secretária, computador portátil ou tablet)?
_Por que importa: Guia o desenho dos painéis de bordo executivos do módulo `C15`._
> 
