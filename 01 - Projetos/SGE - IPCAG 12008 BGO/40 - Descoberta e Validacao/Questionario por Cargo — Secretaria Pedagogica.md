---
title: "Questionário por Cargo — Secretaria Pedagógica (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Secretaria Pedagógica"
  - "DSC-04-SEC-PED"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-04-SEC-PED"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - secretaria-pedagogica
---

# Questionário de Parametrização: Secretaria Pedagógica

**Finalidade:** Recolher os parâmetros de configuração e práticas operacionais reais da Secretaria Pedagógica para configurar os módulos de Matrícula, Processo Individual (`C03`), Certificação (`C09`), Estatística (`C15`) e Migração de Dados (`C17`), cumprindo a diretriz da `DEC-009` (Pontos de Controlo PC-E1 e PC-E2).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Chefe da Secretaria Pedagógica (`CHEFE_SEC_PED`) e Oficiais Pedagógicos (`OP_PED`)  
**Como as suas respostas serão usadas:** As respostas serão inseridas diretamente como parâmetros de sistema no SGE e nos modelos de documentos oficiais (`DOF-01` a `DOF-12`), sem necessidade de alterações estruturais ao código.

## Contexto

A especificação v2.0 do Sistema de Gestão Escolar (SGE) para o IPCAG N.º 12008 / BGO está estruturalmente fechada. O sistema foi concebido para ser altamente configurável: os prazos de entrega de documentos, modelos de cartões, regras de ordenação de pautas, checklists de matrícula e sequências de livros físicos são geridos por tabelas de parâmetros. Este questionário reúne 47 questões identificadas na triagem técnica para as quais apenas a equipa da Secretaria Pedagógica detém o conhecimento prático da rotina escolar.

## Como responder

- **Prazo sugerido:** Entrega até ao Ponto de Controlo PC-E1 (antes do início do período de matrículas de 2027/2028).
- **Sem pressão de formalismo:** Respostas curtas, anotações práticas ou indicação de "como fazemos hoje" são perfeitamente aceites.
- Se algum ponto não for aplicável ou for desconhecido, assinale com `?` ou indique quem poderá esclarecer.

---

## 1. Processo Individual, Matrícula e Validação Documental

### [Q-C03-01] Quais são exatamente os documentos exigidos para Matrícula (10ª Classe), Confirmação (11ª–13ª) e Transferência de Entrada?
_Por que importa: Configura o checklist obrigatório de validação documental no ecrã de matrícula (`RN-11.2`)._
> 

### [Q-C03-04] O Certificado original da 9ª Classe fica retido no processo físico ou a escola aceita cópia autenticada?
_Por que importa: Define o alerta de custódia documental física no sistema (`RN-11.4.2`)._
> 

### [Q-C03-03] Atestado médico de aptidão física: qual é a validade exigida e que entidade o pode emitir?
_Por que importa: Configura a regra de validação do atestado no compartimento de saúde (`RN-11.3.4`)._
> 

### [Q-C03-05] Que documentos comprovativos são exigidos ao Encarregado de Educação e em caso de alteração de tutor?
_Por que importa: Evita cadastros indevidos e parametriza a validação do parentesco legal (`RN-11.9.2`)._
> 

### [Q-C03-06] Qual é o prazo limite concedido ao encarregado para entregar documentos em falta e qual a consequência do incumprimento?
_Por que importa: Configura o temporizador automático de pendências (`RN-11.6.3`)._
> 

### [Q-C03-07] Que documentos em falta impedem que atos académicos específicos (ex.: falta de BI bloqueia emissão de certificado)?
_Por que importa: Configura a matriz de bloqueios automáticos da Secretaria (`RN-11.7`)._
> 

### [Q-C03-11] Que documento probatório é exigido para retificação de nome ou data de nascimento de um aluno já matriculado?
_Por que importa: Define os requisitos do fluxo de alteração de dados pessoais (`RN-11.8.2`)._
> 

### [Q-C03-12] O aluno pode ingressar com Cédula Pessoal? Há prazo obrigatório para apresentação do BI definitivo?
_Por que importa: Configura o estado de pendência de identificação civil (`RN-11.8.4`)._
> 

### [Q-C03-13] Como é feita a digitalização dos processos? Que peças do processo físico devem ser obrigatoriamente digitalizadas?
_Por que importa: Dimensiona o repositório de anexos digitalizados (`RN-11.5`)._
> 

### [Q-C03-14] Em caso de transferência de saída, que documentos originais são devolvidos ao encarregado e quais ficam arquivados na escola?
_Por que importa: Define a guia de entrega de espólio documental na transferência (`RN-11.13`)._
> 

