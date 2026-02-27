# Template de Artigo LaTeX FATEC Registro

Template LaTeX para artigos científicos do curso de Desenvolvimento de Software Multiplataforma (DSM) da FATEC Registro. A estrutura agora é modular e ideal para trabalho em equipe.

## 📋 Características

- **Documento principal (`main.tex`)** como controlador das seções
- **Seções individualizadas** em arquivos dentro de `sections/`
- **Preambulo separado** em `preamble/packages.tex` e `preamble/commands.tex`
- **Pasta dedicada para figuras (`images/`), tabelas (`tables/`) e referências (`references/`)
- **Compatível com latexmk** e fluxo multi-compilação tradicional
- **Organização adequada a repositórios Git e colaboração**

## 📁 Estrutura de Diretórios

```
artigo/
├── main.tex                 # arquivo principal que inclui todo o restante
├── referencias.bib          # bibliografia (preservada no nível superior)
├── preamble/                # pacotes e comandos globais
│   ├── packages.tex
│   └── commands.tex
├── sections/                # cada seção do documento em arquivo separado
│   ├── introducao.tex
│   ├── objetivos.tex
│   ├── fundamentacao.tex
│   ├── estado-da-arte.tex
│   ├── metodologia.tex
│   ├── resultados.tex
│   └── conclusao.tex
├── images/                  # todas as figuras do projeto
│   └── base/                # logos e imagens de template
├── tables/                  # tabelas externas (se desejar)
├── references/              # outros arquivos de bibliografia ou estilos
└── README.md                # este arquivo atualizado
```


## 🚀 Como Usar

### Pré-requisitos

- **LaTeX** instalado (recomendado: [TeX Live](https://www.tug.org/texlive/) ou [MiKTeX](https://miktex.org/))
- **BibTeX** para processar referências bibliográficas
- **Pacotes LaTeX necessários**:
  - `babel` (português)
  - `graphicx` (imagens)
  - `amsmath`, `amsfonts`, `amssymb` (matemática)
  - `fancyhdr` (cabeçalho/rodapé)
  - `tikz` (cabeçalho com logos)
  - `hyperref` (links)
  - `cite`, `booktabs` (tabelas e citações)

A maioria dos pacotes é instalada automaticamente pelo gerenciador de pacotes do LaTeX.

### Compilação

Para compilar o documento corretamente com todas as referências e formatação, execute:

```powershell
pdflatex artigo.tex; bibtex artigo; pdflatex artigo.tex; pdflatex artigo.tex
```

#### Por que 4 comandos?

Este documento usa recursos que exigem múltiplas compilações:

1. **Primeiro `pdflatex`**: Gera o arquivo `.aux` com informações sobre citações e cria marcações para o cabeçalho com logos (TikZ)

2. **`bibtex`**: Processa o arquivo `referencias.bib` e gera o `.bbl` com as referências formatadas

3. **Segundo `pdflatex`**: Inclui as referências no PDF e renderiza o cabeçalho corretamente

4. **Terceiro `pdflatex`**: Resolve todas as referências cruzadas e finaliza o documento

## 📝 Personalização

### Cabeçalho Institucional

O cabeçalho com as logos da FATEC, CPS e Governo de SP usa TikZ com `remember picture, overlay`, que precisa de 2 compilações para posicionar os elementos corretamente.

### Referências Bibliográficas

As referências estão no arquivo [referencias.bib](referencias.bib) e são processadas pelo BibTeX. Edite esse arquivo para adicionar ou modificar referências.

Exemplo de entrada no `referencias.bib`:

```bibtex
@article{exemplo2024,
  author  = {Sobrenome, Nome},
  title   = {Título do Artigo},
  journal = {Nome da Revista},
  year    = {2024},
  volume  = {10},
  pages   = {1-10}
}
```

## 🧹 Limpeza de Arquivos Temporários

Para remover arquivos temporários mantendo a estrutura funcionando:

```powershell
Remove-Item *.blg, *.fdb_latexmk, *.fls, *.out, *.log -ErrorAction SilentlyContinue
```

**Importante**: Mantenha os arquivos `.aux` e `.bbl` para evitar recompilar tudo.
