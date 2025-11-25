
Proving Verbal Arguments:

Example:
    Russia was a superpower, and either France was strong or Napoleon made an error. Napoleon did not make an error, but if thea army did not fail, then France was strong. So the army failed and Russia was a superior power.

    A: Russia was a superpower
    B: France was strong
    C: Napoleon made an error
    D: The army failed.

    (A ^ (B v C) ^ C' ^ (D' -> B)) -> (D ^ A)

    1. A ^ (B' v C) hyp
    2. C'           hyp
    3. D' -> B      hyp
    4. A            1, simp
    5. B' v C       1, simp
    6. C v B'       5, comm
    7. B'           2,6 ds
    8. B -> (D')'   3, cont
    9. (D')'        7,8 mp
    10. D           9, dn
    11. D ^ A       10,4 con


Example:
    If a program is efficient, it executed quickly. Either the program is efficient, or it has a bug. However, the program does not execute quickly. Therefore, it has a bug.

    (E -> Q. ^ E v B ^ E') -> B

    1. E -> Q   hyp
    2. E v B    hyp
    3. Q'       hyp
    4. E'       1,3 mt
    5. B        2,4 ds

Example:
    The crop is good, but there is not a enought water. If there is a lot of rain or not a lot of sun, then there is enough water. Therefore, the crop is good and there is a lot of sun.

    C ^ W' ^ R v S' -> W' -> (C ^ S)

    1. C ^ W'           hyp
    2. (R v S') -> W    hyp
    3. C                1, simp
    4. W'               1, simp
    5. (R v S')'        2,4 mt
    6. R' ^ S''         5 Demorgans
    7. S''              6 simp
    8. S                7 dn
    9. C ^ S            3,8 con


Review - Terms:
    Proof - valid argument to establish truth of a mathematical statment
    Argument - a sequence of statements that end with a conclusion
    Valid - the conclusion or final statement of the argument must follow the truth of proceeding statements or premis od the argument.
    Agrument is valid if and only if it is impossible for all the premise to be true and the conclusion to be false.
    Rules of inference - use them to deduce new statements from the statements that we already have.


Proof techniques - CP and IP
    CP (Condition Proof) - if the proof takes the form of asserting a conditional, and proving the antecedent - A of  the conditional necessarily leads to the consequent, B.
        The goal of the conditional proof is to show that if A were true, the desired conclusion follows. if A == T, A -> B is also true.
        From hyp P, derive Q, then conclude P -> Q.

        If a proof or derivation from a premise/hyp A to a conclusion B does not contain any use of CP or IP, then we can apply CP for tautology A -> B.

        Example:
            ((A v B) -> (C ^ D)) ^ A ^ (C -> E) -> (D ^ E)
            1. (A v B) -> (C ^ D)   hyp
            2. A                    hyp
            3. C -> E               hyp
            4. A v B                2, add
            5. C ^ D                1,4 simp
            6. C                    5, simp
            7. E                    3,6 simp
            8. D                    5 simp
            9. D ^ E                7,8 con
                QED                 1-9, CP

        Subproofs - A proof that's a part of another proof
        Always starts with a new premise and ends by applying a CP or IP to derive
        When this happens, the premise is discharged and we cannot come bacl

        Example:
            Prove (A v B) -> (B' -> A)
            1. A v B        hyp
                                            ----
            2.      B'      hyp [for B' -> A]   |___subproof
            3.      A       1,2 ds              |
                                            ----
            4. B' -> A      2,3 CP
                QED         1,4 CP

            Could also just move B' over with deduction ( (A v B ^ B') -> A)

        Example:
            Prove (A v B -> C) -> ((A -> C) ^ (B -> C))
            1. A v B -> C       hyp

            2.      A           hyp [for A -> C]
            3.      A v B       2 add
            4.      C           1,3 imp
            5. A -> C           2-4 CP

            6.      B           hyp [for B -> C]
            7.      A v B       6, add
            8.      C           1,7 imp
            9. B -> C           6-8 CP

            10. (A -> C) ^ (B -> C) 5,9 con
                QED             1,5, 9-10 CP



    IP (Indirect Proof) - form of prood that established the validity of a truth by first assuming that the opposite proposition is true, and then shows that such an assumption leads to a contradiction.
        Works because ta statement cannot be both true and false. (i.e. Q and Q' cannot be true.)
        inc or inconsistency rule
        From hyp P', derive False, then conclude P. If P is assumed false, P' is true. Show that if P' is true, it implies Q and Q', which is impossible
        So, the assumption that P == false (P') is wrong, and P == true.

        If a proof of a derivation from a premise A' to the conclusion False, then we could apply CP to get A - > False
        But we also know that A == A' -> False. So the result is A.

        Subproofs are were IP is useful.

        Example:
            Prove ((A -> B) ^ (A v B)) -> B
            1. A -> B       hyp
            2. A v B        hyp
            3.      B'      hyp [for B]                 //Assume B' is true from B, then try to find contradiction
            4.      A       2,3 ds
            5.      B       1,4 mp                      //We now have B and B', a contradiction
            6.      False   3,5 contra/inconsistency    //line 3 and 5 cannot be true.
            7.B             3-6 IP
                QED         1-2, 7 CP                   //This is stylistic, not required

        Example:
            Prove (A ^ A')'
            1. ((A ^ A')')'     hyp [for (A ^ A')']     //assume original statment is false
            2. A ^ A'           1 dn
            3. A                2 simp
            4. A'               2 simp                  //contradiction
            5. False            3,4 contra/inc
                QED             1-5 IP                  //could also have used Demorgans

            Example:
                Prove (A v B) -> (B' -> A)
                1. B' -> A          hyp

                2.      A v B       hyp [for A v B]

                3.          B'      hyp [for B]     //nested IP proof
                4.          A       1,3 mp
                5.          A v B   4 add           //can refer to lines that are furthr out and above
                6.          False   2,5 contra      //found a contradiction

                7.      B           3-6 IP          //so, B
                8.      A v B       7 add
                9.      False       1,8 contra

                10, A v B           2,7-9 IP
                    QED             1,4 CP

                Shorter
                1. B' -> A          hyp

                2.      (A v B)'    hyp [for A v B]
                3.      A' ^ B'     2 Demorgans
                4.      B'          3 simp
                5.      A           1,4 mp
                6.      A v B       4 add
                7.      False       2,6 contra

                8. A v B            2-7 IP
                    QED             1,8 CP

                Example:
                    Prove ((A -> C) ^ (B -> C)) -> ((A v B) -> C)
                    1. A -> C       hyp
                    2. B -> C       hyp
                    3.      A v B   hyp [for (A v B) -> C]
                    4.      C       1,2,3 Cases         //cases rule says if we have (P v Q), (P -> R), and (Q -> R) we have R
                    5. A v B -> C   3-4 CP
                        QED         1-2, 5 CP

Deductive Method Review:
    Example:
        ((A -> C) ^ (B -> C)) -> ((A v B) -> C) == ((A -> C) ^ (B -> C) ^ (A v B)) -> C
        1. A -> C       hyp
        2. B -> C       hyp
        3. A v B        hyp
        4.      C'      hyp [for C]
        5.      A'      1,4 mt
        6.      B'      2,4 mt
        7.      A       3,6 ds
        8.      False   5,7 contra
        9. C            1,8 IP

        Thereby proving the case rule

Normal Forms:
    Literal - either propositional or its negation A and A' for example are literals
    Disjunctive normal - C1 v C2 v ...Cn where each Ci is a conjunction of literals (fundamental conjunction).
    Conjunctive normal - D1 ^ D2 ^ ...Dn where each Di is a disjunction of literals (fundamental disjunction).

    The following are both: A, B', A v B, A ^ B'

    Any wff has a DNF and CNF. For any propositional variable A we have True == A  A' and False == A ^ A'. Both forms are DNF and CNF

    1. remove conditionals ->
    2. move negations in, and
    3. transform into required form

Satisfyable and Unsatisfiable wffs:
    Boolean Logic : exactly the same as propositional logic, with a slightly different notation
    Boolean formula is a wff involving Boolean variables and operations  (AND), (OR), and (NOT)
    A formula is satisfyable if some assignment of false and true to the variables makes the propositon true.

    3CNF - each disjunction contains exactly 3 literals - i.e (A' v B v C) ^ (A v B' v C) ^ (C v B v C')

    Satisfiable - the set of all wffs that have some way to assign values to variables so that each wff is True is a very special set
    SAT = W | W is a satisfiable boolean formula - does it have a satisfying assignment
    3SAT =  W | W is a satisfyable full 3CNF formula

    If a wf has 320 variables, then it has 2^{320} rows in the truth table. yikes!

    P = NP problem. Prove there is no Poly-time method to if a formula is satisfyable, or find a fast method (i.e. prove the absence or the method or that one exists)
    This problem, is what AI is thrown at. Because we cannot directy compute the solutions (i.e. we have no polytime fast method, so we use brute force of Neural Networks)







