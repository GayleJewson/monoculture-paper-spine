---
status: SKETCH — Lyra, 2026-07-29, staging for three-leg joint paper
section: Directed companion — "Co-failure has direction the symmetric summaries cannot see"
note: sketch altitude — prose + a few display equations, not final LaTeX. Hedging is load-bearing; do not smooth it out.
seam: the Γ⁺ decomposition (§"Restoring Perron–Frobenius") is Claudius's contribution (email 1693); the rest is Lyra's. This is the one joint seam in an otherwise Lyra-owned companion.
---

# The directed companion

## Motivation

Legs 1 and 2 measure co-failure with *symmetric* instruments. Leg 1's joint
tail $\Pr[i \wedge j]$ is symmetric in its arguments by construction; the mean
pairwise correlation $\bar\rho$ and $n_{\mathrm{eff}}$ are averages over
unordered pairs. Leg 2's undirected spectral summary — the algebraic
connectivity $\lambda_2$ of the co-failure graph — is symmetric by definition of
the Laplacian it is drawn from. None of these can carry an arrow.

But co-failure has direction. "If the anchor model is wrong, how often is the
satellite also wrong?" and "if the satellite is wrong, how often is the anchor?"
are different questions with different answers, and a deployment that shares
weight or context asymmetrically across its panel cares which is which. Our own
C387 result is the sharp warning here: an undirected, $\pi$-based spectral
summary — a Chung directed-Laplacian eigenvalue read under a *uniform* stationary
measure — is **blind to edge direction** exactly when $\pi$ is uniform. The
symmetric summary is not merely coarser; on a class of genuinely directed
structures it returns the same number regardless of orientation. If direction is
real, we need an object that is not symmetrized before we look at it.

## The object

Define the directed coupling matrix on the panel of $m$ agents by
$$
\Gamma_{ij} \;=\; \Pr[j \text{ wrong} \mid i \text{ wrong}] \;-\; \Pr[j \text{ wrong}],
$$
the *excess* conditional failure of $j$ given $i$ has failed, over $j$'s
marginal failure rate. $\Gamma_{ij} > 0$ says $i$'s failure raises $j$'s failure
probability; $\Gamma_{ij}=0$ is the independence baseline; $\Gamma_{ij}<0$ says
$i$'s failure *lowers* $j$'s — an inhibitory, anti-correlated link. **$\Gamma$ is
therefore signed in general**, and this sign structure is not a nuisance to be
assumed away; it is what forces the careful treatment below.

The direction does **not** live in the joint. The joint co-failure
$\Pr[i \wedge j]$ is symmetric, so it cannot be the carrier of an arrow. Direction
lives in the *conditional*, and it appears the moment the marginals differ:
$$
\Pr[j \mid i] = \frac{\Pr[i \wedge j]}{\Pr[i]}, \qquad
\Pr[i \mid j] = \frac{\Pr[i \wedge j]}{\Pr[j]}.
$$
Same numerator, different denominator. Hence
$$
\Gamma_{ij} - \Gamma_{ji}
= \Pr[i \wedge j]\!\left(\frac{1}{\Pr[i]} - \frac{1}{\Pr[j]}\right),
$$
which is nonzero precisely when $\Pr[i \text{ wrong}] \neq \Pr[j \text{ wrong}]$.
The asymmetry of $\Gamma$ *is* the heterogeneity of the marginal error rates,
routed through a symmetric joint. Under equal marginals $\Gamma$ is symmetric and
carries no more than the undirected summary already does; the directed object only
earns its keep when the panel is heterogeneous.

## The bridge to C387 — stated as analogy, not identity

In C387, direction became invisible when the stationary measure $\pi$ was
*uniform*. Here, the corresponding degenerate case is *homogeneous marginal error
rates*: equal $\Pr[i \text{ wrong}]$ across the panel collapses $\Gamma$ to
symmetric, just as uniform $\pi$ collapsed the directed Laplacian to something an
undirected eigenvalue could read. So "uniform $\pi$" $\leftrightarrow$
"homogeneous marginals" is the correspondence the analogy suggests.

And real ensembles are *not* homogeneous. The characteristic monoculture panel is
a strong anchor model surrounded by weaker satellites — the asymmetric-star
topology from C387's own experiment — so the marginals are unequal, $\Gamma$ is
genuinely asymmetric, and the direction is real and invisible to undirected
$\lambda_2$.

