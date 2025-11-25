## Markdown and Symbolic Logic: A Beginner’s Guide

David W. Agler

# 1. What is this guide, what is Markdown, and why would I ever want to use Markdown to do logic?

This is a guide to learning how to use Markdown in order to do some basic logic. The next step up from doing logic with pencil and paper is with a text editor or word processor of some variety. One of the best options is LATEX but this is often intimating for new students. MSWord is another option but (i) it cannot be easily rendered to HTML / XHTML, which means you can publish your work to the web and (ii) when manipulating logical symbols, MSWord often goes bonkers.

Markdown is an excellent alternative with a number of additional, non-logical possibilities (see this article from [LifeHacker](http://lifehacker.com/5943320/what-is-markdown-and-why-is-it-better-for-my-to-do-lists-and-notes) for more on Markdown) But, what is Markdown? Here is the definition of Markdown from John Gruber, Markdown’s creator:

> **Markdown** is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).

In other words, its a tool that allows you to take plain text and turn it into readable documents, e.g. HTML or PDF.

To use Markdown, it will be helpful to have a Markdown editor. There are a number of free editors available: [Dingus](http://daringfireball.net/projects/markdown/dingus) (web),[MarkdownPad](http://markdownpad.com/) (Windows), [Mou](http://mouapp.com/) (Mac), [LightPaper](http://clockworkengine.com/lightpaper-mac/) (Mac & Android app), [Dillinger] (web), and [Markable](http://markable.in/) (web). Ideally, what we want a free, cross-platform Markdown editor that comes packaged with the ability to input mathematical symbols, has support for tables, and allows for exporting as PDF.

For this guide, I’m going to use [StackEdit](https://stackedit.io/). Stackedit can be obtained either through their wesite or as extension through Google Drive.

As a side note, StackEdit had a bug when trying to publish formulas to Firefox and Explorer. If you plan on using StackEdit to publish to the web, you will want to fix the bug either by replacing:

```
<script type="text/javascript" src="https://stackedit.io/libs/MathJax/MathJax.js?config=TeX-AMS_HTML"></script>
with
```

in the output HTML file with:

```
<script type="text/javascript"
  src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
```

But, there are other, perhaps more secure options, available, e.g. saving the MathJax.js onto your server, see [MathJax: Getting Started](http://docs.mathjax.org/en/latest/start.html).

# 2. Symbols for Logic

If you are new to logic, you should know that logic involves a number of “special symbols”. To input these symbols using Markdown, you will need to insert a specific command between two dollar signs, e.g. `$\someCommand$`. Let’s look at one example. In propositional logic, there is what is called the caret, which looks like this: ∧

To get the caret to display, you will need to type

`$\wedge$`

Here are the rest of the symbols you will need:

|||
|---|---|
|**Propositional Logic**||
|¬|`$\neg$`|
|→|`$\rightarrow$`|
|↔|`$\leftrightarrow$`|
|∨|`$\vee$`|
|∧|`$\wedge$`|
|⊢|`$\vdash$`|
|⊣|`$\dashv$`|
|**Predicate Logic**||
|∀|`$\forall$`|
|∃|`$\exists$`|
|∈|`$\in$`|
|⊨|`$\models$`|
|**Modal Logic**||
|□|`$\Box$`|
|◊|`$\Diamond$`|

# 3. How to Create a Truth Table

Learning how to create a table in Markdown is a key skill. Once you learn this, learning how to solve proofs using Markdown will be easy. There are a number of excellent guides on how to create tables using Markdown, e.g. [Table Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables) and [PHP Markdown Extra](http://michelf.ca/projects/php-markdown/extra/).

|Bold Header #1|Bold Header #2|
|---|---|
|CONTENT|CONTENT|
|CONTENT|CONTENT|

In order to make that table, I input the following to Markdown

```
Bold Header #1  | Bold Header #2
----------------|----------------
CONTENT   | CONTENT
CONTENT | CONTENT
```

So, now let’s turn to using Markdown to create truth tables. First, let’s create a rather large table that we can copy and paste

```
|P|Q|R||x|x|x|x|x|x|x|x|x|x|x|x|x|
|-
|1| |||||||||||||||||||
|2| |||||||||||||||||||
|3| |||||||||||||||||||
|4| |||||||||||||||||||
|5| |||||||||||||||||||
|6| |||||||||||||||||||
|7| |||||||||||||||||||
|8| |||||||||||||||||||
```

Next, let’s create three different tables. First, one where we are dealing with a single propositional letter **P**:

```
|P|x|x||x|x|x|x|x|x|x|x|x|x|x|x|x|
|-
|T| |||||||||||||||||||
|F| |||||||||||||||||||
```

Second, a truth table where we are dealing with two propositional letters **P** and **Q**:

```
|P|Q|x||x|x|x|x|x|x|x|x|x|x|x|x|x|
|-
|T|T|||||||||||||||||||
|T|F|||||||||||||||||||
|F|T|||||||||||||||||||
|F|F|||||||||||||||||||
```

Third, a truth table where we have three propositional letters: **P**, **Q**, **R**:

```
|P|Q|R||x|x|x|x|x|x|x|x|x|x|x|x|x|
|-
|T|T|T|| ||||||||||||||||
|T|T|F|| ||||||||||||||||
|T|F|T|| ||||||||||||||||
|T|F|F|| ||||||||||||||||
|F|T|T|| ||||||||||||||||
|F|T|F|| ||||||||||||||||
|F|F|T|| ||||||||||||||||
|F|F|F|| ||||||||||||||||
```

Now let’s consider some examples. Suppose we wanted to use the truth-table test to determine if (P→Q)∨¬P is a tautology. Let’s begin by copying and pasting the table with two propositional letters **P** and **Q**:

```
|P|Q|x||x|x|x|x|x|x|x|x|x|x|x|x|x|
|-
|T|T|||||||||||||||||||
|T|F|||||||||||||||||||
|F|T|||||||||||||||||||
|F|F|||||||||||||||||||
```

Next, let’s input (P→Q)∨¬P into the top row, reserving a separate column for P, →, Q, ∨, ¬, and the rightmost P:

```
|$P$|$Q$||($P$|$\rightarrow$|$Q$)|$\vee$|$\neg$|$P$||
|-
|T|T|||||||||||||||||||
|T|F|||||||||||||||||||
|F|T|||||||||||||||||||
|F|F|||||||||||||||||||
```

This produces the following table:

|P|Q||(P|→|Q)|∨|¬|P||
|---|---|---|---|---|---|---|---|---|---|
|T|T|||||||||
|T|F|||||||||
|F|T|||||||||
|F|F|||||||||

To make things easier, we are going to replace all of the pipes in all of the rows under the formula with the formula itself:

|P|Q||(P|→|Q)|∨|¬|P||
|---|---|---|---|---|---|---|---|---|---|
|T|T||(P|→|Q)|∨|¬|P||
|T|F||(P|→|Q)|∨|¬|P||
|F|T||(P|→|Q)|∨|¬|P||
|F|F||(P|→|Q)|∨|¬|P||

Next, let’s copy and paste the T’s & F’s under **P** and **Q** under every colummn containing **P** and **Q** (hint: hold ALT when using the mouse to vertical select, copy, & paste):

|P|Q||(P|→|Q)|∨|¬|P||
|---|---|---|---|---|---|---|---|---|---|
|T|T||(T|→|T)|∨|¬|T||
|T|F||(T|→|F)|∨|¬|T||
|F|T||(F|→|T)|∨|¬|F||
|F|F||(F|→|F)|∨|¬|F||

Finally, use the truth-table rules for the various operators to fill in the rest of the table:

|P|Q||(P|→|Q)|∨|¬|P||
|---|---|---|---|---|---|---|---|---|---|
|T|T||(T|T|T)|T|F|T||
|T|F||(T|F|F)|F|F|T||
|F|T||(F|T|T)|T|F|F||
|F|F||(F|T|F)|T|F|F||

Finally, we can bold the column containing the main operator of the formula to perspicuously display that the truth-table tests indicates the formula is **not** a tautology.

|P|Q||(P|→|Q)|∨|¬|P||
|---|---|---|---|---|---|---|---|---|---|
|T|T||(T|T|T)|**T**|F|T||
|T|F||(T|F|F)|**F**|F|T||
|F|T||(F|T|T)|**T**|F|F||
|F|F||(F|T|F)|**T**|F|F||

## 3.1. Aligning th econtents of your table (optional)

You can control the alignment of tables by using a colon `:` after the separator tab. Adding the colon to the right aligns to the right:

|Bold Header #1|Bold Header #2|
|---|---|
|CONTENT|CONTENT|
|CONTENT|CONTENT|

```
Bold Header #1  | Bold Header #2
-----------:|-----------:
CONTENT     | CONTENT
CONTENT     | CONTENT
```

Adding it to the left aligns to the left.

|Bold Header #1|Bold Header #2|
|---|---|
|CONTENT|CONTENT|
|CONTENT|CONTENT|

```
Bold Header #1  | Bold Header #2
:-----------|:-----------
CONTENT     | CONTENT
CONTENT     | CONTENT
```

Adding it to the left and right, center aligns:

|Bold Header #1|Bold Header #2|
|---|---|
|CONTENT|CONTENT|
|CONTENT|CONTENT|

```
Adding it to the left and right, center aligns:
Bold Header #1  | Bold Header #2
:-----------:|:-----------:
CONTENT      | CONTENT
CONTENT      | CONTENT
```

# 4. How to Create a Truth Tree

I’ve experimented with different methods of creating truth trees here: [Symbolic Logic and LATEX](http://davidagler.com/projects/LatexAndSymLogic_AnIntroduction.pdf). While I think you can use this method to create nice looking trees, I don’t find the method terribly intuitive or useful for doing trees on the fly. If you have a better way of creating trees, I’d love to hear from you.

# 5. How to Create a Fitch-Style Proof

In creating Fitch-style proofs using Markdown, we will start by creating a table without a header. To do this, we simply leave the first row of the table blank:

``````
|||||||||
|-
|Row 1| x | y | z
|Row 2| x | y | z
```

Notice that row 1 is not bolded:

||||||||
|---|---|---|---|---|---|---|
|Row 1|x|y|z||||
|Row 2|x|y|z||||

Next, let’s create a table five rows long.

```
|   | | | | | | | |
|-
|1 | | | | | | |
|2 | | | | | | |
|3 | | | | | | |
|4 | | | | | | |
|5 | | | | | | |
```

Reserve the cells to the immediate right of the numbers for formula in the main line of the proof(e.g. premises) and the rightmost cells for the justification of various lines in the proof:

|||||||||
|---|---|---|---|---|---|---|---|
|1|Formula||||||Justifications|
|2|in the||||||go|
|3|main part||||||in|
|4|of the proof||||||the far|
|5|go in the left||||||right|

```
|    |      | | | | | | | |
|-
|1 |          | | | | | | 
|2 |          | | | | | | 
|3 |          | | | | | | 
|4 |          | | | | | | 
|5 |          | | | | | | 
```

With this general template in place, let’s look at how to prove the following valid argument / sequent:

> P→Q,(P∧S)∧R⊢Q

Begin by copying the formula and pasting it in the leftmost cell after the numbers:

```
|    |      | | | | | | | |
|-
|1 | $P\rightarrow Q$            | | | | | | $P$
|2 | $(P\wedge S)\wedge R$       | | | | | | $P$
|3 |                             | | | | | | 
|4 |                             | | | | | | 
|5 |                             | | | | | | 
```

Next, since this proof does not require any assumptions, it can be solved staying in the “main line” of the proof:

```
|    |      | | | | | | | |
|-
|1 | $P\rightarrow Q$             | | | | | | $P$
|2 | $(P\wedge S)\wedge R$        | | | | | | $P$
|3 | $P\wedge S$                  | | | | | | 2$\wedge E$
|4 | $P$                          | | | | | | 3$\wedge E$
|5 | $Q$                          | | | | | | 1,4$\rightarrow E$
```

which gives us the following:

|||||||||
|---|---|---|---|---|---|---|---|
|1|P→Q||||||P|
|2|(P∧S)∧R||||||P|
|3|P∧S||||||2∧E|
|4|Pspan>||||||3∧E|
|5|Q||||||1,4 →E|

For proofs that require assumptions (subproofs), only two modifications are required. To indent the subproof, we simply move the formula that are a part of the subproof one cell to the left. Second, to further indicate the presence of a subproof, we make use of ‘∣’ which will create a descending line ∣ in the cell.

For example, consider a proof of the following argument:

> P∨Q,P→R,Q→R⊢R

||||||||||
|---|---|---|---|---|---|---|---|---|
|1|P∨Q||||||P||
|2|P→R||||||P||
|3|Q→R||||||P||
|4||∣P|||||A||
|5||∣R|||||2,4→E||
||||||||||
|6||∣Q|||||A||
|7||∣R|||||3,6→E||
|8|R||||||1,4-5,6-7 ∨E||

# Useful Guides for Working with Markdown

1. Markdown Editing Help: [http://math.stackexchange.com/editing-help](http://math.stackexchange.com/editing-help)
2. Markdown Code for Symbols: [http://web.ift.uib.no/Teori/KURS/WRK/TeX/symALL.html](http://web.ift.uib.no/Teori/KURS/WRK/TeX/symALL.html)
3. Markdown Guide from the Creator: [http://daringfireball.net/projects/markdown/basics](http://daringfireball.net/projects/markdown/basics)
4. Mathew Mitchell’s Markdown Tutorial: [http://mathewmitchell.net/tutorials/markdown/](http://mathewmitchell.net/tutorials/markdown/)
5. A Plethora of Markdown Materials: [http://designshack.net/articles/html/mastering-markdown-30-resources-apps-and-tutorials-to-get-you-started/](http://designshack.net/articles/html/mastering-markdown-30-resources-apps-and-tutorials-to-get-you-started/)
6. Markdown Syntax Guide: [http://sourceforge.net/p/symboliclogic/wiki/markdown_syntax/](http://sourceforge.net/p/symboliclogic/wiki/markdown_syntax/)
7. MathJax.js: [http://www.mathjax.org/download/](http://www.mathjax.org/download/)