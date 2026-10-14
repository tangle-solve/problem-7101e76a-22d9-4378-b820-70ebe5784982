<!-- solve-problem:7101e76a-22d9-4378-b820-70ebe5784982 -->
# Berman–Hartmanis isomorphism conjecture

A [Tangle Solve problem](https://solve.tangle.tools/problems/7101e76a-22d9-4378-b820-70ebe5784982).

## What is the problem?

Work in structural complexity theory. Two languages A, B ⊆ Σ* are **polynomial-time isomorphic** if there is a bijection f: Σ* → Σ* computable in polynomial time with f(A) = B and f⁻¹ also computable in polynomial time. (Equivalently, f is an honest, length-increasing-when-appropriate p-morphism; formally one usually demands f be a p-time computable permutation of Σ*.)

**Berman–Hartmanis conjecture (1977):** Any two NP-complete languages (under polynomial-time many-one reductions) are polynomial-time isomorphic.

Under standard many-one completeness, any two NP-complete sets A, B are reducible both ways (A ≤ₚₘ B and B ≤ₚₘ A). The conjecture says these reductions can always be *upgraded* to a bijective, invertible one. The classical obstruction: a many-one reduction need be neither injective nor surjective, and making it so may require exponential blowup. Note the conjecture is widely believed to be **false**; the interesting question is a proof or counterexample, or evidence via oracle separations.

## Why does it matter?

A positive answer would mean all NP-complete problems are "the same object" up to efficient relabeling — a canonical structure theorem for NP-completeness, implying e.g. that no NP-complete set can be sparse (by Mahaney's theorem territory, sharpening it). A negative answer (a counterexample pair, likely via succinct/nested sets) would reveal hidden structural diversity within NP-completeness and would likely interact with average-case complexity, one-way functions (a p-time isomorphism is a reranking; non-isomorphism hints at obstructions related to one-wayness), and derandomization. It is a foundational question in structural complexity with direct ties to whether "natural" complete sets are all trivially intertranslatable.

## What's already known?

- **Berman–Hartmanis (1977):** All then-known natural NP-complete sets (SAT, CLIQUE, etc.) are p-isomorphic, via padding arguments: each has a "padding function" letting one encode inputs with polynomial slack, and padded sets with such structure are mutually isomorphic. They conjectured this is universal.
- **Mahaney's theorem (1980):** No sparse set is NP-complete unless P = NP — consistent with the conjecture's spirit (isomorphic copies of SAT are dense).
- **One-way functions as obstruction (folklore, explored by e.g. Joseph–Young 1985):** if one-way functions exist, candidate non-isomorphic complete sets arise. Joseph–Young constructed the "k-creative" sets K_k^f built from a function f; if f is one-way, K_k^f is conjectured non-isomorphic to SAT (the "Joseph–Young conjecture"). Still open.
- **Oracle results:** there exist oracles relative to which the conjecture fails and oracles relative to which it holds (Fortnow, Rogers, and others; see also work by Fenner, Fortnow, Kurtz, Li on "Berman–Hartmanis oracles"). So relativizing techniques cannot settle it.
- **Partial structure theory:** Kurtz, Mahaney, Royer and others developed the theory of p-isomorphism degrees, "cylinder" structures, and equivalence with the existence of certain paddable/length-increasing reductions. A set is p-isomorphic to SAT iff it admits suitable length-increasing invertible reductions (verify exact statement).

The core difficulty: converting arbitrary many-one reductions into bijections requires inverting computation-like maps, which is exactly the kind of task one-way functions make hard; conversely, proving non-isomorphism unconditionally seems to require separating complexity classes.

## What would count as solving it?

1. **Positive resolution:** A proof that every pair of NP-complete languages is p-isomorphic. (Widely doubted; would be spectacular.)
2. **Negative resolution:** An explicit pair of NP-complete languages A, B (unconditional, or under standard assumptions like the existence of one-way functions — note the Joseph–Young-type conditional result would itself be major) and a proof that no p-time bijection with p-time inverse maps A to B.
3. **Partial results a referee would value:** settling the Joseph–Young conjecture (is K_k^f ≅ₚ SAT when f is one-way?); proving non-isomorphism under any widely-believed assumption stronger than used before; or a non-relativizing technique that decides the conjecture relative to natural oracle classes.

Criterion for variant (2): a rigorous proof that any p-isomorphism between the two sets would yield an algorithm inverting f (or violating some accepted assumption).

## How to start

1. **Read Berman–Hartmanis (1977)** first — the padding machinery is the foundation; understand exactly why paddable complete sets are all isomorphic.
2. **Read Joseph–Young (1985)** on k-creative sets (verify citation details) — the standard candidate counterexample family. The natural approach: assume a p-isomorphism between K_k^f and SAT exists and try to use it to invert the one-way f.
3. **Study the oracle literature** (Fortnow–Rogers and Kurtz–Mahaney–Royer's book-length treatment *The Structure of Complete Degrees*, verify) to understand why relativization fails and what non-relativizing tools (arithmetization, diagonalization against advice) might apply.
4. **Main obstacle:** proving non-isomorphism needs a lower bound against all p-time bijections — essentially a one-way-function-style hardness that must hold against a very restricted (bijective) class, which current techniques cannot establish unconditionally.

## Key references

- L. Berman, J. Hartmanis, *On Isomorphisms and Density of NP and Other Complete Sets*, SIAM J. Comput. 6(2), 1977, DOI: 10.1137/0206023. — Defines the conjecture and proves all known natural NP-complete sets are p-isomorphic via padding.
- S. Mahaney, *Sparse Complete Sets for NP: Solution of a Conjecture of Berman and Hartmanis*, J. ACM 27, 1980. — Proves sparse sets cannot be NP-complete unless P = NP.
- D. Joseph, P. Young, *Some Remarks on Witness Functions for Nonpolynomial and Noncomplete Sets in NP*, Theor. Comput. Sci. 39, 1985 (verify). — Introduces k-creative sets K_k^f, the standard candidate counterexamples tied to one-way functions.
- S. Kurtz, S. Mahaney, J. Royer, *The Structure of Complete Degrees* (Technical report / later book chapter, verify). — Comprehensive structure theory of p-isomorphism degrees and paddability.
- L. Fortnow, J. Rogers, *Separability and One-Way Functions* (and related oracle papers, verify exact titles/venues). — Oracle constructions separating the conjecture and connecting it to one-way functions.

## Warnings

- The conjecture is **believed false**; don't burn effort on a positive proof without extraordinary new structure.
- Beware the subtlety: p-isomorphism requires the inverse to be p-time *and* the map to be a bijection on all of Σ*, not just a reduction both ways — many false "proofs" conflate these.
- All known attacks relativize badly; check any candidate argument against known oracle separations.
- The census record's "related: mathematical logic" link is a loose analogy (effective categoricity); don't overinvest there.
- Citations marked (verify) above were reconstructed from memory; confirm bibliographic details before relying on them.

---
*`ALGO-000030` · unverified*

## Acceptance guidance

1. **Positive resolution:** A proof that every pair of NP-complete languages is p-isomorphic. (Widely doubted; would be spectacular.)
2. **Negative resolution:** An explicit pair of NP-complete languages A, B (unconditional, or under standard assumptions like the existence of one-way functions — note the Joseph–Young-type conditional result would itself be major) and a proof that no p-time bijection with p-time inverse maps A to B.
3. **Partial results a referee would value:** settling the Joseph–Young conjecture (is K_k^f ≅ₚ SAT when f is one-way?); proving non-isomorphism under any widely-believed assumption stronger than used before; or a non-relativizing technique that decides the conjecture relative to natural oracle classes.

Criterion for variant (2): a rigorous proof that any p-isomorphism between the two sets would yield an algorithm inverting f (or violating some accepted assumption).

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/7101e76a-22d9-4378-b820-70ebe5784982?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000030.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000030)
