#### Boolean Algebra
Propositional logic is boolean algebra.
Boolean algebra is a generalized notation, but it evolved alongside propositional logic.
The main operations are conjunction, disjunction, and negation. 

Prop logic is one of many examples of Boolean Algebra

B, $\vee$, $\wedge$, $\neg$, T, F
Functions directly map to truth tables

#### Examples:
##### 1
F\{T, F\}$^{3}$ $\rightarrow$ {T, F}
f($x_{1}$, $x_{2}$, $x_{3}$) = $x_{1}$ $\cdot$ $\neg$$x_{2}$ + $x_{3}$ = f(0, 1, 0) = 0

| $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{1}$ $\cdot$ $\neg$$x_{2}$ + $x_{3}$ |
| :-----: | :-----: | :-----: | :-------------------------------------: |
|    1    |    1    |    1    |                    1                    |
|    1    |    1    |    0    |                    0                    |
|    1    |    0    |    1    |                    1                    |
|    1    |    0    |    0    |                    1                    |
|    0    |    1    |    1    |                    1                    |
|  ==**0**==  |  ==**1**==  |  ==**0**==  |                  ==**0**==                  |
|    0    |    0    |    1    |                    1                    |
|    0    |    0    |    0    |                    0                    |
#### Idempotent Properties
1. x + (y  $\cdot$  z  )  = (x + y) $\cdot$ (x + z)
2. x + 0 = x
3. x + $\neg$ x = 1
4. x $\cdot$ 1 = x
5. x $\cdot$ $\neg$ x = 0 
6. (x + y) + z = x + (y + z)
7. x $\cdot$ y = y $\cdot$ x
8. (x $\cdot$ y) $\cdot$ z = x $\cdot$ (y $\cdot$ z)
9. x $\cdot$ ( y + z) = (x $\cdot$ y) + (x $\cdot$ z)
10. x + y = y + x


11. x $\cdot$ x = x and x + x = x
	Proof: x $\cdot$ x = x starting with x
		x = x $\cdot$ 1
			= x $\cdot$ (x + $\neg$ x)
			= (x $\cdot$ x) + (x $\cdot$ $\neg$ x)
			= x $\cdot$ x + 0
			= x $\cdot$ x

12. 0 $\cdot$ x = 0 and 1 + x = 1
	Proof: 0 $\cdot$ x = 0
		0 $\cdot$ x = (x $\cdot$ $\neg$ x) $\cdot$ x
			= (x $\cdot$ x) $\cdot$ $\neg$ x
			= x $\cdot$ $\neg$ x 
			= 0
13. x + x $\cdot$ y = x and x $\cdot$ (x + y) = x
	Proof: x + x $\cdot$ y
		= x $\cdot$ 1 + x $\cdot$ y
		=x $\cdot$ (1 + y)
		= x $\cdot$ 1
		= x
14. x $\cdot$ (x + y) = x
	Proof: x $\cdot$ (x + y)
		= x + 0 $\cdot$ x + y
		= x + (0 $\cdot$ y)
		= x + 0
		=x
15. For x an element of a boolean algebra B, the element $\neg$ x is called the complement of x.
	The complement satisfies: 
	x + $\neg$ x = 1 and x $\cdot$ $\neg$ x = 0
	Theorem on the uniqueness of complements:
	
	For any x in a boolean algebra, if an element of $x_{1}$ exists such that:
		x + $x_{1}$ = 1 and 
		x $\cdot$ $x_{1}$ = 0
	then $x_{1} = $\neg$ x 
	
	Show (x + y) + ($\neg$ x $\cdot$ $\neg$ y) = 1
	and (x + y) $\cdot$ ($\neg$ x  $\cdot$ $\neg$ y) = 0 and that proves that ($\neg$ x $\cdot$ $\neg$ y) = $\neg$ (x + y)

#### Hints for Proving Equalities
Start w/ more complicated expressions
Add some form of 0 or multiplying by some form of 1
Remember distributive property of addition
Remember idempotent properties
#### Rules
Boolean Algebra Rules \[B, +, •, , 0, 1\]  
##### Or  
1. x + y = y + x commutative  
2. (x + y) + z = x + (y + z) associative  
3. x + (y • z) = (x + y) • (x + z) distributive  
4. x + 0 = x identity  
5. x + $\neg$ x = 1 complement  
##### And  
6. x • y = y • x commutative  
7. (x • y) • z = x • (y • z) associative  
8. x • (y + z) = (x • y) + (x • z) distributive  
9. x • 1 = x identity  
10. x • $\neg$ x = 0 complement  
##### Derived Rules  
11. x + x = x idempotent  
12. (x • y)’ = x’ + y’ De Morgan’s  
13. (x + y)’ = x’ • y’ De Morgan’s  
14. x’’ = x double negation  
15. x • x = x and x + x = x self-reference  
16. 0 • x = 0 and 1 + x = 1 domination  
17. x + (x • y) = x and x • (x + y) = x absorption

#### Isomorphic
Two elements of a structure are isomorphic if there is a bijection (isomorphism) that maps the elements of one instance onto the elements of elements of the other.

Graph isomorphism:
Used to classify groups of things together, and then can talk about properties of the items that map together.

map all the operators from one structure to another.
i.e.:
f, B $\rightarrow$ b is an isomorphism for \[B, +, $\cdot$, $\neg$, 0, 1] and \[b, \&, \*, '', $\rho$, 1\] 
1. $f$ is a bijection
2. 2. $f$(x + y) = $f$(x) \& $f$(y)
3. $f$(x$\cdot$y) = $f$(x) \* $f$(y)
4. $f$($\neg$x) = (f(x))''
An isomorphism maps by the intuition: "operate and map" = "map and operate"

Similar properties also exist for the algebra of sets and the algebra of propositional wffs. 
##### Theorem on finite boolean algebras:
Let $B$ be any boolean algebra with n elements. Then $n = 2^{m}$ for some $m$ and $B$ is isomorphic to $P(S)$ = ){1, 2, ....., $m$})   (powers set)
