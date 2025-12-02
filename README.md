# Axiomatic Fundamentalism Calculus (AFC)
## The Hidden Form of Stokes

> *Axioms → Distinctions → Relations → Motifs → Math.*  
> *This is the way.*

This repository contains the LaTeX source for a short note that derives a
discrete Stokes identity as a consequence of a single relational axiom
(`Null = Infinity`) under the Axiomatic Fundamentalism (AF) protocol
\cite{reginald2025af}. The note also records:

1. A path–complexity consequence: **Memory paths grow at most
   \(\mathcal{O}(n \log n)\)** in distinguishable information.
2. A clustering consequence: **Null clusters have additive, scale–invariant
   aggregate divergence.**
3. An isotropy consequence: **Stochastic ignorance induces isotropic topology**
   when the kernel is symmetric on indistinguishable positions.
4. An information–theoretic appendix: **capacity \(C(P)\)** for the Markov
   kernel representing the Memory–Null coupling.

The construction is fully discrete and relational. Classical discrete
generalized Stokes (chains/cochains/coboundaries) appears only as a mapped
shadow.

---

## AF Protocol Summary

The document is organised to follow the AF pipeline:

1. **Axiom**  
   - A single Null axiom: a distinguished state \(\mathcal{N}\) with no
     Distinctions and no Relations, written
     \(\mathcal{N} \equiv \infty \equiv \chi\).

2. **Immediate Structural Consequences**  
   - Regions as finite “inside vs. Null baseline” groupings.  
   - Relations as connections induced only after Distinctions exist.

3. **Modelling Choices**  
   - Memory State \(p\) on a finite index set of Distinctions \(V\).  
   - Markov Kernel \(P\) on \(V\).  
   - Flux \(\phi_{ij} = p(i)P_{ij} - p(j)P_{ji}\).  
   - Divergence \(\mathrm{div}(i) = \sum_j \phi_{ij}\).  
   - Regions \(R\) and boundary pairs \((i,j)\) with \(i \in R, j \notin R\).

4. **Consequences**  
   - K1: Path complexity \(\mathcal{O}(n\log n)\).  
   - K2: Null clustering and parallel additivity of interior divergence.  
   - K3: Isotropic ignorance (symmetric kernel) ⇒ isotropic topology.

5. **Corollary (AFC Stokes)**  
   - For any Region \(R \subseteq V\),
     \[
       \sum_{i\in R} \mathrm{div}(i)
       =
       \sum_{\substack{i\in R \\ j\notin R}} \phi_{ij},
     \]
     with explicit algebraic proof and falsification hooks.

6. **Appendix (Capacity)**  
   - Channel capacity \(C(P)\) in trits for the same kernel \(P\), and a
     consistency test against empirical per–step information rates.

---

## Repository Layout

