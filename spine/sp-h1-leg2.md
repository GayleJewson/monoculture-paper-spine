---
status: DRAFT (K3-scoped) — Lyra, 2026-07-29, for Lyra review before any push to main
section: The SP/H¹ Leg-2 subsection — the sheaf obstruction and what it does (and does not) certify
scope: K3 only. K4 (dim H¹ = 3, correlated orientation flips, off-diagonal harmonic Gram) is IN FLIGHT with Clio; referenced here only as forthcoming.
review-note: >
  This is a conservative first draft. Every nontrivial claim is tagged [proved] /
  [conjecture, obligation: …] / [convergent-structure cite, not transfer]. It is
  deliberately under-committed at the higher-order end. Lyra rules on anything flagged
  ⟦RULE⟧ before this leaves the branch.
---

# Leg 2: the sheaf obstruction $H^1$, and the third-order object it witnesses

## Where this subsection sits

The connective tissue (Leg 1 → Leg 2) has already delivered the motivating
wall: no pairwise statistic can certify that $m \ge 3$ agents fail
independently, because $\bar\rho$, $\varphi$, and $n_{\mathrm{eff}}$ are marginals
over the $\binom{m}{2}$ two-agent sub-problems and the higher-order dependence was
summed away in taking them. This subsection states, K3-scoped, *what object does
carry the certificate the pairwise statistics cannot* — and, just as importantly,
what that object does **not** say. The prime directive of the draft is the second
half of that sentence: the load-bearing risk here is a true statement attached to
the wrong quantity, and $H^1$ is exactly the kind of invariant that invites it.

## The Leg-2 claim, K3-scoped

Let the agent graph on $m$ judges carry a presheaf of local failure sections: to
each low-order face (vertices, edges) we assign the locally observed failure law
on that face, and the sheaf condition asks that these restrict consistently on
overlaps. For $m = 3$ the relevant nerve is the triangle $C_3$ (the hollow cycle)
/ its filled counterpart, and the first Čech cohomology $H^1$ of this presheaf is
the obstruction to gluing the pairwise-consistent local sections into a single
globally consistent joint failure law.

**Claim (Leg 2, K3).** Pairwise co-failure statistics cannot certify global
($m \ge 3$) independence; the first genuine obstruction to certification is a
third-order object, and $H^1$ of the co-failure presheaf on $C_3$ is a computable
invariant that *witnesses* the presence of that obstruction.

- **[proved]** Pairwise independence does not imply mutual independence; there
  exist joint laws on $\{0,1\}^3$ that match every prescribed marginal and every
  pairwise $\theta_{ij}$ yet carry an irreducible three-way dependence. This is
  the coordinate content of C407 and is standard (Bernstein-type constructions).
- **[proved]** The irreducible three-way dependence has an explicit coordinate:
  $\theta_{123}$, the third-order log-linear (Möbius) interaction coefficient — the
  coefficient of $x_1 x_2 x_3$ in
  $\log p(x) = \theta_\varnothing + \sum_i \theta_i x_i + \sum_{i<j}\theta_{ij}x_ix_j + \theta_{123}\,x_1x_2x_3$
  on $\{0,1\}^3$ — equivalently the irreducible triple log-odds ratio, the residual
  that no pairwise fit reproduces. On the C400 triangle-sheaf counterexample this
  residual carried $\approx 3.9\%$ of the joint-failure KL (irreducible mass
  $\approx 0.0057$). $\theta_{123}$ is Möbius-independent of all edge data
  $\theta_{ij}$: it varies while every $\theta_{ij}$ is held fixed.
- **[conjecture, obligation: Clio's graded construction]** That $H^1$ (or a graded
  companion such as an $H^2$-style object) is the *natural cohomological home* of
  $\theta_{123}$. On $C_3$, $\dim H^1 = 1$: there is exactly one obstruction class,
  and — per Clio's K3 conventions memo (thread 1690/1695) — the sign of the
  agreement class $\eta_{\mathrm{agr}}$ is unambiguous, because $\dim H^1 = 1$
  leaves no off-diagonal to pair a sign against. What $H^1$ on $C_3$ is *proved*
  to do is witness the obstruction; the precise coordinate identification of
  $\theta_{123}$ with a cohomological generator is an obligation on Clio's graded
  construction, not discharged here (see "What is NOT claimed").

## The connective-tissue loop (why this is the spine, not an add-on)

The object that justifies Leg 2 is the same object that refuted the earlier C400
factorization bridge, read from the opposite side.

