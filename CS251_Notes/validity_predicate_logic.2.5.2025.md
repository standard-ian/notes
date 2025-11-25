## Predicate vs. Propositional
A predicate wff is valid if it is true in all possible interpretations
($\forall$x)P(x) $\rightarrow$ ($\exists$x)P(x) is a valid predicate
A $\vee$ $\neg$A is a tautology

|                 | Propositional wffs                                 | Predicate wffs                                   |
| --------------- | -------------------------------------------------- | ------------------------------------------------ |
| Truth values    | True/false - depends on truth of statement letters | True/false/neither (if there is a free variable) |
| Intrinsic truth | Tautology - true for all values                    | Valid wff - true for all interpretations         |
| Methodology     | Truth table to determine tautology                 | No algorithm for validity                        |
It is provable that there is no valid algorithm to determine validity for predicate wffs
## Validity
A predicate wff is valid if every interpretation is a model.
An interpretation that makes a wff true is a **model**
An interpretation that makes it false is called a **countermodel**
A predicate wff is unsatisfiable if every interpretation is a countermodel
Satisfiable if there is at least one interpretation that makes it true

| Propositional wffs | example            | Predicate wffs                                                | example                                                     |
| ------------------ | ------------------ | ------------------------------------------------------------- | ----------------------------------------------------------- |
| Tautology          | A $\vee$ $\neg$A   | Valid wff - true for all interpretations                      | ($\forall$x)P(x)<br>$\rightarrow$<br>($\exists$x)P(x)       |
| Contradiction      | A $\wedge$ $\neg$A | Invalid wff - may be true on some interpretations but not all | ($\exists$x)P(x)<br>$\rightarrow$ <br>($\forall$x)P(x) <br> |
**($\exists$x)P(x) $\rightarrow$ ($\forall$x)P(x)** domain of all cats, P(x) = "x is black"
This will be false. The premise of the implication is true, but the conclusion is false

| Propositional wffs                                               | example            | Predicate wffs                                                     | example                                                |
| ---------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------ | ------------------------------------------------------ |
| Satisfiable - there is some assignment that makes it true        | A $\vee$ B         | Valid wff - some interpretation makes this true                    | ($\exists$x)P(x)<br>$\rightarrow$ <br>($\forall$x)P(x) |
| Unsatisfiable - there is no assignment of T/F that makes it true | A $\wedge$ $\neg$A | Unsatisfiable - there is no interpretation that can make this true | <br>($\exists$x)(P(x)<br>$\wedge$<br>$\neg$P(x)')      |
**($\exists$x)P(x)$\rightarrow$ ($\forall$x)P(x)** domain of all cats, P(x) = "x speaks Spanish" This will be vacuously true! The premise of the implication is false.

**$\forall$(x)P(x) $\rightarrow$($\exists$x)P(x)** - valid because if every object of the domain has a certain property, there exists one that has the property

**($\forall$x)P(x) $\rightarrow$P(a)** - valid since the constant 'a' is in the same range of P(x)

**($\exists$x)P(x) $\rightarrow$($\forall$x)P(x)** - not valid since property P need not be true for all objects in every domain.
If P(x) is "x is even" then there is an integer that is even but not every integer is even. (this is a countermodel)
But this is satisfiable since there is an interpretation that will make it true. Try P(x) = "x $\neq$ x"

**($\forall$x)\[P(x) $\vee$ Q(x)\] $\rightarrow$ ($\forall$x)P(x) $\vee$($\forall$Q(x))** - invalid, while the premise is true, the conclusion is false. While it is true that every integer is either even or odd, it is not true that every integer is even or that every integer is odd - it is a mixture of both.

## Some Valid Conditionals Whose Converses Are Invalid
Converse of "if A then B" is "if B then A"

(a) $\forall$xA(x) $\rightarrow$ $\exists$xA(x) - valid for all interpretations. if for all, then one exists is valid. The converse is not, that conclusion does not logically follow
	converse: $\exists$xA(x) $\rightarrow$  $\forall$xA(x)
	countermodel, the premise of the countermodel does not for sure imply the conclusion
	
(b) $\exists$x(A(x) $\wedge$ B(x)) $\rightarrow$ $\exists$xA(x) $\wedge$ $\exists$xB(x)) - valid for all interpretations. if there exists a domain where both A(x) and B(x) are true, the conclusion is sound. The converse however, the premise does not support the implication.
	converse:  $\exists$xA(x) $\wedge$ $\exists$xB(x)) $\rightarrow$ $\exists$x(A(x) $\wedge$ B(x))
	countermodel: if A(x) = "even" and B(x) = "odd", there is no number that is both even and odd
	
