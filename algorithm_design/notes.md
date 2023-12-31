# **算法设计与分析笔记** 
author按：\
这一部笔记，主要记录学习过程中的一些想法，以便后续查看时能回忆起当时的理解，并加深印象。

## $Part1$ &emsp;分治策略
&emsp;&emsp;主方法用来求解递归式，获得一些渐进紧确界：\
&emsp;&emsp;**主定理**&emsp;令 $a\geq 1$ 和 $b > 1$ 是常数， $f(n)$ 是一个函数， $T(n)$ 是定义在非负整数上的递归式
$$T(n)=aT(n/b)+f(n)\tag{1.1}$$

&emsp;&emsp;其中我们将 $n/b$ 解释为 $\lfloor n/b\rfloor$ 或 $\lceil n/b\rceil$ .那么：\
&emsp;&emsp;1.若对于某个常数 $\varepsilon > 0$ 有 $f(n)=O(n^{\log _b a-\varepsilon})$ ，则 $T(n)=\Theta(n^{\log _b a})$ .\
&emsp;&emsp;2.若 $f(n)=\Theta(n^{\log _ ba})$ ，则 $T(n)=(n^{\log _ ba}\lg n)$ .\
&emsp;&emsp;3.若对于某个常数 $\varepsilon > 0$ 有 $f(n)=\Omega(n^{\log _b a+\varepsilon})$ ，且对于某个常数 $c < 1$ 和足够大的 $n$ 有 $af(n/b)\leq cf(n)$ ，则 $T(n)=\Theta(f(n))$ .\

$\boxed{To\ Be\ Continued}$
