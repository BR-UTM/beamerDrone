# Drone - Beamer para Projeto BR-UTM / ITA

Este é um tema Beamer/LaTeX para o projeto BR-UTM do Instituto Técnológico de Aeronáutica.

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
wget https://github.com/BR-UTM/beamerDrone/raw/main/img/background1.png
wget https://github.com/BR-UTM/beamerDrone/raw/main/img/background2.png
wget https://github.com/BR-UTM/beamerDrone/raw/main/ITA_logo.png
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

### Imagem de Fundo

O comando `\setbackground{imagem.png}` pode ser usado para configurar uma imagem de fundo para a apresentação:

```latex
\documentclass[aspectratio=169]{beamer}

\usetheme{Drone}
\setbackground{img/background1.png} % Defina aqui sua imagem de fundo

 . . .
```

### Páginas de transição

O parâmetro `nosectionpage` remove as telas de transição (_que usam o título da seção_).


```latex
\documentclass[aspectratio=169,nosectionpage]{beamer}

\usetheme{Drone}

\title{Seu Título}
\author{Seu Nome}

\begin{document}

\titlepage

\begin{frame}[plain, allowframebreaks]
  \frametitle{Sumário}
  \tableofcontents
\end{frame}

\setcounter{framenumber}{0} % Reinicia a contagem de páginas

\section{Exemplo}

\subsection{Tema Drone}

\begin{frame}{Exemplo de Frame}

    \begin{block}{Exemplo de bloco}
        \begin{itemize}
            \item Exemplo de lista;
            \item Item do exemplo de lista;
        \end{itemize}
    \end{block}

\end{frame}

\section{Outra seção}

\subsection{Mais uma página}


\begin{frame}{Outro exemplo de Frame}

    \begin{block}{Outro exemplo de bloco}
        \begin{itemize}
            \item Outro exemplo de lista;
            \item Item do outro exemplo de lista;
        \end{itemize}
    \end{block}

\end{frame}


\begin{frame}{Última página}

    \begin{itemize}
        \item Final da apresentação
    \end{itemize}
    \label{LastFrame} % Marca este como o último slide a ser contado

\end{frame}

\begin{frame}[plain]
    \closingpage{
        \Large Obrigado! \\
        \medskip
        \Huge Dúvidas? \\
        \bigskip\bigskip\bigskip\bigskip
        \normalsize drone-comp@ita.br \\
        \normalsize https://drone-comp.ita.br
    }
\end{frame}

\end{document}
```


### Compilando

```bash
latexmk -xelatex -outdir=out exemplo
```