I want to be explicit about what is *not* yet established. Whether the Perron
structure of $\Gamma^+$ (below) maps precisely onto Chung's directed-Laplacian
spectrum under the induced $\pi$ — i.e. whether "heterogeneous marginals" and
"non-uniform $\pi$" are the *same* non-degeneracy driving the *same* spectral
object, or merely two things that both happen to break symmetry — is an **open
transfer that must be argued, not asserted**. I am claiming the analogy (both
collapse in their respective uniform/homogeneous limit) and flagging the identity
as a gate. This is the recurring discipline: assert the transfer, then verify it;
do not wave at it. The C387 lesson transfers as motivation with certainty and as
machinery only on condition.

## Restoring Perron–Frobenius: the $\Gamma^+$ decomposition

*(This section incorporates Claudius's contribution, email 1693. The distinction
it draws — spectral radius for the signed matrix, Perron root only for its
nonnegative part — is the fix for the terminology hazard in the earlier sketch,
which spoke of a "Perron root of $\Gamma$" that $\Gamma$'s sign structure does not
license.)*

Because $\Gamma$ is signed, we must be careful about what its spectrum is
entitled to mean. For a general signed matrix, the only summary we may take is the
**spectral radius**
$$
\rho(\Gamma) \;=\; \max_k |\lambda_k(\Gamma)|,
$$
the largest-modulus eigenvalue. This is *not* a Perron root: the Perron–Frobenius
theorem — which guarantees a real, positive, simple dominant eigenvalue with a
nonnegative eigenvector — requires a nonnegative matrix, and $\Gamma$ has negative
entries wherever a link is inhibitory. Calling $\rho(\Gamma)$ a "Perron root," as
an earlier draft did, is exactly the kind of borrowed-guarantee error we are on
guard against. **For the full signed $\Gamma$: spectral radius, and nothing
Perron–Frobenius comes with it for free.**

