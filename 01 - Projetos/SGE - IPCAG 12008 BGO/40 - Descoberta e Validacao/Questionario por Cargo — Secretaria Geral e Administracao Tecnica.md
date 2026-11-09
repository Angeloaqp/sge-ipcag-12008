---
title: "Questionário por Cargo — Secretaria Geral e Administração Técnica (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Secretaria Geral e Administração Técnica"
  - "DSC-07-SEC-GER"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-07-SEC-GER"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - secretaria-geral
  - administracao-tecnica
---

# Questionário de Parametrização: Secretaria Geral e Administração Técnica

**Finalidade:** Recolher dados operacionais sobre gestão de pessoal, arquivo corrente, segurança física de postos de trabalho, conectividade, energia de socorro e equipamentos informáticos para parametrizar os módulos de Autenticação e Segurança (`C14`), Gestão de Pessoal (`C11`), Operação Local (`C18`), Migração (`C17`) e Tesouraria (`C10`), cumprindo a `DEC-009` (Pontos de Controlo PC-E1 e PC-E2).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Chefe da Secretaria Geral (`CHEFE_SEC_GER`) e Administrador Técnico Local (`ADMIN_TEC`)  
**Como as suas respostas serão usadas:** As respostas serão utilizadas para calibrar tempos limite de sessão, políticas de MFA, conectividade de sincronização, dimensionamento do UPS/gerador e procedimentos de carga histórica de funcionários e dados financeiros.

## Contexto

A especificação v2.0 do SGE está estruturalmente estabilizada. O SGE funcionará no servidor local da escola com capacidade de operação offline de contingência (`DEC-006`, `DEC-013`). Para garantir que a transição seja perfeita no arranque do ano letivo 2027/2028, é essencial parametrizar com precisão as condições elétricas, de rede e de rotina de escritório da Secretaria Geral e da equipa técnica.

## Como responder

- **Prazo sugerido:** Entrega até ao Ponto de Controlo PC-E1.
- Respostas breves, dados reais de campo ou anotações das práticas atuais.
- Assinale com `?` caso algum ponto requeira medição ou confirmação posterior.

---

## 1. Cadastro de Funcionários e Gestão de Pessoal (RH / Secretaria Geral)

### [MIG-Q24] Onde estão arquivados os processos dos funcionários e professores? Todos possuem Número de Agente do Estado?
_Por que importa: Mapeia as fontes de carga para a migração inicial (`C11`) e a regra de preenchimento do N.º de Agente para os docentes públicos destacados (achado `A15`)._
> 

### [Q-C04-10] Como são registadas atualmente as faltas dos professores (por tempo letivo ou por dia de serviço) e qual o impacto no livro de ponto físico?
_Por que importa: Configura o parâmetro `RN-12.14.6` de equivalência de faltas e integração entre o horário semanal e a folha de assiduidade._
> 

### [Q08-02] Qual é o número total estimado de professores e funcionários administrativos em funções na escola? Quantos possuem telemóvel próprio com capacidade para aplicações?
_Por que importa: Dimensiona a volumetria de utilizadores do SGE (`C14`) e a adesão ao módulo móvel de lançamento de notas e sumários._
> 

### [Q09-14] Todos os funcionários e professores dispõem de endereço de correio eletrónico (email) ativo? A escola disponibiliza email institucional?
_Por que importa: Define o fluxo de recuperação de credenciais de acesso (via email ou presencial perante o `ADMIN_TEC`/`CHEFE_SEC_GER`, conforme `RN-16.10`)._
> 

### [HITL / DEC-019 / Q-APD-04] Qual é o email e o telefone institucionais da Secretaria Geral a indicar como ponto de contacto de proteção de dados nos avisos de privacidade?
_Por que importa: Conforme a `DEC-019`, o ponto de contacto é operado pelo `CHEFE_SEC_GER` sob a tutela do `DIR_GERAL` (`MOD-GOV-09`); o contacto é impresso nos avisos `AV-01` a `AV-06` e na cláusula do `DOF-03` (APD-11 §4.4)._
> 

---

## 2. Postos de Trabalho, Horários de Balcão e Segurança de Acesso

### [Q-C14-08] Qual é o horário oficial de funcionamento contínuo do balcão da Secretaria Geral e da Tesouraria?
_Por que importa: Configura o parâmetro de expiração máxima e fecho automático de sessões de balcão (`RN-16.8`)._
> 

