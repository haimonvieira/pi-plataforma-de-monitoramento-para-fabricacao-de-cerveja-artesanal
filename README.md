# PI Fatec Registro - Plataforma de Monitoramento para Fabricacao de Cerveja Artesanal

Este repositorio contem os artefatos do Projeto Integrador (PI) da FATEC Registro.

## Sobre o projeto

O projeto tem como objetivo apoiar o registro e o monitoramento das etapas de fabricacao de cerveja artesanal, com foco em organizacao de dados, rastreabilidade e apoio a tomada de decisao.

## Conteudo atual do repositorio

Atualmente, o repositorio esta estruturado principalmente para a producao do artigo academico em LaTeX.

```text
.
|-- README.md
`-- artigo/
    |-- artigo.tex
    |-- referencias.bib
    |-- artigo.pdf
    |-- imgs/
    `-- README.md
```

## Pre-requisitos

Para trabalhar no artigo, voce precisa de:

- Distribuicao LaTeX ([MiKTeX](https://miktex.org/download) ou [TeX Live](https://www.tug.org/texlive/))
- BibTeX

## Como compilar o artigo

No diretorio `artigo/`, execute:

```powershell
pdflatex artigo.tex
bibtex artigo
pdflatex artigo.tex
pdflatex artigo.tex
```

Ou em uma unica linha:

```powershell
pdflatex artigo.tex; bibtex artigo; pdflatex artigo.tex; pdflatex artigo.tex
```

## Entrega academica

Este repositorio e parte das atividades do Projeto Integrador da FATEC Registro.

Se necessario, ajuste este README com:

- nomes dos integrantes
- semestre/turma
- professor orientador
- escopo final da plataforma

## Referencia interna

- Documentacao detalhada do artigo: `artigo/README.md`

Teste