- **[proved]** C400 conjectured that the co-failure log-growth rate factors as a
  sum of $H^1$-indexed pairwise contributions (an additive KL split). It is
  refuted: $\theta_{123}$ is precisely the term an additive pairwise split cannot
  reproduce, and the refutation was confirmed by an opposite-prior blind pair
  (2026-07-27).
- **[proved, as a rhetorical identity]** These are one statement seen twice. The
  bridge asserted the higher-order object *factors* (joint reduces to pairwise);
  Leg 2 asserts it *does not* (there is an irreducible higher-order obstruction).
  If pairwise measures could certify independence, cohomology would be a
  restatement of what we already knew and the bridge would have held. It did not,
  so the obstruction is real and $H^1$ is the object that carries it. The term
  that killed the theorem is the term that makes the leg non-trivial.

## What $H^1$ does and does not say

This is the guard-rail paragraph, and it is stated positively so it cannot be
skimmed past.

- **[proved]** $H^1 \ge 1$ (a nonzero class, holonomy $\ne 1$ around the cycle)
  *witnesses* an obstruction: the pairwise-consistent local sections cannot be
  glued into one globally consistent joint law. This is what Leg 2 is entitled to
  assert.
- **[proved — this is the load-bearing negative]** $H^1 = 0$ is **ambiguous** and
  carries **no** independence certificate. A genuine independence collapses the
  obstruction to zero *by coherence*; a monoculture collapses it to zero *by
  degeneracy* — all sections having fallen onto one, so they trivially glue.
  Vanishing $H^1$ cannot distinguish "coherent" from "collapsed." Therefore Leg 2
  claims only "$H^1 \ge 1$ obstructs / witnesses non-factorizability," and **never**
  "$H^1 = 0 \Rightarrow$ independent." $H^1 = 0$ is silent, not healthy.

The practical consequence for the paper: $H^1$ is used only as a positive
detector of coupling, never as a clean bill of health. Every downstream use — in
particular the Leg-3 weighting prior — must respect this asymmetry.

## Convergent structure from outside AI (parallel, not transfer)

Within one week the same *shape* of obstruction was recorded from other fields.
It is worth citing for the reader who will notice the resemblance — but it must be
weighted as convergent structure, not as external verification of our object.

- **[convergent-structure cite, not transfer]** Sargsyan (arXiv 2607.15629),
  machine-verified in Cubical Agda, exhibits a Specker-triangle configuration in
  which pairwise-consistent local causal data admit no global model, the
  obstruction being a computable $H^1$ class with holonomy $\ne 1$. This is the
  *same cohomological machinery* — Čech $H^1$ of a presheaf of local sections,
  holonomy detecting failure-to-glue — but on a **different base** (measurement
  contexts, not agents) carrying a **different meaning** (contextuality / global
  labelling of *outcomes* in the Abramsky–Brandenburger sense, not statistical
  dependence of *failures*). Crucially, Sargsyan's $H^1$ is over $\mathbb{Z}_2$
  (Boolean observables); ours ($\theta_{123}$) is real-valued log-linear. The
  coefficient ring **and** the base category both differ; there is no functor
  between them. The honest claim is a conceptual parallel in *shape only*. We are
  not entitled to say his $H^1$ *is* our co-failure $H^1$, nor that he verified our
  framework. The gluing-consistency $\to$ failure-independence step is a
  Künneth-epistemic transfer we must argue on its own terms; the analogy does not
  hand it to us.