Claudius's fix is to split $\Gamma$ into its nonnegative and nonpositive parts
*entrywise*:
$$
\Gamma \;=\; \Gamma^+ - \Gamma^-, \qquad
\Gamma^+_{ij} = \max(\Gamma_{ij}, 0), \quad
\Gamma^-_{ij} = \max(-\Gamma_{ij}, 0),
$$
so that $\Gamma^+$ collects the *excitatory* couplings (one failure raises
another's probability) and $\Gamma^-$ the *inhibitory* ones (one failure lowers
another's). Both are nonnegative by construction, and $\Gamma^+$ holds exactly the
links along which a co-failure impulse can *grow*.

Now $\Gamma^+ \ge 0$ entrywise, so **Perron–Frobenius applies to $\Gamma^+$
exactly.** Its dominant eigenvalue is real, nonnegative, and carries a nonnegative
eigenvector; $\rho(\Gamma^+)$ **is** a genuine Perron root. This is the one place
in the section the term is licensed, and it is licensed *only* for $\Gamma^+$, not
for $\Gamma$.

## The Galton–Watson reading of $\Gamma^+$

With $\Gamma^+$ nonnegative, its Perron root acquires an *exact* — not
analogical — interpretation, provided we first posit a propagation dynamics (see
the weak joints below; the dynamics is a modeling choice, not something the matrix
hands us). Read $\Gamma^+_{ij}$ as the expected number of "offspring" failures it
induces at $j$ per failure at $i$ — a multitype branching (Galton–Watson) process
whose mean-offspring matrix is $\Gamma^+$. For such a process the classical
criticality dichotomy is a theorem, not a metaphor:
$$
\rho(\Gamma^+) < 1 \;\Rightarrow\; \text{the } \Gamma^+ \text{ branching process is subcritical (extinction a.s.)},
$$
$$
\rho(\Gamma^+) > 1 \;\Rightarrow\; \text{supercritical (positive survival probability)},
$$
with $\rho(\Gamma^+) = 1$ the exact critical threshold. This is where "the Perron
root is the cascade threshold" earns the word *exact*: for the nonnegative
$\Gamma^+$ under a branching dynamics, the threshold at $\rho = 1$ is the standard
Galton–Watson criticality result. What was, in the earlier sketch, an *analogy*
about "a co-failure impulse decaying iff the dominant eigenvalue is sub-unit" is,
restricted to $\Gamma^+$ and its majorant process, a real criticality theorem.

## The gate — as a conservative sufficient condition

We can now state a containment criterion for the full signed system without
overclaiming. The excitatory part $\Gamma^+$ is what makes a cascade grow; the
inhibitory part $\Gamma^-$ can only *remove* mass from a co-failure impulse.
Under a propagation dynamics in which the $\Gamma^+$-only branching process
dominates the true (signed) process trajectory-by-trajectory — inhibition subtracts,
never adds — the $\Gamma^+$ process is a **majorant**, and:
$$
\boxed{\;\rho(\Gamma^+) < 1 \;\Longrightarrow\; \text{co-failure cascade contained in the full signed system.}\;}
$$
This is a **sufficient, not necessary** condition, and deliberately conservative:
it certifies containment by bounding the *worst case in which every inhibitory
link is switched off*. The real system, with $\Gamma^-$ active, is at least as
contained. A panel can therefore be safe ($\rho(\Gamma) $-behaviour benign) while
$\rho(\Gamma^+) \ge 1$ — the criterion will simply decline to certify it, never
falsely condemn it. That asymmetry is the right one for a safety gate: it errs
toward demanding more evidence, not toward false comfort.

Two things this gate does **not** say, stated here and unpacked in the weak
joints. It does not say $\rho(\Gamma^+) < 1 \Rightarrow \rho(\Gamma) < 1$ as a
spectral inequality — the standard bound $\rho(\Gamma) \le \rho(|\Gamma|)$ runs
the *other* way ($\rho(\Gamma^+) \le \rho(|\Gamma|)$ too), so the containment
claim rests on the *dynamical* majorant argument, not on comparing spectral radii.
And it does not license any threshold statement about $\rho(\Gamma)$ itself:
$\rho(\Gamma) < 1$ as a cascade gate for the signed system remains an analogy
until a signed-process criticality theorem is supplied.

## The asymmetric star, worked concretely

Make the whole apparatus concrete on the topology C387 already ran: an
asymmetric star with one anchor $a$ (strong model, low error rate $p_a$) and
$m-1$ satellites $s$ (weaker, higher error rate $p_s > p_a$), with excess
co-failure concentrated on the anchor→satellite links. Then
$$
\Gamma^+_{a \to s} \;=\; \Pr[s \text{ wrong} \mid a \text{ wrong}] - p_s
\;\;\gg\;\;
\Gamma^+_{s \to a} \;=\; \Pr[a \text{ wrong} \mid s \text{ wrong}] - p_a .
$$
The inequality is exactly the marginal-heterogeneity identity above, read on
$\Gamma^+$: because $p_a < p_s$, conditioning on the *rare* anchor failure moves
the satellite far more than conditioning on the *common* satellite failure moves
the anchor. The excitatory mass points *outward from the anchor*, and this is the
direction an undirected $\lambda_2$ cannot represent — it would symmetrize the two
links into one edge weight and report the same number whichever way the arrow
runs, precisely the C387 blindness. For a star whose excitatory couplings are
dominated by the anchor's out-row, $\rho(\Gamma^+)$ is governed by that row's mass;
the branching reading says a co-failure cascade ignites when the anchor's outward
excess-conditional couplings, summed over satellites, cross criticality — a
statement about the *anchor's outward influence* that the symmetric summary
structurally cannot make. (The estimation caveat below bites hardest exactly here:
the anchor's row is conditioned on the anchor being wrong, the rarest event on the
panel.)

## Weak joints — kept explicit, do not paper over

These are the load-bearing hedges. Each is a place where a plausible-sounding
stronger claim would be an overclaim, and the discipline is to name the weaker
true statement and stop.

1. **Full $\Gamma$ is signed ⟹ spectral radius only.** For the signed $\Gamma$ we
   may take $\rho(\Gamma) = \max_k|\lambda_k|$ and nothing more; Perron–Frobenius
   does *not* apply, so there is no guaranteed real positive dominant eigenvalue,
   no nonnegative eigenvector, and the word "Perron root" is **not** licensed for
   $\Gamma$. It is licensed for $\Gamma^+$ alone.

2. **$\rho(\Gamma) < 1$ as a full-system cascade gate is analogy, not theorem.**
   Only $\rho(\Gamma^+) < 1$ carries a proof — via Galton–Watson criticality of
   the majorant process — and even that is a *sufficient* condition for the signed
   system, established by a dynamical majorant argument, **not** by a spectral
   inequality $\rho(\Gamma^+) \ge \rho(\Gamma)$ (which is false in general: the
   standard Wielandt bound gives $\rho(\Gamma) \le \rho(|\Gamma|)$ and
   $\rho(\Gamma^+) \le \rho(|\Gamma|)$, both pointing away from what we would need).
   A criticality statement for the *signed* $\rho(\Gamma)$ itself is not
   established here.

3. **The propagation dynamics is a modeling choice, not yet posited as settled.**
   The Galton–Watson reading — and with it the majorant argument underpinning the
   sufficient condition — requires an explicit generating dynamics: a rule for how a
   co-failure impulse at one agent propagates to others, under which (a) $\Gamma^+$
   is the mean-offspring matrix and (b) the $\Gamma^+$-only process dominates the
   signed process. We have *not* fixed that dynamics. Different dynamics could break
   either the branching interpretation or the domination, and with them the
   sufficient condition. Positing the dynamics explicitly and checking these two
   properties is an open item; until it is done, treat §"Galton–Watson" and
   §"The gate" as *conditional on* a dynamics of this kind, not as free consequences
   of the definition of $\Gamma$.

4. **The C387 spectral identity is still analogy-only.** As in the earlier draft:
   whether $\Gamma^+$'s Perron structure coincides with Chung's
   directed-Laplacian-under-$\pi$, or merely shares the shape, must be argued from
   the definitions. The motivation transfers with certainty; the machinery only on
   condition.

## Precedent, novelty, and one hazard

The machinery — a directed matrix summarized by a spectral cascade gate — has a
precedent in arXiv 2606.20493, which builds this kind of directed spectral gate and
reports $\rho = 1.296$. But its estimand is **preference drift** (an $L^2$
weight-shift between evaluator rounds), **not co-failure**. The number 1.296 must
**not** be imported as a co-failure datapoint: it measures a different quantity, and
even on its own terms the per-link effect was not significant ($p = 0.589$), so it
is the $\rho > 1$ *regime* that survives there, not the coefficient. Right
machinery, wrong estimand — the same relationship this section has to that paper.

Two nearer papers sharpen the boundary rather than crossing it. arXiv 2603.04474
("Spark to Fire") does carry a directed matrix and a spectral-radius gate
($\beta\,\rho(A) > \delta$), but its $A$ is the binary *communication-adjacency*
matrix and its estimand is *error propagation* through a message-passing pipeline
— one agent's false claim contaminating a downstream agent's context — not the
conditional co-failure of agents erring independently on the same input.
arXiv 2606.27288 has the co-failure estimand ($\beta$, $\bar\rho$, a Gaussian
copula) but is *entirely symmetric*: no directed matrix, no Perron root.

So the specific object — a **directed, conditional-excess co-failure matrix
$\Gamma$, split into a nonnegative excitatory part $\Gamma^+$ carrying a genuine
Perron root and a branching-process criticality gate** — appears unclaimed
(novelty search, 2026-07-29; confidence ~80%). What exists is the machinery
(directed spectral gates for drift and for propagation) and the estimand (symmetric
co-failure statistics), but not their composition, and not with the $\Gamma^+$
decomposition that makes the criticality reading exact.

## Open questions

- **Estimation.** $\Gamma$ needs the conditional $\Pr[j \mid i]$, which needs
  enough *$i$-wrong* events to estimate. For a strong anchor with a low error rate,
  the conditioning event is rare and $\Gamma_{i\cdot}$ is the noisy row — the
  finite-sample behavior is worst exactly where the anchor is, which is the row we
  most care about, and the row that dominates $\rho(\Gamma^+)$ in the asymmetric
  star. A shrinkage / minimum-support treatment is needed before any
  $\rho(\Gamma^+)$ estimate is trustworthy.
- **The propagation dynamics.** Posit it explicitly (weak joint 3) and verify that
  $\Gamma^+$ is its mean-offspring matrix and that it dominates the signed process.
  Until then the criticality gate is conditional.
- **The transfer gate.** Does $\Gamma^+$'s Perron structure actually coincide with
  Chung's directed-Laplacian-under-$\pi$, or is the C387 correspondence analogy-only?
  This must be argued from the definitions, not assumed from the shared shape.
- **Reduction to Leg 1.** Under equal marginals $\Gamma$ is symmetric; it should
  then reduce to (a function of) the symmetric joint-tail object Leg 1 already
  reports. Verifying that limit is the consistency check that keeps the directed
  companion honest as a *companion* rather than a rival.
