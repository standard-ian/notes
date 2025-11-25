## Verbal Arguments:
### Example 1:
Every crocodile is bigger than every alligator. Sam is a crocodile. But there is a snake, and Sam isn't bigger than that snake. Therefore, something is not an alligator.
C(x) x is a croc
A(x) is an alligator
B(x, y) x is bigger than y
s is a constant (Sam)
S(x) x is a snake

($\forall$x)($\forall$y)\[C(x) $\wedge$ A(y) $\rightarrow$ B(x, y)\] $\wedge$ C(s) $\wedge$ ($\exists$x)(S(x) $\wedge$ $\neg$\[B(s,x)\]) $\rightarrow$ ($\exists$x)$\neg$\[A(x)\]
1. ($\forall$x)($\forall$y)\[C(x) $\wedge$ A(y) $\rightarrow$ B(x, y)\]    hyp
2. C(s)                                                  hyp
3. ($\exists$x)(S(x) $\wedge$ $\neg$\[B(s,x)\])                   hyp
4. ($\forall$y)\[C(s) $\wedge$ A(y) $\rightarrow$ B(s, y)\]        1, ui
5. S(a) $\wedge$ $\neg$\[B(s, a)\]                          3, ei
6. (C(s) $\wedge$ A(a)0 $\rightarrow$ B(s, a))             4, ui
7. $\neg$\[B(s, a)\]                                    5, sim
8. $\neg$\[C(s) $\wedge$ A(a)\]                             6,7 mt
9. $\neg$\[C(s)\] $\vee$ $\neg$\[A(a)\]                    9, demorgans
10. $\neg$\[A(a)\]                                     10, ds
11. ($\exists$x)$\neg$\[A(x)\]                             10, eg
### Example 2:
Every ambassador speaks only to diplomats, and some ambassadors speak to someone. Therefore, there is a diplomat.
A(x) x is an ambassador
S(x, y) x speaks to y
D(x) x is a diplomat

($\forall$x)($\forall$y)\[A(x) $\wedge$ S(x, y)) $\rightarrow$ D(y)\] $\wedge$ ($\exists$x)($\exists$y)(A(x) $\wedge$ S(x, y)) $\rightarrow$ ($\exists$x)D(x)
1. ($\forall$x)($\forall$y)\[A(x) $\wedge$ S(x, y)) $\rightarrow$ D(y)\]           hyp
2. ($\exists$x)($\exists$y)(A(x) $\wedge$ S(x, y))                         hyp
3. ($\exists$y)(A(a) $\wedge$ S(a, y))                                2, ei
4. ($\forall$y)((A(a) $\wedge$ S(a, y)) $\rightarrow$ D(y))                1, ui
5. A(a) $\wedge$ S(a, b)                                          3, ei
6. (A(a) $\wedge$ S(a, b)) $\rightarrow$ D(b)                         4, ui
7. D(b)                                                         5,6 mp
8. ($\exists$x)D(x)                                                   7, eg