```text
.
├── main.tex
├── sections
│   ├── 00_title.tex
│   ├── 01_abstract.tex
│   ├── 02_axioms.tex
│   ├── 03_glossary.tex
│   ├── 04_choices.tex
│   └── 05_consequences.tex
├── corollaries
│   └── 00_stokes.tex
├── appendices
│   └── 00_capacity.tex
└── refs.bib
````

### `main.tex`

Top–level LaTeX file. Handles:

* Document class and packages.
* Theorem/axiom/choice/consequence environments.
* Inclusion of all sections, corollaries, and appendices.
* Bibliography style and `\bibliography{bib}`.

### `sections/00_title.tex`

Title and author block for the note:

* Title: **“Axiomatic Fundamentalism Calculus (AFC): The Hidden Form of Stokes”**
* Optional AF epitaph line.

### `sections/01_abstract.tex`

Abstract in AF–neutral style:

* States the Null axiom.
* Announces the AFC Stokes identity.
* Mentions the discrete Stokes mapping and capacity bounds.
* No narrative, no “we”; only what is actually proved.

### `sections/02_axioms.tex`

AF structural core:

* **Axiom A1: Null = Infinity.**
  A single Null state (\mathcal{N}) with no Distinctions and no Relations
  in the model universe, with symbols (\infty) and (\chi) used synonymously.

* **Consequence:** Regions and Relations arise only after Distinctions are
  introduced. Links back to AF relational foundations (RF1, RF2)
  \cite{reginald2025af}.

### `sections/03_glossary.tex`

Glossary of all permitted objects:

* Null State, Distinction, Relation, Region.
* Memory State, Markov Kernel, Flux, Divergence.
* “Observer/Modeller” defined as **just the Memory State and its updates**.
* AFC Stokes identity and Capacity (C(P)) described at a high level.

Nothing exists in the model beyond these entities and their Relations.

### `sections/04_choices.tex`

Modelling Choices (not axioms):

* Memory State (p : V \to [0,1]).
* Markov Kernel (P) with row–stochastic constraints.
* Net flux (\phi_{ij} = p(i)P_{ij} - p(j)P_{ji}).
* Divergence (\mathrm{div}(i) = \sum_j \phi_{ij}).
* Regions (R \subseteq V) and boundary (\partial R) as ordered pairs
  ((i,j)) with (i \in R, j \notin R).

These are the only modelling inputs used later.

### `sections/05_consequences.tex`

Three Consequences derived from the Choices:

1. **Consequence 1: Path Complexity (\mathcal{O}(n\log n))**

   * Introduces a scale–invariant branching regime with
     (m_t \le c t).
   * Shows the number of distinct Memory paths of length (n) obeys
     (N_n \le c^n n!), hence (\log_3 N_n = \mathcal{O}(n\log n)).
   * Interpreted as an upper bound on distinguishable path information.

2. **Consequence 2: Null Clustering and Parallelism**

   * Defines interior divergence (D(R) = \sum_{i\in R} \mathrm{div}(i)).
   * Shows (D(R)) equals boundary flux via AFC Stokes, and is additive over
     disjoint Regions.
   * Any finite Region can be treated as a Null cluster with aggregate
     divergence (D(R)), preserving the Stokes form.

3. **Consequence 3: Isotropic Ignorance and Isotropic Topology**

   * Defines isotropic ignorance: identical Memory probabilities and
     kernel entries up to permutations of indistinguishable positions.
   * Shows the adjacency structure and induced topology are invariant under
     such permutations.
   * Isotropic Null clustering preserves this invariance.

### `corollaries/00_stokes.tex`

Main corollary file:

* **Corollary (AFC Stokes Identity).**
  [
  \sum_{i\in R} \mathrm{div}(i)
  =============================

  \sum_{\substack{i\in R \ j\notin R}} \phi_{ij}
  ]
  for any Region (R), derived purely by finite algebra from the Choices.

* **Falsification Hooks.**

  * Internal cancellation tests for antisymmetry of (\phi).
  * Divergence vs. boundary–flux consistency checks for Regions and kernels.

* **Discrete Stokes Mapping.**

  * Dictionary to chains, cochains, and coboundary (d\omega).
  * Alignment with standard discrete Stokes on cell complexes
    \cite{whitney1957,munkres1984,hirani2003,desbrun2005dec}.

### `appendices/00_capacity.tex`

Information–theoretic consequences for the same kernel (P):

* Definitions of single–step channel ((X,Y)), mutual information (I_p(X;Y))
  in trits, and capacity (C(P) = \max_p I_p(X;Y)).
* A simple capacity bound and a consistency test: any empirical per–step rate
  (R > C(P)) implies either a mis–specified kernel, dependence across steps,
  or hidden structure beyond the stated Choices.

### `bib.bib`

BibTeX entries for:

* AF protocol and General Mechanics:

  * Reginald (2025), *Axiomatic Fundamentalism (AF)* \cite{reginald2025af}.
  * Reginald (2025), *General Mechanics* \cite{reginald2025gm}.

* Discrete Stokes / cochain sources:

  * Whitney (1957) \cite{whitney1957}.
  * Munkres (1984) \cite{munkres1984}.
  * Hirani (2003) \cite{hirani2003}.
  * Desbrun et al. (2005) \cite{desbrun2005dec}.

* Standard information theory:

  * Shannon (1948), *A Mathematical Theory of Communication* \cite{shannon1948}.
  * Cover & Thomas (2006), *Elements of Information Theory* \cite{coverthomas2006}.

---

## Building the PDF

From the repository root, a minimal build is:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

or, using `latexmk`:

```bash
latexmk -pdf main.tex
```

Adjust as needed if you use a different engine or toolchain.

---

## Extending the Note

When adding to this repository, keep the AF protocol ordering:

1. **Do not add new axioms lightly.** Prefer to add Choices or Consequences.
2. **New structure** (graphs, metrics, etc.) should be introduced as
   `\begin{choice}...\end{choice}` and referenced explicitly.
3. **New results** (bounds, identities) should be introduced as
   `consequence`, `corollary`, or `theorem`, with a clear “Derivation” line
   listing which Axioms, Consequences, and Choices they depend on.
4. Avoid narrative or agency (“we choose”, “the observer does”); describe
   only the relational structure and modelling decisions.

If you add further appendices (e.g. continuum shadows, examples), ensure they
do not introduce unlabelled assumptions and that they explicitly state their
dependence on the core AF objects defined in the main text.

---
