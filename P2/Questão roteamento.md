# Questão 2

## Subitem II
Três primeiras iterações de Dijkstra:
iter | $N'$ | $D(t), p(t)$ | $D(v), p(v)$ | $D(w), p(w)$ | $D(x), p(x)$ | $D(y),p(y)$ | $D(z),p(z)$
---|---|---|---|---|---|---
$0$ | $u$ | $2, u$ | $3, u$ | $3, u$ | $\infty$ | $\infty$ | $\infty$
$1$ | $ut$ | $2, u$ | $3, u$ | $3, u$ | $\infty$ | $9, t$ | $\infty$
$2$ | $utv$ | $2, u$ | $3, u$ | $3, u$ | $4, v$ | $9, t$ | $\infty$

## Subitem II

## Primeira iteração
__ | $t$ | $u$ | $v$ | $w$ | $x$ | $y$ | $z$
--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:
$t$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$
$u$ | 2 | 0 | 3 | 3 | $\infty$ | $\infty$ | $\infty$
$v$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$
$w$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$
$x$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$
$y$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$
$z$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | $\infty$

## Segunda iteração
__ | $t$ | $u$ | $v$ | $w$ | $x$ | $y$ | $z$
--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:
$t$ | 0 | 2 | 4 | $\infty$ | $\infty$ | 7 | $\infty$
$u$ | 2 | 0 | 3 | 3 | $\infty$ | $\infty$ | $\infty$
$v$ | 4 | 3 | 0 | 4 | 3 | 8 | $\infty$
$w$ | $\infty$ | 3 | 4 | 0 | 6 | $\infty$ | $\infty$
$x$ | $\infty$ | $\infty$ | 3 | 6 | 0 | 6 | 8
$y$ | 7 | $\infty$ | 8 | $\infty$ | 6 | 0 | 12
$z$ | $\infty$ | $\infty$ | $\infty$ | $\infty$ | 8 | 12 | 0

## Terceira iteração
__ | $t$ | $u$ | $v$ | $w$ | $x$ | $y$ | $z$
--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:
$t$ | 0 | 2 | 4 | 5 | 7 | 7 | 15
$u$ | 2 | 0 | 3 | 3 | 6 | 9 | 14
$v$ | 4 | 3 | 0 | 4 | 3 | 8 | 11
$w$ | 5 | 3 | 4 | 0 | 6 | 12 | 14
$x$ | 7 | 6 | 3 | 6 | 0 | 6 | 8
$y$ | 7 | 9 | 8 | 12 | 6 | 0 | 12
$z$ | 15 | 14 | 11 | 14 | 8 | 12 | 0

SG4 15.
| iter | $N'$ | $A$   | $C$   | $D$      | $E$    | $F$   |
| ---- | ---- | ----- | ----- | -------- | ------ | ----- |
| $0$  | $b$  | $2,b$ | $8,b$ | $\infty$ | $10,b$ | $4,b$ |
| 1    | $ba$   | - | $2,a$ | $4,a$ | $10,b$   | $4,b$  |       |
| 2    | $bac$   | - | - | $1,c$ | $10,b$   | $4,b$  |       |
| 3    | $bacd$   | - | - | - | $4,d$   | $4,b$  |       |
| 4    | $bacde$   | - | - | - | -   | $2,e$  |       |

| iter | $N'$ | $A$   | $C$   | $D$      | $E$    | $F$   |
| ---- | ---- | ----- | ----- | -------- | ------ | ----- |
| $0$  | $b$  | $2,b$ | $8,b$ | $\infty$ | $10,b$ | $4,b$ |
| 1    | $ba$   | - | $4,a$ | $6,a$ | $10,b$   | $4,b$  |       |
| 2    | $bac$   | - | - | $5,c$ | $10,b$   | $4,b$  |       |
| 3    | $bacd$   | - | - | - | $9,d$   | $4,b$  |       |
| 4    | $bacde$   | - | - | - | -   | $4,b$  |       |

| iter | $N'$    | $A$   | $C$   | $D$      | $E$    | $F$   |
| ---- | ------- | ----- | ----- | -------- | ------ | ----- |
| $0$  | $b$     | $2,b$ | $8,b$ | $\infty$ | $10,b$ | $4,b$ |
| 1    | $ba$    | -     | $4,a$ | $6,a$    | $10,b$ | $4,b$ |
| 2    | $bac$   | -     | -     | $5,c$    | $10,b$ | $4,b$ |
| 3    | $bacf$  | -     | -     | $5,c$    | $6,f$  | -     |
| 4    | $bacfd$ | -     | -     | -        | $6,f$    | -      |