- **[convergent-structure cite, not transfer]** 2606.01663 ("A Sheaf Framework for
  Strategic Multi-Agent Systems") independently built the same machinery on the
  game-theory side (Nash equilibria $\leftrightarrow$ global sections; $H^1 = 0$ iff
  a pure-strategy equilibrium exists; Künneth splitting the obstruction into
  geometric / epistemic / strategic parts). Their sheaf is a strategic
  best-response sheaf; ours is a shared-brief co-failure sheaf — same schema,
  possibly not the same mechanism. The candidate bridge is their Künneth
  *epistemic* component (co-failure as shared information), but that transfer must
  be argued from primary, not waved. Note that this paper's own $H^1 = 0$ result is
  a *strategic* statement and does **not** license reading $H^1 = 0$ as
  independence in our setting — the ambiguity guard above still binds.

## What is NOT claimed here (stated positively)

These are the guards that deferred this subsection repeatedly. Each is stated as a
positive commitment so that a reader — or a future draft — cannot mistake silence
for permission.

1. **$\theta_{123}$ is not a cup product.** We define $\theta_{123}$ as the
   third-order log-linear (Möbius) coefficient. We do **not** write
   $\theta_{123} = a \cup b$ and do **not** call it a "triple cup product." Two
   independent reasons, both **[proved]**: (A) Möbius-independence — $\theta_{123}$
   varies freely while all edge cocycles $\theta_{ij}$ are frozen, so it cannot be
   a product of edge classes; (B) $H^2(C_3) = 0$ — the filled 2-simplex is
   contractible and the hollow $C_3$ is $S^1$, so the cup map
   $H^1 \times H^1 \to H^2$ is identically zero on this nerve. The tell is arity: a
   cup product is binary in two named 1-cocycles; $\theta_{123}$ carries three
   indices and zero input classes.
2. **The C400 bridge is not used.** No bound in this leg reads
   $\text{log-growth} \ge c \cdot \dim H^1 \cdot f^2$ or any additive-KL-over-$H^1$
   decomposition. That bridge is refuted (pairwise-log-linear-only; broken by
   $\theta_{123}$) and separately confounded by difficulty (under latent difficulty
   $\mathrm{corr}(\dim H^1, \text{failure rate}) \approx +0.93$). $H^1$ enters this
   leg, and the downstream Leg-3 prior, as a **qualitative weighting prior only** —
   a statement of *where to bet* — and enters **no** bound as a defined quantity.
3. **$H^1 = 0$ does not imply independence.** (Restated from the guard-rail
   paragraph, because it is the single most tempting overclaim.) Only $H^1 \ge 1$
   is asserted to carry content.
4. **Sargsyan / 2606.01663 are convergent structure, not shared machinery and not
   verification.** No functor, no "same $H^1$," no "verified our paper."
5. **The cohomological home of $\theta_{123}$ is a conjecture with a stated
   obligation.** ⟦RULE — Lyra: the discharge condition below is my best statement
   of the proof-obligation; confirm it matches what you and Clio agreed before this
   is quoted as the obligation.⟧ *Obligation:* exhibit a graded construction on a
   nerve with $H^2 \ne 0$, together with two named 1-cocycles drawn from **outside**
   the pairwise edge data whose Alexander–Whitney product equals $\theta_{123}$
   per-simplex. Until that is built, "$\theta_{123}$ lives where a cup product would
   live" is a conjecture, not a computation.

## K4 and beyond (forthcoming — not asserted here)

Everything above is K3-scoped, and deliberately so.

- **[conjecture / forthcoming — see directed companion]** On K4, $\dim H^1 = 3$,
  and Clio's memo (thread 1690) shows the K3 degeneracy breaks: a single edge-flip
  flips two of three basis cycles at once (a correlated flip = $\mathrm{diag}(\pm 1)$
  conjugation of the harmonic Gram $G$), so two sign sources that were degenerate on
  K3 — orientation-induced vs pairing-induced — separate and become load-bearing.
  Clio's spectrum-invariance result (thread 1695, **[proved]** on her side):
  $\det G$, $\mathrm{tr}\, G$, the eigenvalues, and the diagonal cycle-norms are
  intrinsic; the off-diagonal $G_{ij}$ are convention-dependent and must be labelled
  as such. The connection between the off-diagonal harmonic Gram and the co-failure
  correlation $\beta_{ij}$ (C410) is the subject of the directed companion and is
  **not** asserted here; Clio is computing the K4 Gram now.
- **[scope note]** In this subsection, "the sign of $\eta_{\mathrm{agr}}$ is
  unambiguous" is scoped to **K3 only**. Do not carry it to K4.

---

## Draft rigor ledger (for review, not for the paper body)

- Leg-2 claim (pairwise cannot certify $m\ge3$ independence) — **[proved]** (C407 /
  Bernstein-type constructions).
- $\theta_{123}$ as the irreducible third-order coordinate — **[proved]**.
- $H^1 \ge 1$ witnesses the obstruction — **[proved]** (holonomy $\ne 1$).
- $H^1 = 0$ is ambiguous / no independence certificate — **[proved]** (degeneracy
  vs coherence, 2606.01663 confirms the ambiguity externally).
- $\theta_{123} \ne$ cup product — **[proved]** (Möbius-independence + $H^2(C_3)=0$).
- Cohomological home of $\theta_{123}$ — **[conjecture, obligation: Clio graded
  construction, discharge condition stated above]**.
- Sargsyan 2607.15629, 2606.01663 — **[convergent-structure cite, not transfer]**.
- C400 bridge — **not used**; $H^1$ enters as qualitative prior only, no bound.
- K4 Gram / $\beta_{ij}$ link — **[forthcoming, directed companion]**; not asserted.
