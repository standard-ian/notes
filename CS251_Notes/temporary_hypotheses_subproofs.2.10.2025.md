## Temporary hypotheses
A temporary hypothesis can be inserted into a proof sequence.

### Example 1:
Prove the argument \[(P(x)) $\rightarrow$ ($\forall$y)Q(x, y)\] $\rightarrow$ ($\forall$y)\[P(x) $\rightarrow$Q(x, y)\]
1. P(x) $\rightarrow$ ($\forall$y)Q(x, y)     hyp
2. P(x)                           temp. hyp
	1. ($\forall$y)Q(x, y)         1,2 mp
	2. Q(x, y)               3, ui - from ($\forall$y)P(x) derive P(t) or P(a)
3. P(x) $\rightarrow$ Q(x, y)            temp hyp discharged
4. ($\forall$y)\[P(x) $\rightarrow$Q(x, y)\]  5, ug - add the quantifier back if P(x) has not been deduced from                                                a hyp where x is a free variable.

### Example 2:
Prove the argument \[(P(x)) $\rightarrow$ ($\forall$y)Q(x, y)\] $\rightarrow$ ($\forall$y)\[P(x) $\rightarrow$Q(x, y)\]
5. P(x) $\rightarrow$ ($\forall$y)Q(x, y)     hyp
	1. P(x)                   temp. hyp
	2. ($\forall$y)Q(x, y)         1,2 mp
	3. Q(x, y)               3, ui - from ($\forall$y)P(x) derive P(t) or P(a)
6. P(x) $\rightarrow$ Q(x, y)            2-6 CP
7. ($\forall$y)\[P(x) $\rightarrow$Q(x, y)\]  5, ug - add the quantifier back if P(x) has not been deduced from                                                a hyp where x is a free variable.

### Example 3:
$\neg$\[($\exists$x)A(x)\] $\leftrightarrow$ ($\forall$x)$\neg$\[A(x)\]
1. $\neg$\[($\exists$x)A(x)\]     hyp
2. A(x)                temp hyp
	1. ($\exists$x)A(x)  2 eg
3. A(x) $\rightarrow$ ($\exists$x)A(x) temp hyp discharged
4. $\neg$\[A(x)\]           1, 4 mt
5. ($\forall$x)$\neg$\[A(x)\]    5 ug 
### Example 4:
($\forall$x)$\neg$\[A(x)\] $\rightarrow$ $\neg$\[($\exists$x)A(x)\]
1. ($\forall$x)$\neg$\[A(x)\]         hyp
2. ($\exists$x)A(x)              temp hyp
	1. A(a)           2 ei - strip off quantifier
	2. $\neg$\[A(a)\]    1, ui
	3. $\neg$\[($\forall$x)$\neg$\[A(x)\]\]  3,4, inc
3.  ($\exists$x)A(x) $\rightarrow$ $\neg$\[($\forall$x)$\neg$\[A(x)\]\]   temp hyp discharged - use mt to find negation of conc.
4.  $\neg$\[$\neg$\[($\forall$x)$\neg$\[A(x)\]\]\]    1, double negation
5. $\neg$\[($\exists$x)A(x)]             6,7 mt

### Example 5:
Same, but use IP
($\forall$x)$\neg$\[A(x)\] $\rightarrow$ $\neg$\[($\exists$x)A(x)\]
1. ($\forall$x)$\neg$\[A(x)\]         hyp
	1. ($\exists$x)A(x)      temp hyp for  $\neg$\[($\exists$x)A(x)\] using IP
	2. A(a)            2, ei
	3. $\neg$\[A(a)\]     1, ui  - ei must be used first. We can re-use A(a) in this order
	4. false         sub 2,3 contradiction
2. $\neg$\[($\exists$x)A(x)\]      2,5 IP discharged

### Example 6:
Prove ($\forall$x)\[(B(x) $\vee$ C(x)) $\rightarrow$ A(x)\] $\rightarrow$ ($\forall$x)\[B(x) $\rightarrow$ A(x)\]
Can't get B(x) out so temporary proof is useful
1.  ($\forall$x)\[(B(x) $\vee$ C(x)) $\rightarrow$ A(x)\]     hyp
2. (B(x) $\vee$ C(x)) $\rightarrow$ A(x)              1, ui
3. B(x)                                       temp hyp
	1. B(x) $\vee$ C(x)                    3, add
	2. A(x)                              2, 4 mp
4. B(x) $\rightarrow$ A(x)         temp hyp discharged - not quantifying over free var or prev use of ei
5. ($\forall$)\[B(x) $\rightarrow$ A(x)\]                6, ug

### Basic Equivalences 
1. $\neg$\[$\forall$x W\] $\equiv$ $\exists$x$\neg$W and $\neg$\[$\exists$xW\] $\equiv$ $\forall$x$\neg$W
2. $\forall$x$\forall$yW $\equiv$ $\forall$y$\forall$xW  and $\exists$x$\exists$yW $\equiv$ $\exists$y$\exists$xW
3. $\exists$(A(x) $\vee$ B(x)) $\equiv$ $\forall$xA(x) $\rightarrow$ $\exists$xB(x)
4. $\exists$x(A(x)) $\vee$ B(x)) $\equiv$ $\exists$xA(x) $\vee$ $\exists$xB(x)
5. $\forall$x(A(x) $\wedge$ B(x)) $\equiv$ $\forall$xA(x) $\wedge$ $\forall$xB(x)
6. Renaming variables - if y does not occur in W(x), then:
	$\exists$xW(x) $\equiv$ $\exists$yW(y) and $\forall$xW(x) $\equiv$ $\forall$yW(y)
7. If x does not occur free in some wff C, then:
	(a)  $\forall$xC $\equiv$ C and $\exists$xC $\equiv$ C
	(b)  $\forall$x(C $\vee$ A(x)) $\equiv$ C $\vee$ $\forall$xA(x) and $\exists$x(C $\vee$ A(x)) $\equiv$ C $\vee$ $\exists$A(x)
	(c)   $\forall$x(C $\wedge$ A(x)) $\equiv$ C  $\wedge$ $\forall$xA(x) and $\exists$x(C  $\wedge$ A(x)) $\equiv$ C  $\wedge$ $\exists$A(x)
	(d)   $\forall$x(C $\rightarrow$ A(x)) $\equiv$ C  $\rightarrow$ $\forall$xA(x) and $\exists$x(C   $\rightarrow$ A(x)) $\equiv$ C  $\rightarrow$ $\exists$A(x)
	(e)  $\forall$x(A(x) $\rightarrow$ C) $\equiv$ $\exists$xA(x) $\rightarrow$ C and  $\exists$x(A(x) $\rightarrow$ C) $\equiv$ $\forall$xA(x) $\rightarrow$ C  - be careful w/ this
