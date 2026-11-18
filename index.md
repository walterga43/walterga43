# $LaTeX{}$: for Dummies

By David O'Regan, Blu Medina, Walter Adams

### What is $LaTeX{}$?

$LaTeX{}$ is like a programming language for writing documents. Instead of clicking buttons, like in Microsoft Word, you type your content along with specific text commands to format it.

**Benefits of $LaTeX{}$**:

- Creates clean equations for complex math that would otherwise be messy--for instance changing A subseteq B to $A \subseteq B$.
- Makes math more understandable as equations are visualized rather than typed out.
- Gives professors an easier time when grading math homework submitted in online documents such as `.md` and `.tex` files.

### With vs. Without $LaTeX{}$

|                      With $LaTeX{}$                      |                      Without $LaTeX{}$                      |
| :------------------------------------------------------: | :---------------------------------------------------------: |
| ![With LaTeX](https://hackmd.io/_uploads/r1ic3i56Ml.png) | ![Without LaTeX](https://hackmd.io/_uploads/Skschjcafg.png) |

### What types of classes can $LaTeX{}$ be used for?

$LaTeX{}$ can be used in a variety of courses, especially those that involve mathematical equations, scientific notation, or technical writing. While it is most commonly associated with mathematics, it is also useful in other fields where clear formatting and organization are important.

Classes that we will be covering in this short quick start + cheat sheet guide are:

> [**Computer Science**](#computer-science-section)
>
> [**Math & Statistics**](#math-section)
>
> [**Physics**](#physics-section)

But $LaTeX{}$ can also be useful in other subjects, such as engineering, chemistry, and economics, or really any subject where documents require specialized notation or formatting.

## Your First Document (.tex)

##### Where to Write $LaTeX{}$

To turn your code into a finished PDF, you need a $LaTeX{}$ editor. We recommend [Overleaf](https://www.overleaf.com), a free online editor that works right in your browser, so there is nothing to install.

Every $LaTeX{}$ document starts with a preamble that tells the editor what kind of document you are making and what packages need to be loaded.

##### Example

```
\documentclass[12pt, letterpaper]{article}
\usepackage{amsmath}
\usepackage{amssymb}

\title{My First LaTeX Document}
\author{Your Name}
\date{\today}

\begin{document}
\maketitle

\section{Introduction}
This is my first paragraph. Inline math looks like $x^2 + y^2 = z^2$. % Inline math

\section{Problem 1}
Display math gets its own line:
\[
  \int_{0}^{1} x^2 \, dx = \frac{1}{3}  % Display math
\]

\end{document}
```

`\documentclass` is used to determine the type of document you are creating. For nearly all homework assignments `{article}` is what you should use.

`\usepackage` loads extra tools. amsmath gives you better equation formatting, and amssymb is needed for symbols like $\mathbb{R}$.

> [!WARNING]
> Forgetting to set a document class or define used packages can cause certain $LaTeX{}$ functions to not be recognized by your .tex file!

`\title`, `\author`, and `\date` only store information. Nothing will show up until you call `\maketitle` inside the document.

`\section{}` creates a numbered heading, which makes it easy to split homework into Problem 1, Problem 2, etc.

##### Inline vs. Display Math

- Inline math goes between single dollar signs, like $x^2$, and stays in the same line as your text.
- Display math goes between \[ and \] and is centered on its own line.
  To show work step by step, use align\* and put & before each = so they line up:

```
\begin{align*}
  2x + 3 &= 7 \\
  2x &= 4 \\
  x &= 2
\end{align*}
```

\begin{align*}
2x + 3 &= 7 \\
2x &= 4 \\
x &= 2
\end{align*}

Quick-Reference Cheat Sheet:

| #   | Symbol                                              | Meaning                         | $LaTeX{}$ code                                                      |
| --- | --------------------------------------------------- | ------------------------------- | ------------------------------------------------------------------- |
| 1   | $\frac{a}{b}$                                       | Fraction                        | `\frac{a}{b}`                                                       |
| 2   | $\sqrt{x}$                                          | Square root                     | `\sqrt{x}`                                                          |
| 3   | $x^{n}$                                             | Superscript (exponent)          | `x^{n}`                                                             |
| 4   | $x_{i}$                                             | Subscript                       | `x_{i}`                                                             |
| 5   | $\sum_{i=1}^{n} a_i$                                | Summation                       | `\sum_{i=1}^{n} a_i`                                                |
| 6   | $\int_{a}^{b} f(x)\,dx$                             | Integral                        | `\int_{a}^{b} f(x)\,dx`                                             |
| 7   | $\infty$                                            | Infinity                        | `\infty`                                                            |
| 8   | $\alpha$ $\beta$ $\theta$ $\lambda$                 | Greek letters                   | `\alpha`, `\beta`, `\theta`, `\lambda`                              |
| 9   | $\leq$ $\geq$ $\neq$ $=$ $\equiv$ $\cong$ $\approx$ | Inequalities                    | `\leq`, `\geq`, `\neq`, `=`, `\equiv`, `\cong`, `\approx`           |
| 10  | $\times$ $\cdot$ $+$ $-$                            | Operations                      | `\times`, `\cdot`, `+`, `-`                                         |
| 11  | $\rightarrow$                                       | Right arrow (implies / maps to) | `\rightarrow` (or `\to`)                                            |
| 12  | $\in$ $\subset$ $\subseteq$                         | Set Theory                      | `\in`, `\subset`, `\subseteq`                                       |
| 13  | $\lim_{x \to 0} f(x)$                               | Limit                           | `\lim_{x \to 0} f(x)`                                               |
| 14  | $\frac{\partial f}{\partial x}$                     | Partial derivative              | `\frac{\partial f}{\partial x}`                                     |
| 15  | $n \choose k$, $\begin{bmatrix}x \\y\end{bmatrix}$  | Binomials and Matrices          | `n \choose k` or `\binom{n}{k}`,`\begin{bmatrix}x \\y\end{bmatrix}` |
| 16  | $\mathbb{R}$, $\mathbb{Z}$, $\mathbb{N}$            | Common Sets                     | `\mathbb{R}`,`\mathbb{Z}`, `\mathbb{N}`                             |

## <a id='computer-science-section'> Computer Science </a>

$LaTeX{}$ is often used within Computer Science for classes such as Discrete Math, Combinatorics, and other proof-based classes. Reading the math for these classes without $LaTeX{}$ can be long and confusing.

You often use inline $LaTeX{}$ in Computer Science to make proofs easier to read.

> [!TIP]
> Inline $LaTeX{}$ is a symbol--such as $x_2$--surrounded by text. It is created by enclosing your desired symbols in dollar signs. **Example:** `$x_2$` $\rightarrow x_2$

| #   | Symbol                                              | Meaning                         | $LaTeX{}$ code                                            |
| --- | --------------------------------------------------- | ------------------------------- | --------------------------------------------------------- |
| 1   | $\frac{a}{b}$                                       | Fraction                        | `\frac{a}{b}`                                             |
| 2   | $x^{n}$                                             | Superscript (exponent)          | `x^{n}`                                                   |
| 3   | $x_{i}$                                             | Subscript                       | `x_{i}`                                                   |
| 4   | $\infty$                                            | Infinity                        | `\infty`                                                  |
| 5   | $\alpha$ $\beta$ $\theta$ $\lambda$                 | Greek letters                   | `\alpha`, `\beta`, `\theta`, `\lambda`                    |
| 6   | $\leq$ $\geq$ $\neq$ $=$ $\equiv$ $\cong$ $\approx$ | Inequalities                    | `\leq`, `\geq`, `\neq`, `=`, `\equiv`, `\cong`, `\approx` |
| 7   | $\times$ $\cdot$ $+$ $-$                            | Operations                      | `\times`, `\cdot`, `+`, `-`                               |
| 8   | $\rightarrow$                                       | Right arrow (implies / maps to) | `\rightarrow` (or `\to`)                                  |
| 9   | $\in$ $\subset$ $\subseteq$                         | Element of                      | `\in`, `\subset`, `\subseteq`                             |
| 10  | $\mathbb{R}$, $\mathbb{Z}$, $\mathbb{N}$            | Common Sets                     | `\mathbb{R}`,`\mathbb{Z}`, `\mathbb{N}`                   |

In Computer Science, $LaTeX{}$ can also be used to denote algorithms, boolean logic, sets and relations, and pseudocode.

> [!TIP]
> Boolean Logic is very prevalent in proofs and truth tables.

**Boolean Logic:**
| Symbol | Meaning | $LaTeX{}$ Code |
| ---------- | -------------------------------------------------------------------------------- | -------------- |
| $\land$ | **Conjunction:** True and only if both inputs are True. | `$\land$` |
| $\lor$ | **Disjunction:** True if at least one input is True. | `$\lor$` |
| $\neg$ | **NOT:** If $A$ is True than $\neg A$ if False and vice versa. | `$\neg$` |
| $\oplus$ | **Exclusive OR:** Only yields True if the inputs are different. | `$\oplus$` |
| $\implies$ |**Implies:** Yields False only when a True premise leads to a False conclusion. | `$\implies$`
| $\iff$ | **Biconditional:** Yields True only when both inputs have the exact same truth value. | `$\iff$` |
| $\top$ | **Tautology:** A statement that is always inherently True under all conditions. | `$\top$` |
| $\bot$ | **Contradiction:** A statement that is always inherently False under all conditions. | `$\bot$` |

### Tables

As mentioned above, boolean logic can be very helpful in truth tables.

To create truth tables, you need to know how to create tables and how to use $LaTeX{}$ with them. Tables only have **two** requirements: the use of `|` and `-` to create the basic structure. Other than that, you may edit them freely!

1. The first row of a table--usually where you find your column headers--is going to look like this in `.md` and `.tex` files:

```
| Column 1 | Column 2 | Column 3 | And so on ... |
| -------- | -------- | -------- | ------------- |
```

to create:

| Column 1 | Column 2 | Column 3 | And so on ... |
| -------- | -------- | -------- | ------------- |

2. The following rows are made of continuing vertical bars to identify the start and end of columns. After the first full dashed line, it is no longer needed to indicate new rows. So, to create extra rows you need to write:

```
| OLD Column 1 | OLD Column 2 | OLD Column 3 | OLD And so on ... |
| ------------ | ------------ | ------------ | ----------------- |
| Row 1 | Row 1 | Row 1 | Row 1 |
| Row 2 | Row 2 | Row 2 | Row 2 | Row 2|

```

to create:
| OLD Column 1 | OLD Column 2 | OLD Column 3 | OLD And so on ... |
| ------------ | ------------ | ------------ | ----------------- |
| Row 1 | Row 1 | Row 1 | Row 1 |
| Row 2 | Row 2 | Row 2 | Row 2 |

> [!NOTE]
> Notice how the column lines are aligned for the column names and dashes but not any of the rows? This is a unique feature of tables where you **do not** have to align any aspect of the tables, and it will format the table in a presentable manner by itself. The alignment of rows is a personal preference, not a requirement. 3. Once you have your table, you can add whatever you'd like in it. This includes images, hyperlinks, inline styles, lists, and more. This section, though, focuses on inline and display $LaTeX{}$.

    - To add inline $LaTeX{}$ you'd follow the normal procedure for inline, just in a table!

| With Text                              | Example                                  | Alone   | Example |
| -------------------------------------- | ---------------------------------------- | ------- | ------- |
| This is AND $\land$ a Boolean Operator | `This is AND $\land$ a Boolean Operator` | $\land$ | `\land` |

Now you can create Truth Tables:
| $P$ | $Q$ | $P \land Q$ | $P \lor Q$ | $P \implies Q$ |
| :---: | :---: | :---: | :---: | :---: |
| T | T | T | T | T |
| T | F | F | T | F |
| F | T | F | T | T |
| F | F | F | F | T |

## <a id='math-section'> Math & Statistics </a>

$LaTeX{}$ is widely used in Mathematics and Statistics courses, particularly in classes like Calculus, Linear Algebra, Probability, and Mathematical Statistics. These subjects often involve complex equations, notations, formulae, and proofs that can be difficult to format using traditional word processors.

> [!TIP]
> $LaTeX{}$ codes can be combined and stacked, allowing you to create complex formulae, for example:
> $y = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}$
> is created by nesting a plus-or-minus `\pm`, a superscript `x^{}`, and a square root `\sqrt{}` within a fraction `\frac{}{}`

General Mathematical Notations:

| #   | Symbol                                              | Meaning                | $LaTeX{}$ code                                            |
| --- | --------------------------------------------------- | ---------------------- | --------------------------------------------------------- |
| 1   | $\frac{a}{b}$                                       | Fraction               | `\frac{a}{b}`                                             |
| 2   | $\sqrt{x}$                                          | Square root            | `\sqrt{x}`                                                |
| 3   | $x^{n}$                                             | Superscript (exponent) | `x^{n}`                                                   |
| 4   | $x_{i}$                                             | Subscript              | `x_{i}`                                                   |
| 5   | $\sum_{i=1}^{n} a_i$                                | Summation              | `\sum_{i=1}^{n} a_i`                                      |
| 6   | $\infty$                                            | Infinity               | `\infty`                                                  |
| 7   | $\alpha$ $\beta$ $\theta$ $\lambda$                 | Greek letters          | `\alpha`, `\beta`, `\theta`, `\lambda`                    |
| 8   | $\leq$ $\geq$ $\neq$ $=$ $\equiv$ $\cong$ $\approx$ | Inequalities           | `\leq`, `\geq`, `\neq`, `=`, `\equiv`, `\cong`, `\approx` |
| 9   | $\times$ $\cdot$ $+$ $-$ $\pm$                      | Operations             | `\times`, `\cdot`, `+`, `-` `\pm`                         |
| 10  | $\in$ $\subset$ $\subseteq$                         | Element of             | `\in`, `\subset`, `\subseteq`                             |
| 11  | $\mathbb{R}$, $\mathbb{Z}$, $\mathbb{N}$            | Common Sets            | `\mathbb{R}`,`\mathbb{Z}`, `\mathbb{N}`                   |

### Calculus

Calculus relies heavily on $LaTeX{}$ because it involves derivatives, integrals, limits, and other expressions that can become difficult to read when written in plain text.

Some common examples include:

| Concept             | Example                         | $LaTeX{}$ Code                  |
| ------------------- | ------------------------------- | ------------------------------- |
| Derivative          | $\frac{dy}{dx}$                 | `\frac{dy}{dx}`                 |
| $2^{nd}$ Derivative | $\frac{d^2y}{dx^2}$             | `\frac{d^2y}{dx^2}`             |
| Partial derivative  | $\frac{\partial f}{\partial x}$ | `\frac{\partial f}{\partial x}` |
| Definite Integral   | $\int_0^b f(x)\,dx$             | `\int_0^b f(x)\,dx`             |
| Limit               | $\lim_{x\to\infty} f(x)$        | `\lim_{x\to\infty} f(x)`        |

> [!TIP]
> When showing your work for a derivative, you can use align\* to organize each step:
>
> ```
> \begin{align*}
> f(x) &= x^2 + 3x \\
> f'(x) &= 2x + 3
> \end{align*}
> ```
>
> $\begin{align*}
> f(x) &= x^2 + 3x \\
> f'(x) &= 2x + 3
> \end{align*}$
>
> This produces aligned equations that make your work easy to follow.

### Linear Algebra

Linear Algebra uses matrices, vectors, and systems of equations. $LaTeX{}$ makes these especially easy to format using environments such as bmatrix and pmatrix.

#### Example:

```
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
```

Produces:

$\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}$

You can also use a `\det(A)` to represent the determinant of a matrix, or `\vec{v}` to represent a vector.

### Probability and Statistics

Probability and Statistics use $LaTeX{}$ to represent distributions, probabilities, expected values, and statistical formulae.

| Concept                 | Example                 | $LaTeX{}$ Code                  |
| ----------------------- | ----------------------- | ------------------------------- |
| Probability             | $P(A)$                  | `P(A)`                          |
| Conditional Probability | $P(A\mid B)$            | `P(A\mid B)`                    |
| Expected Value          | $E[X]$                  | `E[X]`                          |
| Variance                | $\operatorname{Var}(X)$ | `\operatorname{Var}(X)`         |
| Standard Deviation      | $\sigma$                | `\sigma`                        |
| Normal Distribution     | $X\sim N(\mu,\sigma^2)$ | `X\sim N(\mu,\sigma^2)`         |
| Binomials               | $\binom{n}{k}$          | `n \choose k` or `\binom{n}{k}` |

These tools are particularly useful when writing statistical proofs, showing calculations, or presenting probability distributions in homework assignments.

## <a id='physics-section'> Physics </a>

$LaTeX{}$ is used throughout Physics courses such as Mechanics, Electricity & Magnetism, Thermodynamics, and Quantum Mechanics. Physics relies heavily on vectors, derivatives, and Greek letters, which are almost impossible to type cleanly without $LaTeX{}$.

> [!TIP]
> Use `\text{}` to write units so they don't come out italic like variables. **Example:** `$9.8 \, \text{m/s}^2$` $\rightarrow 9.8 \, \text{m/s}^2$

| #   | Symbol                                            | Meaning                         | $LaTeX{}$ code                                    |
| --- | ------------------------------------------------- | ------------------------------- | ------------------------------------------------- |
| 1   | $\vec{v}$                                         | Vector                          | `\vec{v}`                                         |
| 2   | $\hat{x}$                                         | Unit vector                     | `\hat{x}`                                         |
| 3   | $\dot{x}$, $\ddot{x}$                             | Time derivatives                | `\dot{x}`, `\ddot{x}`                             |
| 4   | $\Delta x$                                        | Change in                       | `\Delta x`                                        |
| 5   | $\nabla$                                          | Gradient (del)                  | `\nabla`                                          |
| 6   | $\vec{a} \cdot \vec{b}$, $\vec{a} \times \vec{b}$ | Dot and cross product           | `\vec{a} \cdot \vec{b}`, `\vec{a} \times \vec{b}` |
| 7   | $\hbar$                                           | Reduced Planck constant         | `\hbar`                                           |
| 8   | $\varepsilon_0$, $\mu_0$                          | Electric and magnetic constants | `\varepsilon_0`, `\mu_0`                          |
| 9   | $\omega$ $\Omega$ $\rho$ $\tau$ $\phi$            | More Greek letters              | `\omega`, `\Omega`, `\rho`, `\tau`, `\phi`        |
| 10  | $\propto$                                         | Proportional to                 | `\propto`                                         |
| 11  | $30^\circ$                                        | Degrees                         | `30^\circ`                                        |
| 12  | $\frac{d^2x}{dt^2}$                               | Second derivative               | `\frac{d^2x}{dt^2}`                               |

### Quick Kinematics

Kinematics is a branch of Physics that describes motion, often using displacement, velocity, acceleration, and time. $LaTeX{}$ makes it easy to write these equations clearly with all their exponents and subscripts.

The four basic kinematic equations are:

| #   | Equation                             | $LaTeX{}$ Code                       |
| --- | ------------------------------------ | ------------------------------------ |
| 1   | $v_f = v_i + at$                     | `v_f = v_i + at`                     |
| 2   | $\Delta x = v_i t + \frac{1}{2}at^2$ | `\Delta x = v_i t + \frac{1}{2}at^2` |
| 3   | $v_f^2 = v_i^2 + 2a\Delta x$         | `v_f^2 = v_i^2 + 2a\Delta x`         |
| 4   | $\Delta x = \frac{v_i+v_f}{2}t$      | `\Delta x = \frac{v_i+v_f}{2}t`      |

These equations demonstrate how $LaTeX{}$ can combine subscripts, superscripts, fractions, and Greek letters into readable physics formulae.

## More Information

If you would like to dive deeper into the intricacies of $LaTeX{}$, please visit [the Official $LaTeX{}$ Documentation](https://www.latex-project.org/help/documentation/)!
