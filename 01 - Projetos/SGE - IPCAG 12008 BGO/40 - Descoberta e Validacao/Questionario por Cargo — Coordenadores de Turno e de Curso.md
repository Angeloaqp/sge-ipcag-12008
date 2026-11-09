---
title: "Questionário por Cargo — Coordenadores de Turno e de Curso (Fase C — Parametrização e Descoberta)"
aliases:
  - "Questionário Coordenadores de Turno e de Curso"
  - "DSC-09-COORD"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-09-COORD"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - coordenacao-turno
  - coordenacao-curso
---

# Questionário de Parametrização: Coordenadores de Turno e de Curso

**Finalidade:** Obter os parâmetros operacionais de ocupação de espaços, gestão de faltas e substituição de docentes, regras de pontualidade por turno, regime de Estágio Curricular, Prova de Aptidão Profissional (PAP) / Projecto Tecnológico da 13.ª Classe e cálculo da Média Final de Curso (MFC), cumprindo a `DEC-009`, `DEC-022` e `DEC-024` (Pontos de Controlo PC-E1 e PC-E4).

**De:** Equipa de Engenharia de Requisitos e Arquitetura do SGE  
**Para:** Coordenadores de Turno (`COORD_TURNO`) e Coordenadores de Curso Técnico (`COORD_CURSO`)  
**Como as suas respostas serão usadas:** As respostas serão configuradas nas tabelas de espaços escolares (`salas_fisicas`), regras de substituição de professores (`C04`), limites de atrasos e sanções disciplinares (`C13`), e no motor de avaliação da 13.ª classe e conclusão de curso (`C08` e `C16`).

## Contexto

O SGE N.º 12008 / BGO modela fielmente a realidade do ensino técnico-profissional angolano (DP n.º 93/21). Na 13.ª classe, os alunos realizam Estágio e Projecto Tecnológico / Defesa de PAP sob regime tutorial e orientação de júris (`DEC-022`). As questões a seguir calibram o funcionamento diário dos turnos letivos (Manhã e Tarde) e a validação do processo de certificação dos cursos de Gestão, Contabilidade, Informática e outros ministrados no IPCAG.

## Como responder

- **Prazo sugerido:** Entrega até ao Ponto de Controlo PC-E1 (gestão de salas e turnos) e PC-E4 (cálculo de conclusão e PAP).
- Respostas diretas baseadas na prática dos cursos e na coordenação dos turnos.

---

## 1. Gestão de Espaços, Turnos e Substituições (Coordenadores de Turno)

### [Q-C04-08] Além das 12 salas de aula regulares, que outros espaços de ensino existem na escola (ex.: laboratórios de informática, biblioteca, oficinas)? Esses espaços são partilhados entre cursos ou atribuídos em exclusivo?
_Por que importa: Alimenta o catálogo físico de salas (`salas_fisicas`) e a verificação de colisões de alocação de turmas (`RN-12.8`)._
> 

### [Q-C15-08 / Q-C16-05] Qual é a lotação máxima real de alunos por sala de aula e por laboratório? As turmas da 13.ª Classe ocupam sala física fixa em todos os tempos letivos ou utilizam espaços rotativos de projeto/laboratório?
_Por que importa: Parametriza o limite de capacidade de turma (`RN-18.7.2`) e confirma a modelação de regime flexível para o Projecto Tecnológico da 13.ª (`DEC-022`)._
> 

### [Q-C04-09] Qual é a rotina aplicada quando um professor falta a um tempo de aula: é designado de imediato um professor substituto do mesmo turno ou o tempo é preenchido com estudo acompanhado? A partir de quantos dias de ausência é formalizada uma substituição oficial no livro de ponto?
_Por que importa: Configura as regras de substituição temporária e prolongada na grelha de assiduidade docente (`RN-12.14` e `RN-04`)._
> 

### [Q-C13-04] Quantos minutos de tolerância à entrada são concedidos aos alunos em cada turno (ex.: 15 minutos)? Quantos atrasos injustificados acumulados no mesmo mês dão origem a uma participação disciplinar ou falta vermelha?
_Por que importa: Configura o parâmetro automático de conversão de atrasos em faltas de pontualidade (`RN-15.2`)._
> 

### [Q-C13-07] Durante quanto tempo uma participação disciplinar de advertência fica registada no processo individual do aluno antes de prescrever ou ser cancelada por bom comportamento?
_Por que importa: Parametriza o prazo de retenção e expiração de registos disciplinares no módulo `C13` (`RN-15.8`)._
> 

---

## 2. 13.ª Classe, Projecto Tecnológico, Estágios e Conclusão de Curso (Coordenadores de Curso)

### [Q-030 / Q-LEG-07] Qual é a distinção prática e regulamentar no IPCAG entre a disciplina de "Projecto Tecnológico" e a "Prova de Aptidão Profissional (PAP)"? Como é constituído o júri de defesa (inclui peritos externos à escola)?
_Por que importa: Configura o fluxo de registo de temas, atribuição de orientadores, convocação de júris e publicação de pautas de defesa (`RN-18.4`)._
> 

### [Q-LEG-07] Qual é a fórmula exata aplicada para apuramento da Média Final de Curso (MFC)? Quais os pesos relativos atribuídos à Média dos Cursos (10ª–12ª), Estágio Curricular e Defesa da PAP?
_Por que importa: Parametriza o algoritmo de cálculo de aproveitamento final no módulo de avaliação (`C08`), validando a proposta provisória da `DEC-009` antes da entrega E4._
> 

### [Q-C16-08] Se um aluno for aprovado em todas as disciplinas curriculares até à 12.ª classe mas reprovar na defesa da PAP ou no Estágio da 13.ª classe, qual é o regime de reinscrição no ano seguinte: repete com matrícula plena e pagamento de propinas normais ou inscreve-se unicamente para nova defesa/revisão de projeto?
_Por que importa: Parametriza a modalidade de inscrição e cobrança financeira para a 13.ª classe pendente (`DEC-024` e `RN-18.4.2`)._
> 

### [MIG-Q29] Onde e em que suporte documental estão atualmente registadas as notas de estágio, temas de projeto e composições de júri dos alunos da 13.ª Classe que estão a concluir os seus cursos?
_Por que importa: Mapeia as fontes de recolha de dados para migração dos finalistas da coorte atual (`C17`)._
> 