### [Q-C14-09] Existem computadores de balcão partilhados entre múltiplos operadores de serviço?
_Por que importa: Configura a política de bloqueio automático de ecrã após inatividade e a exigência de sessão única e intransmissível por utilizador (`RN-16.9`)._
> 

### [Q-C14-03] Que canais de contacto (email institucional, SMS ou telemóvel) devem ser utilizados para recuperação de palavra-passe e segundo fator de autenticação (MFA)?
_Por que importa: Parametriza as opções disponíveis no ecrã de recuperação de conta e autenticação forte (`RNF 08`)._
> 

### [Q-C10-05] Como é efetuada atualmente a notificação de dívidas a encarregados de educação? É enviado aviso impresso em envelope fechado?
_Por que importa: Parametriza o canal de comunicação de cobrança e garante conformidade com a Lei n.º 22/11 (APD-11 §7 e `RN-13.6`)._
> 

---

## 3. Tesouraria, Borderôs e Extratos Bancários (Histórico e Operação)

### [MIG-Q09] Onde e em que suporte (cadernos, folhas de cálculo Excel, recibos em papel) estão registadas as dívidas históricas de propinas?
_Por que importa: Define a estratégia e o limite temporal da carga histórica de devedores no corte para o SGE (`C17`)._
> 

### [MIG-Q12] No histórico da escola, foram admitidos pagamentos parciais de prestações mensais de propina? Se sim, como eram documentados?
_Por que importa: Calibra o conversor de migração (`AJ-09`) para rececionar saldos parcelares legados, ainda que o SGE opere por prestações inteiras (`DEC-023`)._
> 

### [MIG-Q13] A Tesouraria mantém um arquivo ou livro de registo com os números de operação dos borderôs bancários aceites?
_Por que importa: Configura as rotinas de verificação e deteção automática de borderôs duplicados durante a migração inicial e rotina diária._
> 

### [Q-C10-08] Com que frequência a escola obtém extratos bancários das contas de depósito e que formato é disponibilizado (PDF, ficheiro Excel/CSV ou consulta direta no internet banking)?
_Por que importa: Configura o procedimento de importação e conciliação bancária (`DEC-005` e `RN-13.14`)._
> 

### [Q-C10-09] De que forma aparecem descritas nos extratos bancários as transações via TPA da escola e transferências Multicaixa Express?
_Por que importa: Calibra as regras de correspondência automática N:M e as tolerâncias de reconciliação de pagamentos (`RN-13.15`)._
> 

---

## 4. Infraestrutura Tecnológica, Rede e Energia de Socorro (Administração Técnica)

### [Q09-04] A escola dispõe de gerador elétrico próprio? Se sim, qual a sua capacidade (kVA), tipo de arranque (manual ou automático/ATS) e autonomia de combustível?
_Por que importa: Dimensiona a autonomia requerida para o Sistema de Alimentação Ininterrupta (UPS) do servidor local do SGE (`RNF-DIS-03`)._
> 

### [Q09-05] Quais são os fornecedores de acesso à internet atualmente contratados na escola? Existe cobertura estável de um segundo operador móvel/fixo na zona do Panguila?
_Por que importa: Valida a viabilidade da sincronização diária e a redundância da conectividade de contingência (`DEC-006`)._
> 

### [Q08-13] Como é a cobertura de sinal de rede (Wi-Fi e rede celular 3G/4G) nas salas de aula e áreas pedagógicas?
_Por que importa: Define se os professores necessitarão de sincronização diferida (offline local de 7 dias) no telemóvel para sumários e assiduidade (`RNF 07`)._
> 

### [Q08-07] Entre o corpo docente, existem utilizadores com telemóveis do sistema iOS (iPhone) ou utilizam predominantemente Android?
_Por que importa: Define o planeamento das versões da aplicação móvel ou portal responsivo para suporte ao modo offline._
> 

### [MIG-Q34] Que sala, projetor e computadores estão disponíveis na escola para a realização das sessões de formação aos utilizadores do SGE?
_Por que importa: Permite o escalonamento do plano de formação de utilizadores-chave e equipa administrativa antes do congelamento da implantação._
> 

### [Q-APD-27] Quais são os custos médios e fornecedores viáveis para alojamento da réplica de segurança externa em centro de dados localizado no território angolano?
_Por que importa: Informa a orçamentação e contratação do servidor de réplica externa em conformidade com a Lei n.º 22/11 de Proteção de Dados (`DEC-006` e `APD-11`)._
> 
