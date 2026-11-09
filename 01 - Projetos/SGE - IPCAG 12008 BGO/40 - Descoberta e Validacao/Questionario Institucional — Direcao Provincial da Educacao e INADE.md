---
title: "Questionário Institucional — Direção Provincial da Educação e INADE (Fase C — Parametrização e Articulação Externa)"
aliases:
  - "Questionário Direção Provincial da Educação e INADE"
  - "DSC-10-DPE-INADE"
created: 2026-11-09
updated: 2026-11-09
status: ativo
version: "1.0"
doc_id: "DSC-10-DPE-INADE"
project: "[[00 - MOC SGE IPCAG 12008 BGO|SGE - IPCAG 12008 BGO]]"
tags:
  - sge
  - ipcag-12008
  - questionario
  - descoberta
  - dpe-bengo
  - inade
  - certificacao-nacional
---

# Questionário de Articulação Institucional: Direção Provincial da Educação e INADE

**Finalidade:** Formalizar os canais de articulação, layouts oficiais obrigatórios, modelos de homologação e requisitos de integração com a Plataforma Nacional de Certificação do Ministério da Educação (MED/INADE) e com o Gabinete Provincial da Educação do Bengo (`DPE-Bengo`), de acordo com a `DEC-002`, `DEC-009` e conclusões do Ticket #40 (Ponto de Controlo PC-E4).

**De:** Direção Geral do IPCAG e Equipa de Engenharia de Requisitos do SGE  
**Para:** Gabinete Provincial da Educação do Bengo e Instituto Nacional de Avaliação e Desenvolvimento da Educação (INADE)  
**Como as respostas serão usadas:** As respostas serão utilizadas para calibrar os modelos de impressão oficiais de Certificados e Diplomas (`DOF-01`, `DOF-02`), os livros de termos de conclusão (`DOF-09`) e o formato dos ficheiros de exportação estatística e de homologação externa.

## Contexto

O SGE N.º 12008 / BGO gere o percurso completo de avaliação e conclusão dos alunos dos cursos técnicos do IPCAG. Na emissão de Certificados e Diplomas com valor jurídico nacional, a escola submete as pautas finais e os termos de conclusão à homologação da Direção Provincial da Educação do Bengo e ao registo nos sistemas centrais do Ministério da Educação. Este questionário estabelece os pontos de contacto e especificações técnicas necessárias para essa articulação.

## Pontos de Validação Institucional

---

### [Q-020 / Ticket #40] A Direção Provincial da Educação do Bengo ou o INADE dispõem atualmente de uma plataforma informática centralizada ou portal web para submissão digital de pedidos de emissão de Diplomas e Certificados? Se sim, existe API pública ou protocolo para importação em lote (ex.: XML, CSV ou JSON)?
_Por que importa: O SGE está preparado para gerar Certificados locais com QR Code de autenticação criptográfica imediata e, em simultâneo, exportar lotes de homologação nos formatos que a tutela nacional determinar (`C09`)._
> 

### [Q-021] Qual é o procedimento regulamentar atual e a documentação instrutória exigida pelo Gabinete Provincial da Educação do Bengo para homologar os Diplomas de fim de curso e Termos de Exame dos institutos politécnicos?
_Por que importa: Configura o fluxo de emissão da Guia de Remessa e do Termo Coletivo de Homologação no módulo de certificação escolar (`RN-18.6`)._
> 

### [Q-LEG-14] Existem Decretos Executivos, Circulares Ministeriais ou modelos padronizados do MED que fixem os dizeres obrigatórios, tipo de papel, selo em relevo ou marcas de segurança gráfica dos Certificados de Habilitações e Diplomas do Ensino Médio Técnico?
_Por que importa: Assegura a total conformidade visual e textual dos modelos impressos `DOF-01` e `DOF-02` gerados pelo SGE com as normas nacionais em vigor._
> 

### [Q-LEG-15] Para alunos formados em anos letivos anteriores ao funcionamento do SGE (que solicitam 2.ª via de Certificado ou Declaração com Notas), qual é a diretriz oficial da Direção Provincial relativamente à conferência das pautas históricas em papel arquivadas na escola?
_Por que importa: Valida a `DEC-025`, que estabelece que os documentos anteriores ao SGE são conferidos fisicamente nos livros de arquivo da Secretaria e autenticados digitalmente no SGE mediante emissão de 2.ª via com novo QR Code de segurança._
> 
