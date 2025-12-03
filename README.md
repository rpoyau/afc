Gotcha — the problem is that this whole block (and the rest of the README) is still LaTeX-flavoured, not GitHub-Markdown-safe.

Here’s a **fully cleaned README** where:

* No `$...$`, `\(...\)`, or `\[...\]`
* No `\cite{...}`
* All math is plain text or in `code` / fenced blocks

You can drop this straight into `README.md`:

````markdown
# Axiomatic Fundamentalism Calculus (AFC)
## The Hidden Form of Stokes
[![DOI](https://zenodo.org/badge/1106264434.svg)](https://doi.org/10.5281/zenodo.17795590)

> Axioms → Distinctions → Relations → Motifs → Math.  
> This is the way.

This repository contains the LaTeX source for a short note that derives a
discrete Stokes identity as a consequence of a single relational axiom
("Null = Infinity") under the Axiomatic Fundamentalism (AF) protocol. The
note also records:

1. A path–complexity consequence: **memory paths grow at most O(n log n)**
   in distinguishable information.
2. A clustering consequence: **Null clusters have additive, scale–invariant
   aggregate divergence.**
3. An isotropy consequence: **stochastic ignorance induces isotropic topology**
   when the kernel is symmetric on indistinguishable positions.
4. An information–theoretic appendix: **capacity C(P)** for the Markov
   kernel representing the Memory–Null coupling.

The construction is fully discrete and relational. Classical discrete
generalized Stokes (chains / cochains / coboundaries) appears only as a
mapped shadow.

---

## AF Protocol Summary

The document is organised to follow the AF pipeline:

1. **Axiom**  
   - A single Null axiom: a distinguished state N with no
     Distinctions and no Relations, written

     ```text
     N ≡ ∞ ≡ χ
     ```

2. **Immediate Structural Consequences**  
   - Regions as finite “inside vs. Null baseline” groupings.  
   - Relations as connections induced only after Distinctions exist.

3. **Modelling Choices**  
   - Memory state `p` on a finite index set of Distinctions `V`.  
   - Markov kernel `P` on `V`.  
   - Flux `φ_ij = p(i) P_ij - p(j) P_ji`.  
   - Divergence `div(i) = Σ_j φ_ij`.  
   - Regions `R` and boundary pairs `(i, j)` with `i ∈ R`, `j ∉ R`.

4. **Consequences**  
   - K1: Path complexity `O(n log n)`.  
   - K2: Null clustering and parallel additivity of interior divergence.  
   - K3: Isotropic ignorance (symmetric kernel) ⇒ isotropic topology.

5. **Corollary (AFC Stokes)**  

   For any region `R ⊆ V`,

   ```text
   Σ_{i ∈ R} div(i) = Σ_{i ∈ R, j ∉ R} φ_ij
````

with explicit algebraic proof and falsification hooks.

6. **Appendix (Capacity)**

   * Channel capacity `C(P)` (in trits) for the same kernel `P`, and a
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
```

### `main.tex`

Top–level LaTeX file. Handles:

* Document class and packages.
* Theorem / axiom / choice / consequence environments.
* Inclusion of all sections, corollaries, and appendices.
* Bibliography style and `\bibliography{refs}`.

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
  A single Null state `N` with no Distinctions and no Relations
  in the model universe, with symbols `∞` and `χ` used synonymously.

* **Consequence:** Regions and Relations arise only after Distinctions are
  introduced, tying back to AF relational foundations.

### `sections/03_glossary.tex`

Glossary of all permitted objects:

* Null state, Distinction, Relation, Region.
* Memory state, Markov kernel, flux, divergence.
* “Observer / Modeller” defined as **just the memory state and its updates**.
* AFC Stokes identity and capacity `C(P)` described at a high level.

Nothing exists in the model beyond these entities and their relations.

### `sections/04_choices.tex`

Modelling choices (not axioms):

* Memory state `p : V → [0, 1]`.
* Markov kernel `P` with row–stochastic constraints.
* Net flux `φ_ij = p(i) P_ij - p(j) P_ji`.
* Divergence `div(i) = Σ_j φ_ij`.
* Regions `R ⊆ V` and boundary `∂R` as ordered pairs `(i, j)` with
  `i ∈ R`, `j ∉ R`.

These are the only modelling inputs used later.

### `sections/05_consequences.tex`

Three consequences derived from the choices:

1. **Consequence 1: Path Complexity O(n log n)**

   * Introduces a scale–invariant branching regime with
     `m_t ≤ c t`.
   * Shows the number of distinct memory paths of length `n` obeys
     `N_n ≤ c^n n!`, hence `log_3 N_n = O(n log n)`.
   * Interpreted as an upper bound on distinguishable path information.

2. **Consequence 2: Null Clustering and Parallelism**

   * Defines interior divergence
     `D(R) = Σ_{i ∈ R} div(i)`.
   * Shows `D(R)` equals boundary flux via AFC Stokes, and is additive over
     disjoint regions.
   * Any finite region can be treated as a Null cluster with aggregate
     divergence `D(R)`, preserving the Stokes form.

3. **Consequence 3: Isotropic Ignorance and Isotropic Topology**

   * Defines isotropic ignorance: identical memory probabilities and
     kernel entries up to permutations of indistinguishable positions.
   * Shows the adjacency structure and induced topology are invariant under
     such permutations.
   * Isotropic Null clustering preserves this invariance.

### `corollaries/00_stokes.tex`

Main corollary file:

* **Corollary (AFC Stokes Identity).**

  ```text
  Σ_{i ∈ R} div(i) = Σ_{i ∈ R, j ∉ R} φ_ij
  ```

  for any region `R`, derived purely by finite algebra from the choices.

* **Falsification hooks.**

  * Internal cancellation tests for antisymmetry of `φ`.
  * Divergence vs. boundary–flux consistency checks for regions and kernels.

* **Discrete Stokes mapping.**

  * Dictionary to chains, cochains, and coboundary `dω`.
  * Alignment with standard discrete Stokes on cell complexes.

### `appendices/00_capacity.tex`

Information–theoretic consequences for the same kernel `P`:

* Definitions of single–step channel `(X, Y)`, mutual information `I_p(X; Y)`
  in trits, and capacity `C(P) = max_p I_p(X; Y)`.
* A simple capacity bound and a consistency test: any empirical per–step rate
  `R > C(P)` implies either a mis–specified kernel, dependence across steps,
  or hidden structure beyond the stated choices.

### `refs.bib`

BibTeX entries for:

* AF protocol and General Mechanics (Reginald, 2025).
* Discrete Stokes / cochain sources (Whitney, Munkres, Hirani, Desbrun et al.).
* Standard information theory (Shannon; Cover & Thomas).

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

1. **Do not add new axioms lightly.** Prefer to add choices or consequences.
2. **New structure** (graphs, metrics, etc.) should be introduced as
   `\begin{choice}...\end{choice}` in LaTeX and referenced explicitly.
3. **New results** (bounds, identities) should be introduced as
   `consequence`, `corollary`, or `theorem`, with a clear “Derivation” line
   listing which axioms, consequences, and choices they depend on.
4. Avoid narrative or agency (“we choose”, “the observer does”); describe
   only the relational structure and modelling decisions.

If you add further appendices (e.g. continuum shadows, examples), ensure they
do not introduce unlabelled assumptions and that they explicitly state their
dependence on the core AF objects defined in the main text.

```

If you want to *keep* LaTeX math in the repo but have a Markdown-safe README, this is the version to use.
```