### [Q-C03-18] Qual é a regra de numeração dos boletins de matrícula? Reinicia a cada ano letivo?
_Por que importa: Configura o gerador de séries em `series_numeracao_documental` (`RN-11.14`)._
> 

### [Q-C03-20] A nacionalidade do estudante deve constar impressa no boletim de matrícula ou apenas nos certificados finais?
_Por que importa: Ajusta o modelo visual do boletim (`DOF-01`, `RN-11.8.6`)._
> 

### [Q-APD-13] A Secretaria verifica formalmente quem detém o poder paternal (guarda judicial, tutela) em caso de encarregado que não seja pai/mãe?
_Por que importa: Assegura conformidade com o art. 13.º da Lei n.º 22/11 da APD._
> 

### [Q-APD-28] Para que finalidade específica é recolhido o campo "problema de saúde" na ficha de matrícula e quem tem acesso físico a ele?
_Por que importa: Garante o cumprimento do princípio da finalidade estrita para dados de saúde sensíveis._
> 

### [Q08-10] Qual é a máscara exata de validação do Bilhete de Identidade angolano (ex.: 9 dígitos + 2 letras + 3 dígitos)?
_Por que importa: Configura a expressão regular de validação no formulário de entrada._
> 

### [MIG-Q23] Na digitação dos nomes dos alunos, prefere-se TUDO EM MAIÚSCULAS ou Iniciais Maiúsculas com minúsculas?
_Por que importa: Configura a rotina de normalização automática de nomes na importação._
> 

---

## 2. Cartão de Estudante e Fotografias

### [Q-C03-08] Cartão de estudante: qual é o suporte (PVC ou papel plastificado), prazo de validade e taxa cobrada por 2.ª via?
_Por que importa: Modela os atributos do cartão e o preçário de reemissão (`RN-11.10`)._
> 

### [Q-C03-02] Fotografias: quantas fotos tipo passe são pedidas e a Secretaria dispõe de webcam para capturar a foto no ato?
_Por que importa: Define o fluxo de captura digital vs carregamento de ficheiro no balcão (`RN-11.11`)._
> 

### [Q-APD-06] Para que fins são utilizadas as fotografias dos alunos além do processo individual e do cartão de estudante?
_Por que importa: Modela as finalidades no termo de consentimento informado (`CON-03`)._
> 

---

## 3. Pautas Históricas, Classificações e Migração de Dados

### [MIG-Q01] Onde se encontram atualmente arquivados os dados de identificação dos alunos ativos (livros, fichas em papel, folhas Excel)?
_Por que importa: Planeia os lotes e fontes de carga inicial da migração (`C17`)._
> 

### [MIG-Q03] Como é atribuído e formatado o Número de Processo Individual dos alunos existentes?
_Por que importa: Garante a compatibilidade e a criação de aliases para processos antigos (`AJ-05`)._
> 

### [MIG-Q04] Onde se encontram as Pautas Gerais homologadas dos anos letivos anteriores (10ª à 12ª classes)?
_Por que importa: Organiza o cronograma de digitação e conferência do histórico académico._
> 

### [MIG-Q05] As pautas antigas arquivadas contêm as notas trimestrais (MT1–MT3) e exame, ou contêm apenas a Classificação Final (CFD)?
_Por que importa: Define a profundidade da carga no ficheiro modelo `MIG-F08` (`AJ-08`)._
> 

### [MIG-Q08] Existe uma lista consolidada das cadeiras em atraso e exames extraordinários dos alunos ativos?
_Por que importa: Alimenta a folha `MIG-F10` antes do arranque do ano letivo._
> 

### [MIG-Q17] Existem requerimentos ou declarações pagas por alunos antigos que ainda não foram emitidos ou levantados?
_Por que importa: Regista pendências de atendimento anteriores à entrada do SGE._
> 

### [MIG-Q28] As Guias de Transferência e Certificados de alunos transferidos de outras escolas estão anexados aos respetivos processos físicos?
_Por que importa: Alimenta o ficheiro de histórico externo `MIG-F11`._
> 

### [Q-C16-18] Nas Pautas Gerais em papel, em que secção ou coluna são inscritos os alunos transferidos e os retidos por faltas?
_Por que importa: Ajusta o modelo de pauta geral anual (`DOF-08B`) às categorias históricas._
> 

### [Q08-08] Qual é a convenção exata de ordenação alfabética das listas de chamada (ordenação por primeiro nome ou por apelido)?
_Por que importa: Configura o algoritmo de ordenação da lista de chamada (`RN-05`)._
> 

### [Q-014] Quais são as contagens reais de alunos por turma e mini-pautas ativas no presente ano letivo?
_Por que importa: Calibra o dimensionamento de carga do servidor local._
> 

