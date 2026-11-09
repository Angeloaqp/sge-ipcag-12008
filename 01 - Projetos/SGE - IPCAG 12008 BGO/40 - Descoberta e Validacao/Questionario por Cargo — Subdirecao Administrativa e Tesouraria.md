---
title: "Questionário por Cargo — Subdireção Administrativa e Tesouraria (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Subdireção Administrativa"
  - "DSC-06-SUB-ADM"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-06-SUB-ADM"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - tesouraria
  - subdirecao-administrativa
---

# Questionário de Parametrização: Subdireção Administrativa e Tesouraria

**Finalidade:** Recolher os parâmetros financeiros, fiscais e operacionais para configurar o motor de cobrança de propinas, gestão de multas, acordos de pagamento, bolsas de estudo, conciliação bancária e sessões de caixa (`C10`), bem como validar o enquadramento fiscal (AGT) e a infraestrutura tecnológica (`C18`), em cumprimento da `DEC-002`, `DEC-009`, `DEC-023` e `DEC-026` (Ponto de Controlo PC-E1).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Subdirector Administrativo (`SUB_ADM`), Responsável da Tesouraria e Contabilista da Escola  
**Como as suas respostas serão usadas:** As respostas serão introduzidas nas tabelas `parametros_instituicao`, `parametros_cobranca`, `tabelas_precos_emolumentos` e `contas_bancarias_escola`, permitindo o arranque da tesouraria na Entrega E1 com rigor contabilístico absoluto.

## Contexto

A tesouraria escolar é o coração da sustentabilidade do IPCAG. A especificação assegura que o sistema gere contas correntes de alunos, créditos de borderôs bancários, controlo do semáforo de dívida (`RN-08`) e fecho cego de caixa. Nos termos da `DEC-002`, a emissão com valor fiscal é articulada através de adaptador com software validado pela AGT. Este questionário recolhe as regras práticas de liquidação, prazos de tolerância, enquadramento do IVA e procedimentos bancários.

## Como responder

- **Prazo sugerido:** Entrega no Ponto de Controlo PC-E1 (antes da abertura das caixas de matrícula do ano letivo 2027/2028).
- Responda em conjunto entre a Subdireção Administrativa, os operadores de caixa e a Contabilidade.
- Caso algum elemento documental (certidão de NIF, comprovativo de licença de software ou preçário homologado) esteja disponível, anexe fotocópia simples.

---

## 1. Enquadramento Fiscal e Obrigações AGT (Contabilidade)

### [Q-LEG-19 / Q09-02] Qual é o Número de Identificação Fiscal (NIF) oficial do IPCAG e em que Regime de IVA se encontra inscrito na AGT (Geral, Simplificado ou Exclusão)?
_Por que importa: Conforme a `DEC-026`, o sistema suporta qualquer regime em `parametros_instituicao`. Confirma a menção obrigatória nos documentos fiscais e o modelo declarativo perante a AGT._
> 

### [HITL / DEC-026] Quem é o contabilista responsável pela escola (nome e n.º de cédula profissional)? A escola pode disponibilizar cópia simples da certidão de registo fiscal da AGT (NIF e regime de IVA)?
_Por que importa: Conforme a `DEC-026`, o NIF, o regime de IVA em vigor e o contabilista responsável são dados a recolher no PC-E1 (`DEC-009`) para configurar `parametros_instituicao` e o adaptador fiscal (`DEC-002`)._
> 

### [Q-002 / Q09-03] A escola já utiliza atualmente algum software de faturação certificado pela AGT? Se sim, qual é o nome do programa, versão da licença e dispõe de módulo de integração (API ou ficheiros SAF-T)?
_Por que importa: Conforme a `DEC-002`, o SGE integrará com este software através de adaptador fiscal._
> 

### [Q-003] Quem deve figurar formalmente como adquirente nas faturas e recibos emitidos pela escola: o estudante ou o Encarregado de Educação (com o respetivo NIF)?
_Por que importa: Configura o cabeçalho fiscal do documento e a geração do SAF-T (`C10`)._
> 

### [Q-LEG-16] Qual é o modelo comercial adotado pela escola: emissão de fatura mensal antecipada e recibo após quitação, ou emissão de Fatura-Recibo (`FR`) no momento do pagamento?
_Por que importa: Define o momento de nascimento da dívida e do documento fiscal legal (`DEC-002`)._
> 

