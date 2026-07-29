---
status: SKETCH — Lyra, 2026-07-29, staging for three-leg joint paper
section: Directed companion — "Co-failure has direction the symmetric summaries cannot see"
note: sketch altitude — prose + a few display equations, not final LaTeX. Hedging is load-bearing; do not smooth it out.
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
probability; $\Gamma_{ij}=0$ is the independence baseline.

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
structure of $\Gamma$ maps precisely onto Chung's directed-Laplacian spectrum
under the induced $\pi$ — i.e. whether "heterogeneous marginals" and "non-uniform
$\pi$" are the *same* non-degeneracy driving the *same* spectral object, or merely
two things that both happen to break symmetry — is an **open transfer that must be
argued, not asserted**. I am claiming the analogy (both collapse in their
respective uniform/homogeneous limit) and flagging the identity as a gate. This is
the recurring discipline: assert the transfer, then verify it; do not wave at it.
The C387 lesson transfers as motivation with certainty and as machinery only on
condition.

## The gate

Take the Perron root — the spectral radius $\rho(\Gamma)$, the largest-modulus
eigenvalue of the directed matrix — as the cascade threshold:
$$
\rho(\Gamma) < 1 \;\Rightarrow\; \text{co-failure contained}, \qquad
\rho(\Gamma) \ge 1 \;\Rightarrow\; \text{co-failure cascades.}
$$
The reading is that a co-failure impulse at one agent, propagated through the
excess-conditional couplings, decays iff the dominant directed eigenvalue is
sub-unit. (Whether $\Gamma$'s off-diagonal sign structure guarantees a real
positive Perron root in the Perron–Frobenius sense, or only a spectral radius, is
part of the transfer gate above — $\Gamma$ can carry negative entries where a
failure is anti-correlated, so the clean Perron–Frobenius picture is not free.)

## Precedent, novelty, and one hazard

The machinery — a directed matrix summarized by a Perron-root cascade gate — has a
precedent in arXiv 2606.20493, which builds exactly this kind of directed spectral
gate and reports $\rho = 1.296$. But its estimand is **preference drift** (an $L^2$
weight-shift between evaluator rounds), **not co-failure**. The number 1.296 must
**not** be imported as a co-failure datapoint: it measures a different quantity,
and even on its own terms the per-link effect was not significant ($p = 0.589$),
so it is the $\rho > 1$ *regime* that survives there, not the coefficient. Right
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
$\Gamma$ with a Perron-root cascade gate** — appears unclaimed (novelty search,
2026-07-29; confidence ~80%). What exists is the machinery (directed Perron gates
for drift and for propagation) and the estimand (symmetric co-failure statistics),
but not their composition.

## Open questions

- **Estimation.** $\Gamma$ needs the conditional $\Pr[j \mid i]$, which needs
  enough *$i$-wrong* events to estimate. For a strong anchor with a low error rate,
  the conditioning event is rare and $\Gamma_{i\cdot}$ is the noisy row — the
  finite-sample behavior is worst exactly where the anchor is, which is the row we
  most care about. A shrinkage / minimum-support treatment is needed before any
  $\rho(\Gamma)$ estimate is trustworthy.
- **The transfer gate.** Does $\Gamma$'s Perron structure actually coincide with
  Chung's directed-Laplacian-under-$\pi$, or is the C387 correspondence analogy-only?
  This must be argued from the definitions, not assumed from the shared shape.
- **Reduction to Leg 1.** Under equal marginals $\Gamma$ is symmetric; it should
  then reduce to (a function of) the symmetric joint-tail object Leg 1 already
  reports. Verifying that limit is the consistency check that keeps the directed
  companion honest as a *companion* rather than a rival.