---

## 4. Livros Físicos, Emissão Documental e Certificação

### [MIG-Q18] Que Livros de Registo Físico existem na Secretaria (Termos de Exame, Matrículas, Certificados) e quais os últimos termos lavrados?
_Por que importa: Permite fixar o ponto de passagem nos livros físicos (`livros_registo_fisico`, `RN-10`)._
> 

### [MIG-Q19] Existe um livro de registo ou base de dados de todos os Certificados e Diplomas já emitidos no passado?
_Por que importa: Assegura a unicidade na verificação de 2.ª via (`MIG-F21`)._
> 

### [MIG-Q21] Qual é o procedimento tradicional e o emolumento cobrado para emissão de 2.ª via de documentos antigos?
_Por que importa: Configura o preçário e o fluxo de reemissão com QR Code (`DEC-025`)._
> 

### [MIG-Q39] Qual é o prazo médio de resposta da Secretaria a um antigo aluno cujo processo está no arquivo inativo?
_Por que importa: Fixa o SLA do módulo de atendimento ao público._
> 

### [MIG-Q42] Que modelos de documentos escolares possuem série documental anual própria e reiniciam a numeração em cada ano civil?
_Por que importa: Configura a tabela `series_numeracao_documental`._
> 

### [Q-APD-08] Qual é o prazo em que a Secretaria guarda os livros de termos e qual o procedimento em caso de erro material num termo já lavrado?
_Por que importa: Modela a regra de substituição e preservação permanente arquivística (`PC-01`)._
> 

### [Q-APD-30] Quais são os efeitos/finalidades que podem ser selecionados num pedido de declaração (ex.: serviço militar, emprego, universidade)?
_Por que importa: Configura o menu de opções do requerimento de declaração (`DOF-09B`)._
> 

### [Q08-09] Qual é a regra oficial de escrita por extenso de notas em certificados (ex.: "14 (catorze) valores" ou "Catorze valores")?
_Por que importa: Configura o template de impressão do `DOF-10`._
> 

---

## 5. Relações Institucionais, Estatística e Arquivo

### [Q-018] Qual é a designação oficial exata do órgão provincial que recebe os mapas estatísticos da escola?
_Por que importa: Configura o cabeçalho oficial do mapa estatístico trimestral (`DOF-12`)._
> 

### [Q-LEG-08] Algum dos quatro cursos técnicos ministrados no IPCAG confere dupla certificação profissional ou habilitação específica?
_Por que importa: Configura as menções especiais nos certificados de habilitações._
> 

### [Q-LEG-15] A Direção Provincial da Educação do Bengo exige um modelo em papel específico ou uma plataforma digital para receção dos mapas estatísticos?
_Por que importa: Define o formato de exportação do módulo de estatística escolar (`C15`)._
> 

### [Q-APD-07] As pautas de avaliação continuam a ser afixadas fisicamente em vitrines da escola? Que colunas ficam expostas ao público?
_Por que importa: Define o modelo de impressão pública anonimizada de pautas sem expor dados confidenciais._
> 

### [Q-APD-12] Que dados nominais de alunos ou encarregados a escola é obrigada por lei a enviar à Direção Provincial, GEPE, Diocese ou bancos?
_Por que importa: Mapeia as transferências de dados no Registo de Tratamentos da APD._
> 

### [Q-C15-12] Como são definidas formalmente as categorias estatísticas dos mapas oficiais (alunos transferidos, desistentes, dispensados)?
_Por que importa: Garante que os contadores automáticos do SGE batem certo com as fórmulas da inspeção escolar._
> 

### [Q-C16-14] Onde e em que condições são conservados os processos físicos dos estudantes que concluem o curso ou abandonam a escola?
_Por que importa: Alinha o sistema com a Lei Geral dos Arquivos (Lei n.º 14/17)._
> 

### [Q09-11] Com que periodicidade a escola submete mapas de aproveitamento à Direção Provincial e quem assina esses mapas?
_Por que importa: Modela o circuito de aprovação do relatório estatístico provincial._
> 

### [Q-008] Qual é a percentagem estimada de encarregados de educação que utilizam telemóvel simples (sem WhatsApp/Internet) vs smartphone?
_Por que importa: Calibra o uso do canal impresso vs SMS/Portal._
> 

### [Q-022] Existe formalmente um Edital aprovado para o concurso de admissão à 10ª Classe que a escola afixe anualmente?
_Por que importa: Avalia a inclusão de modelo oficial de edital no catálogo documental._
> 

---

## Observações Adicionais

Existe algum procedimento, formulário ou particularidade da Secretaria Pedagógica que não tenha sido perguntado acima e que considere relevante?

> 