### [Q-LEG-17] Além das propinas e taxas escolares (isentas ao abrigo do art. 12.º n.º 1 l) do CIVA), a escola pratica a venda de bens ou serviços sujeitos a IVA (ex.: batas, manuais, cantina)?
_Por que importa: Configura se a tabela `itens_recibo` aplica taxa de IVA (14%) em itens complementares._
> 

### [Q-LEG-18] Nos estudantes que beneficiam de bolsa de estudo a 100%, qual é a diretriz da contabilidade: emitir fatura com desconto de 100% ou manter o registo interno sem emissão fiscal?
_Por que importa: Configura o comportamento do gerador de faturas para o estado `ISENTA_BOLSEIRO_100`._
> 

### [Q-004 / Q-C16-16] Qual é a estrutura oficial da numeração dos recibos internos e como devem ser numerados os recibos de liquidação de dívidas de anos letivos anteriores?
_Por que importa: Configura as séries em `series_numeracao_documental` e os recibos de cobrança diferida._
> 

---

## 2. Regras de Propinas, Multas de Mora e Prazos

### [Q-C10-01] Qual é a regra exata de cobrança de multa por atraso no pagamento da propina mensal (dia limite, valor fixo ou percentagem diária/mensal e teto máximo)?
_Por que importa: Configura os campos de cálculo na tabela `parametros_cobranca` (`RN-13.3`)._
> 

### [Q-C10-06] Em quantos dias de atraso no pagamento da propina o sistema deve enviar avisos ao encarregado (ex.: aviso preventivo aos 5 dias, cobrança aos 30 dias e notificação formal aos 60 dias)?
_Por que importa: Parametriza a régua de cobrança automática da Central de Avisos (`RN-13.6`)._
> 

### [Q-C16-12] As multas de mora continuam a acumular após o encerramento do ano letivo ou o montante em dívida é congelado na data de fecho da pauta geral?
_Por que importa: Configura o encerramento da conta corrente anual do estudante (`RN-18.10.5`)._
> 

### [MIG-Q11] Na migração das dívidas históricas de anos anteriores, as multas de mora entram no saldo devedor consolidado ou transitam discriminadas do valor de capital?
_Por que importa: Modela os campos de carga no ficheiro `MIG-F18`._
> 

---

## 3. Acordos de Pagamento e Ajustes de Conta Corrente

### [Q-C10-02] Quem tem competência regulamentar para autorizar planos de pagamento em prestações de dívidas acumuladas e qual é o número máximo de tranches permitido?
_Por que importa: Configura as permissões RBAC e o limite de parcelamento em `acordos_pagamento` (`RN-13.7`)._
> 

### [Q-C10-14] O acordo de regularização de dívidas é celebrado por aluno individual ou pode abranger todas as dívidas dos educandos de um mesmo encarregado?
_Por que importa: Define se o acordo é indexado ao `encarregado_id` ou à `matricula_id`._
> 

### [Q-C10-15] Quantos dias de tolerância são concedidos após o vencimento de uma prestação do acordo antes de o plano ser considerado cancelado por incumprimento?
_Por que importa: Parametriza o temporizador do job noturno de quebra de acordos (`RN-13.9`)._
> 

### [Q-C10-04] Quem pode autorizar o perdão total ou parcial de multas de mora e que documento comprovativo deve ser anexado ao sistema?
_Por que importa: Modela a exigência de anexo de despacho na tabela `ajustes_conta_corrente` (`RN-13.4`)._
> 

### [MIG-Q33] Qual é o prazo concedido aos encarregados para reclamarem eventuais divergências na dívida inicial migrada e quem julga a reclamação?
_Por que importa: Modela o fluxo de contestação de saldo inicial na implantação (`C17`)._
> 

---

## 4. Bolsas de Estudo, Descontos e Parceria com a Diocese

### [MIG-Q16] Existe um regulamento interno escrito para atribuição de bolsas e qual é o protocolo oficial de isenção com a Diocese de Caxito?
_Por que importa: Valida a tabela `beneficios_bolsas_matricula` e o catálogo de tipos de benefício (`RN-07`)._
> 

### [Q-APD-09] Que documentos comprovativos de carência económica ou de vínculo laboral são exigidos para concessão de desconto de irmãos ou bolsa social?
_Por que importa: Define o termo de consentimento e prazo de expurgo de dados socioeconómicos sensíveis (`CON-04`)._
> 

