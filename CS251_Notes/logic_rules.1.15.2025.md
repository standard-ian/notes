Equivalences Rules:

    A V B ≡ B V A                           commutative
    A Λ B ≡  B Λ A                          commutative
    (A V B) V C ≡  A V (B V C)              associative
    (A Λ B) Λ C ≡  A Λ (B Λ C)              associative
    A Λ (B V C) ≡ (A Λ B) V (A Λ C)         distributive
    A V (B Λ C) ≡ (A V B) Λ (A V C)         distributive
    (A Λ B)’ ≡ A’ V B’                      De Morgan’s
    (A V B)’ ≡ A’ Λ B’                      De Morgan’s
    A → B ≡ A’ V B                          implication
    A → B ≡ B’ → A’                         contra-position
    A’’ ≡ A                                 double negation
    A Λ True ≡ A                            identity
    A V False ≡ A                           identity
    A V A’ ≡ True                           complement
    A Λ A’ ≡ False                          complement
    A Λ A ≡ A                               self-reference
    A V A ≡ A                               self-reference
    A V True ≡ True                         domination
    A Λ False ≡ False                       domination

Can work in both directions (equivalence).

Inference Rules:

    (R, R → S) → S                          mp
    (R → S, S’) → R’                        mt
    (P V Q, P’) → Q                         ds
    R → (R V S)                             add
    (R, S) → R Λ S                          conjunct
    R Λ S → R, S                            simp
    (P, P’) → Q                             inc

Inference rules allow is to add wffs to a proof sequence.
They cannot work in both directions like Equivalence rules.

Deductive Rule:
    P1 ^ P2 ^ ... Pn -> (R -> Q) can be re-written as:
    (P1 ^ P2 ^ ... Pn ^ R) -> Q

    Gives an additional initial premise.

Example proof of deductive method:
    A -> (B -> C) == A ^ B -> C
    A -> (B -> C) hyp
    A' v (B -> C) imp
    A' v (B' v C) imp
    (A' v B') v C associative
    (A ^ B)' v C Demorgans
    (A ^ B) -> C implication

