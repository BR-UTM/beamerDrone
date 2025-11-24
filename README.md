# Nome do Tema - Beamer para [Área/Instituição]

Este é um tema Beamer/LaTeX para o projeto BR-UTM.

## Instalação Rápida (3 opções)

### Opção 1: Uso por projeto (mais simples)
1. Baixe `beamerthemeDrone.sty` e `beamerinnerthemeuav.sty`
2. Baixe as imagens de fundo e logo do ITA na pasta `img`
3. Coloque na mesma pasta do seu `.tex`
3. Use: `\usetheme{Drone}`

## Instalação Permanente

### Linux/Mac

```bash
mkdir -p ~/texmf/tex/latex/beamertheme-nome
cd ~/texmf/tex/latex/beamertheme-nome
wget https://github.com/BR-UTM/beamerDrone/raw/main/beamerthemeDrone.sty
wget https://github.com/BR-UTM/beamerDrone/raw/main/beamerinnerthemeuav.sty
wget https://github.com/BR-UTM/beamerDrone/raw/main/img/background.png
wget https://github.com/BR-UTM/beamerDrone/raw/main/img/ITA_logo.png
texhash ~/texmf
```

### Windows (MiKTeX)

1. Localize: C:\Users\SeuUsuario\AppData\Roaming\MiKTeX\<versão>\tex\latex\
2. Crie pasta: beamertheme-nome
3. Copie os arquivos `.sty` e imagens na pasta `img`
4. Abra MiKTeX Console → Tasks → Refresh file name database

### Windows (TeX Live)

Similar ao Linux/Mac, use: C:\Users\SeuUsuario\texmf\tex\latex\

## Uso Básico

```latex
\documentclass{beamer}
\usetheme{Drone}

\title{Seu Título}
\author{Seu Nome}

\begin{document}
\begin{frame}
  \titlepage
\end{frame}
\end{document}
```

### Compilando

```bash
latexmk -xelatex -outdir=out exemplo
```
