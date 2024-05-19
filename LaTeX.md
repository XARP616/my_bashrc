# LaTeX section
For handy things in LaTeX

## Images
### Add border to an image
[Read here](https://tex.stackexchange.com/questions/20640/how-to-add-border-for-an-image)

### Crop an image
[Read here](https://tex.stackexchange.com/questions/57418/crop-an-inserted-image)

## Tables

### Color a single cell
[Read here](https://tex.stackexchange.com/questions/50349/color-only-a-cell-of-a-table)

## Text format

### Whole paragraph identation
```latex
\vspace{0.6cm}
\hfill\begin{minipage}{\dimexpr\textwidth-2cm}

  Hello!

\xdef\tpd{1cm}
\end{minipage}
\vspace{0.6cm}
```

[Read here](https://tex.stackexchange.com/questions/35933/indenting-a-whole-paragraph)


## Math

### Create conditional equations

```
\documentclass{article}
\usepackage{amsmath}

\begin{document}
\[
    f(x)= 
\begin{cases}
    \frac{x^2-x}{x},& \text{if } x\geq 1\\
    0,              & \text{otherwise}
\end{cases}
\]
\end{document}
```
[Read here](https://tex.stackexchange.com/questions/47170/how-to-write-conditional-equations-with-one-sided-curly-brackets)

### Equation generator
[Visit here](https://latex.codecogs.com/eqneditor/editor.php)

### XOR symbol in math
`$\xor$`
[Read here](https://tex.stackexchange.com/questions/3936/logic-operators-in-latex-xor#answer-3937)

### Text striketrough (crossed)
[Read here](https://tex.stackexchange.com/questions/23711/strikethrough-text)

# Code

## Copy-pasteable listings (no spaces)
```
\lstset{basicstyle = \ttfamily,columns=fullflexible}
```
[Read here](https://tex.stackexchange.com/questions/119218/how-to-copy-paste-from-lstlistings#answer-119223)

## Assembly language listings
```
\begin{lstlisting}[language={[x86masm]Assembler}]
push eax
\end{lstlisting}
```
[Read here](https://tex.stackexchange.com/questions/557806/listings-package-language-assembler-could-not-be-loaded#answer-557822)

## Miscellaneous
### Opening and closing quotation marks
[Read here](https://tex.stackexchange.com/questions/52351/quote-marks-are-backwards-using-texmaker-pdflatex)

### References to chapters/sections by name and number
[Read here](https://tex.stackexchange.com/questions/66896/ref-chapter-name-in-latex)

### Prevent line break
[Read here](https://stackoverflow.com/questions/1012799/latex-prevent-line-break-in-a-span-of-text)

### Different column width
[Read here](https://tex.stackexchange.com/questions/89721/different-column-widths-using-multicol)

