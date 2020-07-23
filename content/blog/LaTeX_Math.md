---
title: "$\\LaTeX$ Math"
date: 2020-07-23T08:51:30-04:00
slug: "latex-math"
description: "A better way of expressing math language"
keywords: ["LaTeX", "Math", "Computers", "Beauty", "Chemistry", "Science"]
draft: false
tags: ["LaTeX", "Math", "Computers", "Beauty", "Chemistry", "Science"]
math: true
toc: true
esv: false
---

## What in the World is $\LaTeX$?

According to [The $\LaTeX$ Project](https://www.latex-project.org/),
> LaTeX, which is pronounced «Lah-tech» or «Lay-tech» (to rhyme with «blech» or «Bertolt Brecht»), is a document preparation system for high-quality typesetting. It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

What this means in everyday terms, is that this is a way to write documents without worrying about things like font size, margins, paragraph spacing, titles and headings, etc. Instead of concerning themselves with the design of the document, authors can just enter the content. $\LaTeX$ takes care of the rest for them.

Journal articles, books, reports and even slide presentations can be beautifully structured and formatted, and have a consistent look and feel, even across large organizations. Such documents can be easily made to adhere to industry, organizational and disciplinary standards without any effort on the part of the writer.

No more messing around with **Bold** and *Italics* or deciding which typeface to use for the title and headings. No more figuring out how to put in footnotes or how to format the bibliography or how to generate a table of contents or an index. $\LaTeX$ can just generate these structure when you're done typing. And you can use any old text editor; no proprietary software needed.

## What does this have to do with Math?

So. You may have noticed that the word **LaTeX** above looks a little funny. If you're really observant you noticed that the 'Title' of this tab in your browser looks even weirder (as does the title in the list of posts). That's because I'm using $\LaTeX$ to render the word. The [**Markdown**](https://www.markdownguide.org/getting-started/) language I'm using to type this document can interpret it as long as I put a pair of $ around the code. Pretty cool, eh?

The thing is, $\LaTeX$ is not just about typesetting documents. It's also about making beautifully formatted math and science formulas possible in your document. And it's really simple; all you have to do is learn a little about the syntax.

Let's have a look at a common equation used in highschool to analyse quadratics; the quadratic formula. It looks like this. Don't worry if you don't remember what it signifies. It doesn't matter for our purposes.
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$

Now, how did I generate such a nice looking formula so easily, and in a simple web document? Well, since you asked...

`x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}`

That's what I typed in to generate the above equation. I know that looks a bit scary if you're not used to it, but bear with me. I'll explain what you're looking at.

- The backslash `\` is used whenever special symbols are needed.
- `{}` is for grouping things together so they're treated the same.
- `\frac{}{}` is a vertical fraction.
- `\pm` is just the plus/minus symbol.
- `\sqrt` is for the square root symbol.
- `^` is used for an exponent.

and that's about it for this formula. $\LaTeX$ makes it really easy to create very complex formulas and is designed to handle anything that mathematicians and scientists can throw at it.

- Greek letters: `\alpha` becomes $\alpha$. `\Theta` (notice the uppercase **T**) becomes $\Theta$
- Matrices: $\begin{bmatrix}
1 & 2 & 3\\\\ 
4 & 5 & 6\\\\
7 & 8 & 9
\end{bmatrix}$
- Chemistry: $CH_{4(g)} + 2O_{2(g)} \rightarrow CO_{2(g)} + 2H_2O_{(g)}$
- And other fun math-type things: $P_\omega={n_\omega\over 2}\hbar\omega\,{1+R\over 1-v^2}\int\limits_{-1}^{1}dx\,(x-v)|x-v|,$

I don't have any idea what that last one means, but the sky is the limit!

## That's enough fun for one day

So. That's it. $\LaTeX$ is pretty awesome and seems to be showing up in all kinds of places. It's a very efficient way to get nice looking documents and, if that's all you're looking for, very nice formulas.

If you want to know more or you want to play around with this, check out [CodeCogs Online LaTeX Equation Editor](https://latex.codecogs.com/eqneditor/editor.php). It allows you to try out  equations and symbols by clicking on a toolbar and seeing what syntax is available. Hours of fun for the whole family.