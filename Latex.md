This note deals with usage of common latex commands needed for data science in github.  

Github uses **MathJax** to render mathematical expressions.[link](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)  

General Tips:
- `\\` gives newline.
- `&` helps in alignment horizontally.
- Better to put an empty line before and after `$$ $$` block.
- Avoid using characters like `*` to denote something in mathematical expression if possible. Use alternatives list `\ast`.

Equations:
```latex

$$\begin{aligned}
LHS &= RHS \\
LHS2 &= RHS2
\end{aligned}$$

```

$$\begin{aligned}
LHS &= RHS \\
LHS2 &= RHS2
\end{aligned}$$


Matrices:
```latex

$$\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
_{3 \times 3}$$

```
$$\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
_{3 \times 3}$$

