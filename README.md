**Quantum Boolean analysis: an eight-session reading group**

Draft prepared 8 September 2026. Audience: quantum information, extremal combinatorics, theoretical computer science, programming languages, and machine learning. **Eight meetings of 90 minutes each, totaling 12 contact hours.** The literature selection includes published foundations and explicitly identified 2026 preprints.

The proposed route is **Fourier analysis → noise and hypercontractivity → quantum observables → structure and learning → current limitations and research questions**. Two classical sessions give the common language needed for six quantum sessions. With this time budget, the achievable goal is to understand several representative proof methods, read current theorem statements critically, and identify a small joint project. A comprehensive survey would require a longer series.

Hypercontractivity is an excellent organizing technique. It is a central tool with many applications and can be introduced early in the classical background. The group should repeatedly ask which part of a classical proof survives and which part needs a new matrix inequality, definition, or argument.

**Scope and preparation.** The main setting is the algebra of operators on n qubits. A quantum Boolean function is a Hermitian observable A satisfying A² = I, so its measurement outcomes belong to {−1,+1}. A classical Boolean function embeds as a diagonal observable. The analytic framework also studies general operators, bounded observables, and noise channels; we will say when we broaden from Boolean observables to these objects. The foundational reference is [Montanaro–Osborne, Quantum Boolean functions](https://arxiv.org/abs/0810.2435).

Assume basic probability, linear algebra, and comfort reading proofs. Before session 1, participants should review orthonormal bases, expectation, and Cauchy–Schwarz. Before session 3, the quantum participants should circulate a short primer on tensor products, Pauli matrices, density matrices, measurement expectations, and partial trace. Operator algebras and advanced quantum information are not prerequisites.

Budget about 45–75 minutes of preparation per meeting. The presenter should select at most roughly 8–12 pages of core excerpts from the locations below; section ranges identify where to select material, not an instruction to read every proof in those sections. Other references are presenter preparation or optional follow-up. Use the [2021 arXiv edition of O’Donnell’s book](https://arxiv.org/abs/2105.10386), and refer to sections rather than page numbers.

| Session | Central question | Main outcome |
|---|---|---|
| 1. Classical Fourier analysis | How do coefficients describe dependence on variables and response to noise? | Compute spectra, influences, and noise stability in small examples. |
| 2. Classical hypercontractivity | How does smoothing give structural information? | Understand a low-degree moment bound and the architecture of KKL. |
| 3. The quantum Boolean cube | What replaces functions, coordinates, and expectation? | Build the classical–quantum dictionary and calculate a noncommuting example. |
| 4. Quantum hypercontractivity | Which proof steps extend to matrices? | Derive a spectral-tail bound for a local Hamiltonian. |
| 5. Influences and juntas | What can small influence tell us about quantum observables? | Distinguish proved geometric-influence results from the original L² question. |
| 6. Learning quantum observables | How does Fourier structure become a learning algorithm? | Trace coefficient control to approximation and specify the access model. |
| 7. Erasure noise and information | Why do new channels require new analytic tools? | Connect a recent inequality to common-randomness communication bounds. |
| 8. Current counterexamples and projects | Where does the classical analogy fail, and what can we investigate? | Understand a 2026 obstruction and select one or two bounded pilot projects. |

1. **Classical Fourier analysis, influence, and noise.**

   Core reading: O’Donnell §§1.2–1.4. Use definitions and selected examples from §§2.2–2.4 in a presenter handout; those sections are supplementary reading.

   Introduce parity characters, Fourier coefficients, Parseval, degree, coordinate influence, and the noise operator. Work with a dictator, parity, and majority on three bits. Prove Parseval and the diagonal action of noise on Fourier coefficients. Explain how squared coefficient mass records dependence on coordinates.

   Group exercise: compare a dictator and parity under noise, and calculate the spectrum of three-bit majority. End with one page of common notation. The ML connection is approximation by a small collection of coefficients; the combinatorial connection is sensitivity to coordinate changes.

2. **Hypercontractivity and the classical structural argument.**

   Core reading: O’Donnell §9.1 and the KKL statement and proof outline in §9.6. Optional proof background: §§9.3–9.4; §10.1 gives the general parameter range.

   State the hypercontractive inequality and explain why changing the norm measures a stronger form of smoothing. Derive the low-degree moment estimate from the noise inequality. Use KKL, the theorem guaranteeing an influential coordinate, as the structural destination. Present its proof architecture and identify the step using the Boolean-valued assumption: a discrete derivative takes values in {−1,0,1}, so its absolute value equals its square. Recall the statement of Friedgut’s junta theorem as motivation for session 5.

   Work through the one-bit 2-to-4 inequality and a tensorization step, then derive the moment estimate. Keep KKL at the level of a proof outline so that there is time to discuss how its ingredients fit together. The deliverable is a proof diagram recording where hypercontractivity enters.

3. **Pauli Fourier analysis and noncommuting examples.**

   Core reading: [Montanaro–Osborne](https://arxiv.org/abs/0810.2435), §§3 and 5; selected examples from §4. Use §2 as a reference for notation.

   Replace parity characters by Pauli strings and uniform expectation by normalized trace. Explain Pauli degree, normalized Schatten norms, and conditional expectation obtained by tracing out a qubit and inserting identity. Show explicitly how diagonal observables recover the classical theory.

   Work through

   $$
   A_\theta=\cos\theta\,X\otimes I+\sin\theta\,Z\otimes Z.
   $$

   Verify Aθ² = I using anticommutation. Compute its coefficients and the effect of depolarizing noise. Reuse this example in session 5. A second exercise is to see why deleting a coordinate need not preserve A² = I.

   The deliverable is a shared dictionary: parity/Pauli string, expectation/normalized trace, Lp/Schatten p, resampling/depolarization, and coordinate averaging/conditional expectation.

4. **Quantum hypercontractivity with a complete application.**

   Core reading: Montanaro–Osborne §8, especially Theorem 46 and Corollary 51 in the arXiv version; [Montanaro, Some applications of hypercontractive inequalities in quantum information theory](https://arxiv.org/abs/1208.0161), §3, especially Corollary 14 and Theorem 15. Presenter supplement: [King, Hypercontractivity for semigroups of unital qubit channels](https://arxiv.org/abs/1210.8412), Theorem 1 and Corollary 2.

   The one-qubit proof reduces to the classical two-point inequality after diagonalization. Explain why extending to many qubits requires a matrix argument. Treat that technical inequality as a supplied lemma, then prove the application: a low-degree Schatten moment estimate gives a bound on the fraction of large eigenvalues of a local Hamiltonian, by Markov’s inequality and a choice of moment.

   Clarify that k-local means a sum of terms each acting on at most k qubits. The spectral-tail conclusion concerns the proportion of eigenvalues, not the extreme eigenvalue. King supplies the full depolarizing parameter range beyond the original Montanaro–Osborne theorem.

5. **Quantum influences, KKL, and junta approximation.**

   Core reading: [Rouzé–Wirth–Zhang, Quantum Talagrand, KKL and Friedgut’s theorems and the learnability of quantum Boolean functions](https://arxiv.org/html/2209.07279v3), published in CMP in 2024. Select Theorem 3.6 from §3.2, §3.3’s KKL deduction, and the theorem statements in §3.4. Review §2’s influence definitions as needed.

   With dᵢA = A − EᵢA, compare the geometric influence ‖dᵢA‖₁ and squared L² influence ‖dᵢA‖₂², using normalized norms. For Aθ, the second-qubit values are |sin θ| and sin² θ. Thus an L¹ influence theorem does not immediately give the original L² statement.

   Supply the Talagrand inequality and prove its scalar deduction of KKL. Explain junta approximation as dependence on a small set of qubits, recording the actual influence assumptions and approximation norm. The quantum junta bound in this paper involves both total L¹ and L² influences. Inspect one smoothing estimate behind the supplied inequality and discuss where its proof requires a quantum argument.

   Presenter frontier update: [Blecher–Gao–Xu, Geometric influences on quantum Boolean cubes](https://arxiv.org/abs/2409.00224), published 2025, and [Chang–Li, Quantum Talagrand-type Inequalities via Variance Decay](https://arxiv.org/html/2601.01900v2), a 2026 preprint. Compare random restrictions with semigroup arguments. The original L²-KKL problem remains unresolved in the literature checked.

6. **Learning low-degree quantum observables.**

   Core reading: [Volberg–Zhang, Noncommutative Bohnenblust–Hille inequalities](https://arxiv.org/html/2210.14468), published in Mathematische Annalen in 2024. Select the main inequality in §1, the product-state reduction in §2, and Theorem 4.1 with its learning model in §4. The rest of §§3–4 is optional proof reading.

   Introduce Bohnenblust–Hille as an additional coefficient inequality. It controls a coefficient ℓp norm in terms of operator norm with a constant independent of the number of qubits. Explain coefficient thresholding and then the reduction from observable learning to classical learning. Track the dependence on degree separately from dependence on qubit count.

   The cited learning model supplies exact expectation-value queries (ρ, tr(Aρ)) for a specified ensemble of product states and guarantees normalized Schatten-2 approximation. Its logarithmic dependence on n does not by itself count measurement shots. Participants should distinguish queries, physical samples, runtime, output size, and approximation metric.

   Exercise: write a small learning experiment specification with all five quantities. Optional application reading: [Huang–Chen–Preskill, Learning to Predict Arbitrary Quantum Processes](https://preskill.caltech.edu/pubs/preskill-2023-learning.pdf), introduction and problem formulation, published 2023.

7. **A recent information-theoretic application: erasure channels.**

   Core reading: [Bao–Dong–Ou–Yao, Hypercontractivity for Quantum Erasure Channels via Variable Multipartite Log-Sobolev Inequality](https://arxiv.org/html/2311.14321v2), published in IEEE Transactions on Information Theory in July 2025. Select Theorem 1.2, Remark 1.3, the proof overview in §1.2, and the common-randomness task and Theorem 5.4 from §5.

   Begin with the operational problem: Alice and Bob share noisy entangled pairs and want matching random strings using one-way classical communication. Introduce the erasure flag and the weighted norm, equivalently an average over random partial traces. Explain the role of the new log-Sobolev inequality and locate the use of hypercontractivity in the communication lower bound.

   Focus on the task, the inequality’s meaning, and one step in the application, then explore why the previous tensorization argument fails. The proof of the multipartite log-Sobolev inequality is presenter background. End with a diagram linking operational resources to the analytic estimate.

8. **Where classical intuition fails, followed by a project workshop.**

   Core reading: [Joseph Slote, Dense Hamiltonians at the Parseval Limit: The Noncommutative BH Constant is Exponential and the Quantum FEI Conjecture is False](https://arxiv.org/html/2608.01424v1), an eight-page preprint posted 2 August 2026. Read §§1–3; the presenter prepares §4’s construction.

   The preprint constructs degree-d Boolean observables with exp(Ω(d²)) equally sized nonzero Pauli coefficients. Use the stated construction to calculate Fourier entropy and total squared-L² influence, and to derive the obstruction to a dimension-free quantum Fourier entropy–influence inequality. Connect its exponential BH lower bound to session 6. Label this explicitly as a recent preprint; it does not resolve the classical FEI conjecture.

   Use 5 minutes to recall the relevant definitions, 25 minutes for the result, 15 minutes for a construction example, 30 minutes for project pitches and discussion, and 15 minutes to select next steps. The output should be one or two one-page proposals, each specifying a mathematical object, a question, the closest known theorem, and a two-week first milestone.

**How to organize the meetings.** Pair presenters from different backgrounds where possible. One presents the mathematical argument; the other supplies examples and explains its significance from another field. Rotate both roles. Sessions 1–7 use the following 90-minute agenda. Session 8 uses the workshop allocation above.

| Time | Activity | Purpose |
|---|---|---|
| 0–5 min | Recap | Recall the previous result and the question for this meeting. |
| 5–20 min | Definitions and examples | Establish the objects and notation needed for the main argument. |
| 20–45 min | Proof or application | Work through the main argument or one selected part of a longer proof. |
| 45–60 min | Joint exercise | Calculate an example, verify a proof step, or test a proposed extension. |
| 60–85 min | Discussion across fields | Compare interpretations, obstacles, and possible research directions. |
| 85–90 min | Question log and next reading | Record unresolved points and agree on preparation for the next meeting. |

Maintain a shared question log from the first meeting. Record the exact statement under discussion, which proof step fails, a small example, and the source or status of the question. After session 4, identify two or three recurring interests. After session 6, have pairs outline potential projects so that the final workshop starts with concrete material.

**Possible collaboration pilots.** These are proposed starting tasks, not claims of established open problems or guaranteed novelty. Check the closest literature before developing a new theorem claim.

| Pilot | First concrete milestone | Contributions across the group |
|---|---|---|
| Learning with finite measurement precision | Reproduce a small coefficient-thresholding experiment; replace exact expectations by estimated ones and account for errors and measurement shots. | ML supplies learning and robustness questions; QI specifies access and measurements; analysis supplies coefficient estimates. |
| Extremal families of Pauli strings | Reproduce a weight-versus-coordinate-load bound, enumerate small families, and identify a restricted case with a sharp bound. | Combinatorics supplies constructions and counting; QI interprets commutation; TCS supplies search algorithms. |
| Certified observable approximation | Define a tiny circuit language, propagate observables backwards, and prove one sound error rule for truncating Pauli expansions under a specified input model. | PL supplies semantics and composition; QI supplies channel action; ML and analysis supply approximation criteria. |
| Erasure inequalities in small systems | Test the inequality’s parameter dependence on one- and two-qubit examples, then prove one restricted case or locate an extremizer. | QI supplies channel models; analysis supplies norm inequalities; computation guides examples. |

For the extremal pilot, a useful existing starting point is [Slote–Volberg–Zhang, Tightness of and counterexamples to several quantum estimates](https://arxiv.org/html/2608.04411v2), an August 2026 preprint. §8.1 gives a short double-counting bound for pairwise anticommuting strings in terms of string weight and maximum qubit load. §7 explains why an FEI counterexample in that paper does not disprove KKL: its ancilla is highly influential.

The certified-approximation pilot must state its error guarantee precisely. Small normalized Schatten-2 error alone is not a dimension-independent worst-case guarantee on every input state. Choosing the input ensemble and the observable being predicted is part of the problem definition.

**Optional substitutions and reading cautions.** If communication complexity is the strongest shared interest, replace session 7 with [Ben-Aroya–Regev–de Wolf, A Hypercontractive Inequality for Matrix-Valued Functions](https://homepages.cwi.nl/~rdewolf/publ/qc/matrixbeckner.pdf), §§3–4, on quantum random access codes. This uses matrix-valued functions on a classical cube, a related but distinct setting. If structural stability is preferred, replace session 7 with quantum FKN, the statement that concentration on Fourier levels 0 and 1 forces closeness to an observable on at most one qubit. Pair Montanaro–Osborne §9 with the corrected argument in §6 of [Blecher–Gao–Xu](https://arxiv.org/html/2409.00224v1).

Keep one main argument or application per meeting, with additional proof reading optional. Protect the scheduled discussion time throughout the 12-hour series: finding a collaboration depends on participants comparing their questions and working through examples together.