(c)  $\forall$xA(x) $\vee$ $\forall$xB(x) $\rightarrow$ $\forall$x(A(x)$\vee$B(x)) valid if all A(x) and all B(x), all B(x) and A(x). 
	converse: $\forall$x(A(x)$\vee$B(x)) $\rightarrow$ $\forall$xA(x) $\vee$ $\forall$xB(x) 
	countermodel: if **either** A(x) or B(x) is true, this does not imply that all x are either A or B.
(d) $\forall$x(A(x) $\rightarrow$ B(x)) $\rightarrow$ ($\forall$xA(x) $\rightarrow$ $\forall$xB(x)) $\equiv$  $\forall$x($\neg$A(x) $\vee$ B(x)) $\rightarrow$ ($\exists$x$\neg$A(x) $\vee$ $\forall$xB(x)) - valid
	converse:  ($\exists$x$\neg$A(x) $\vee$ $\forall$xB(x)) $\rightarrow$ $\forall$x($\neg$A(x) $\vee$ B(x))
	countermodel: there exists an x such that x is not even, or B(x) is true everywhere, therefor for everything its either not even or its odd which is false

(e) $\exists$x$\forall$yP(x,y) $\rightarrow$ $\forall$y$\exists$Px(x,y) - valid - there exists an x for all y such that something, therefore every y has some x that something. there exists a number, for all other numbers, x > y.
	converse: $\forall$y$\exists$Px(x,y) $\rightarrow$ $\exists$x$\forall$yP(x,y)
	countermodel:  for every y, there exists a number that is larger than it, therefore there exists one number larger than all others. This is obviously false

Some flowers are pink and have thorns. All thorny flowers smell bad. Every flower that smells bad is a weed.

$\exists$x\[P(x) $\wedge$ T(x)\] $\wedge$ $\forall$x\[T(x) $\rightarrow$S(x)\] $\wedge$ $\forall$\[S(x) $\rightarrow$W(x)\]
some pink flowers have thorns but not all
All thorny flowers smell bad, **so some pink flowers (with thorns) smell bad** (some flowers smell bad)
All flowers that smell bad are weeds, **so some pink flowers (the ones that smell bad) are weeds.**

## Proofs and Derivation Rules with Quantifiers
Build from quantifiers, predicates, and logical connectives
Approach:
	1. Strip off quantifiers
	2. Manipulate unquantified wffs
	3. Reinsert quantifiers
### Strip off quantifiers
Universal Instantiation -ui
Existential Instantiation - ei

| From              | Can Derive                                                                       | Name                      | Restrictions on Use                                                                | Motivation                                                                                                      |
| ----------------- | -------------------------------------------------------------------------------- | ------------------------- | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| ($\forall$x) P(x) | P(t) where $\it{t}$ is a variable or constant symbol                             | Universal Instantiation   | if $\it{t}$ is a variable, it must not fall within the scope of a quantifier for t | If P(x) is true for all elements in the domain then it's true for just t (or any constant a in the domain also) |
| ($\exists$x) P(x) | P(a) where $\it{a}$ is a constant symbol not previously used in a proof sequence | Existential Instantiation | Must be the first rule used that introduces $\it{a}$                               | If P(x) is true for some element in the domain, then use constant a to represent that element                   |
### Replace Quantifiers

| From         | Can Derive     | Name                      | Restrictions on Use                                                                                                                                                           | Motivation                                                                                                                                        |
| ------------ | -------------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| P(x)         | $\forall$xP(x) | Universal Generalization  | P(x) has not been deduced from any hypotheses in which x is a free variable nor has P(x) been deduced by Existential Instantiation from any wff in which x is a free variable | If P(x) is true, there is nothing special about the x that makes it true. (x is arbitrary) then it must be true for all elements x in the domain. |
| P(x) or P(a) | $\exists$xP(x) | Existential Generaization | To go from P(a) to $\exists$xP(x), x must not appear in P(a)                                                                                                                  | if P(x) or P(a) is true, then there is some x or a in the domain that makes it true.                                                              |
Example: "Prove all flowers are plants. Sunflower is a flower. Therefore, sunflower is a plant"
($\forall$x)\[F(x) $\rightarrow$P(x)\] $\wedge$ F(a) $\rightarrow$ P(a):
	1. ($\forall$x)\[F(x) $\rightarrow$P(x)\]     hyp
	2. F(a)                       hyp
	3. F(a) $\rightarrow$ P(a)           1, ui
	4. P(a)                       2, 3 mp