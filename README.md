# Min-Sum декодер LDPC

## Теория

$H$ — проверочная матрица кода

$y$ — вектор для декодирования

$L(y) = \big(f(y_1), f(y_2), \dots, f(y_n)\big)$

### Алгоритм

0. $M_{+} = 0$, $S = L(y)$,
1. $M^{-}_{ji} = H_{ji} (S_i - M^{+}_{ji})$,
2. $M^{+}_{ji} = H_{ji} \min\limits_{k \neq i, H_{jk} = 1} |M^{-}_{jk}| \prod\limits_{k \neq i, H_{jk} = 1} \sgn M_{jk}$,
3. $S_i = L_i(y) + \sum\limits_{j} M^{+}_{ji}$,
4. if $S_i = 0$ - decoded, else - `goto` (1).
