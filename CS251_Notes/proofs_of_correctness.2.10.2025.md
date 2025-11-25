## Proofs of Correctness
Program verification is an attempt to ensure a computer program is correct.
A program is correct if it behaves in accordance with its specifications.
This does not mean that the program solves the problem is was intended to solve.
The program's spec may not address aspects of the clients requirement.
Verification involves testing and proof of correctness.

**Testing** seeks to show that particular input values produce acceptable outputs.
**Proof of correctness** uses formal logic to prove that if the input satisfies certain predicates, the execution satisfies other properties as a result. 

### Assertions:
Denote by X an arbitrary collection of input values to some program or program segment P. 
The actions of P transform X into a corresponding group of output values Y.

```
my_function(int x){
	int y;
	y = x + 1;
	return y;
}
//Y = P(x) suggest that the Y values depend of the X values through the actions of program P.
```
A predicate Q(x) describes the conditions that the input values are supposed to satisfy. X is a set of input values. **Q is the precondition**
A predicate R describes the conditons that the output values ar supposed to satisfy.
These conditions will often involve the input values, so R has the for R(x, Y) or R\[X, P(Y)\]

If a program is supposed to find the square root od a positive number, then X consists of one input value x. 
	Q(x) might be "x > 0"
If y is the single output, then y is supposed to be the square root of x. So R(x, y) would be "$y^{2}$ = x". 
Program P is correct if the following implication is valid:
($\forall$x)(x > 0 $\rightarrow$ \[$P(x)^{2} = x$\]) 

The traditional program correctness notation is called Hoare triple:
\{Q\}P\{R\} means: \{precondition\} P \{postcondition\}

Program segment P, Y = P(X)
Q(X) condition that input should satisfy (precondition)
R(X, Y) of R\[X, P(X)\]. R is the postcondition

A program or segment is broken into individual statements $s_{i}$ with predicates inserted between statements as well as at the beginning and end.

These predicates are called assertions because they assert what is supposed to be true about program variables at that point in the program. 
For example:
\{Q\}
	$S_{0}$
\{$R_{1}$}
	$S_{1}$
\{$R_{2}$\}
	$S_{n-1}$
In large systems, program correctness is a massive undertaking, but provides greater assurance of defined behavior.

Translating to logical wffs, preconditions imply the next postcondition. Hoare notation is shorthand for quantified statements from line to line of the program.

## Assignment Rule
If the pre and post condition are appropriately related, the Hoare triple can be inserted at any time in a proof sequence without having to be inferred from from something earlier in the proof sequence. 

Assignment Rule:
1. $S_{i}$ has the form x = e
2. $R_{i}$ is $R_{i + 1}$ with e substituted everywhere in $R_{i + 1}$ for x.

$R_{1}$ - {x -1 > 0}
	$S_{i}$ - x = x -1 
$R_{2}$ - {x > 0}

Work from the bottom up, the post condition is x > 0. 
Substitute e (x-1) into $R_{i}$ everywhere of x. 