### [Q-C16-11] A renovação do benefício de bolsa ou desconto é automática de um ano para o outro ou exige novo requerimento anual com comprovativo?
_Por que importa: Configura o motor de passagem de ano relativamente à herança de bolsas (`RN-18.11.6`)._
> 

---

## 5. Bancos, Contas da Escola, Borderôs e Conciliação

### [Q-007 / Q09-01] Em que bancos comerciais a escola detém contas bancárias ativas e quais delas recebem pagamentos de propinas por depósito, transferência ou TPA?
_Por que importa: Conforme a `DEC-023`, alimenta o catálogo `contas_bancarias_escola` (1:N com `bancos_angola`)._
> 

### [MIG-Q10] Existem depósitos bancários de encarregados em que o talão foi extraviado mas o valor deu entrada na conta da escola? Como são regularizados?
_Por que importa: Modela o tratamento de saldos credores históricos na migração inicial (`AJ-10`)._
> 

### [Q-C10-10] Quem é o responsável técnico pela conferência e conciliação dos extratos bancários com os borderôs registados no caixa? Com que frequência é realizada?
_Por que importa: Configura o perfil de operador de conciliação bancária (`RN-13.16`)._
> 

---

## 6. Operação de Caixa, Sessões e Contingência

### [Q08-03] Qual é o número médio de estudantes ou encarregados atendidos na Tesouraria num dia de pico (ex.: época de confirmação de matrículas)?
_Por que importa: Dimensiona a volumetria de transações por minuto e o número de postos de caixa em simultâneo._
> 

### [Q-C14-08] Qual é o horário oficial de abertura e encerramento dos guichês de Tesouraria?
_Por que importa: Configura o limite temporal absoluto das sessões de caixa em `sessoes_fecho_caixa`._
> 

### [Q-C14-09] Os postos de trabalho e computadores da Tesouraria são utilizados em exclusivo por cada operador ou são partilhados entre turnos?
_Por que importa: Configura as regras de bloqueio de ecrã e obrigatoriedade de encerramento de sessão._
> 

### [MIG-Q32] A Subdireção Administrativa autoriza uma pausa de 24 a 48 horas nas operações de caixa imediatamente antes do arranque para reconciliação final da carga de dados?
_Por que importa: Fixa a janela de congelamento no plano de arranque da E1 (`MIG-10 §8`)._
> 

### [Q-C10-13] A emissão de um extrato detalhado de conta corrente a pedido do encarregado de educação é gratuita ou está sujeita ao pagamento de taxa de expediente?
_Por que importa: Configura a tabela de emolumentos associada ao relatório financeiro do aluno._
> 

### [Q-C12-06] Os custos operacionais com envio de notificações por SMS (respeitando o teto mensal da `DEC-015`) são integralmente suportados pelo orçamento da escola?
_Por que importa: Garante o controlo de saldo orçamental pelo `SUB_ADM` (`RN-14.6`)._
> 

---

## 7. Relatórios de Gestão e Património

### [Q-C10-12] Que relatórios financeiros e de cobrança são exigidos periodicamente pela Direção Executiva, pela Diocese de Caxito ou pela Direção Provincial?
_Por que importa: Modela o catálogo de relatórios financeiros `REL-FIN` no módulo de tesouraria._
> 

### [Q09-15] A Diocese de Caxito exige mapas mensais consolidados de receitas de propinas? Em que formato e com que periodicidade?
_Por que importa: Configura o modelo de relatório de prestação de contas diocesana._
> 

### [Q-C15-09] O Coordenador de Turno deve ter acesso a indicadores de pontualidade e assiduidade do pessoal administrativo e da tesouraria do seu turno?
_Por que importa: Configura os escopos de visibilidade dos painéis de supervisão administrativa._
> 

### [Q-019] Como é efetuado atualmente o controlo de inventário e património físico da escola (mesas, computadores, equipamentos de laboratório)?
_Por que importa: Confirma a fronteira externa do sistema com a gestão patrimonial fora do SGE (`DEC-008`)._
> 

### [Q-006] Qual é o estado do servidor, UPS, cablagem de rede local e ligação à internet disponível na Tesouraria?
_Por que importa: Dimensiona os requisitos de infraestrutura e contingência da Entrega E1._
> 

---

## Observações Adicionais

Existe alguma regra específica de faturação, cobrança, depósito ou rotina administrativa do IPCAG que não tenha sido mencionada neste questionário?

> 
