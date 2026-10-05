# From Peroxides to Qubits

**Using glow-stick chemistry to introduce excited states, conical intersections and quantum computing to undergraduates**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR-GITHUB-USERNAME/peroxides-to-qubits/blob/main/Peroxides_to_Qubits.ipynb)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
[![License: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/content-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

A self-contained Jupyter / Google Colab teaching module. Students stretch the O–O bond of
hydrogen peroxide, follow the decomposition of 1,2-dioxetane with SA-CASSCF (S₀, S₁, T₁),
verify the conical topology of an S₀/S₁ intersection, and then solve the same CAS(8,6)
active-space problem on a 12-qubit simulator with VQE, SSVQE and state-averaged
orbital-optimized VQE (SA-OO-VQE).

The module accompanies the article:

> S. Hariharan, *From Peroxides to Qubits: Using Glow-Stick Chemistry to Introduce Excited
> States, Conical Intersections, and Quantum Computing to Undergraduates*,
> ChemRxiv (2026), DOI: *to be added*.

## Contents

| File | Description |
| --- | --- |
| `Peroxides_to_Qubits.ipynb` | Student notebook: narrative, code and embedded questions (no outputs) |
| `Peroxides_to_Qubits_executed.ipynb` | The same notebook with all outputs, for reference |
| `Peroxides_to_Qubits_executed.pdf` | PDF rendering of the executed notebook |
| `glowstick_data.zip` | Precomputed geometries, orbitals, intersection-point data and reference results read by the notebook |
| `requirements.txt` | Python dependencies (pinned versions used for all reported numbers) |

Worked answers to the notebook and assessment questions (`Instructor_notes.docx`) are part
of the Supporting Information of the article and are not posted here, so that students
cannot look up the answers.

### Notebook outline

0. Setup
1. Warm-up: breaking the O–O bond of hydrogen peroxide (RHF, broken-symmetry UHF, CASSCF(2,2))
2. The whole reaction: 1,2-dioxetane → 2 formaldehyde (SA-CASSCF + NEVPT2, S₀/S₁/T₁)
3. Is it really a *conical* intersection? (branching plane, tilt and cone opening)
4. The same problem, written for a quantum computer (Jordan–Wigner, 12 qubits)
5. VQE, and then SSVQE: one circuit, two states (the quantum counterpart of CASCI)
6. Orbital optimization: SA-OO-VQE (the quantum counterpart of SA-CASSCF)

## Running the notebook

### Google Colab (no installation)

1. Click the **Open in Colab** badge above.
2. Run the cells from the top. The first cell installs PySCF and PennyLane; if Colab asks
   to restart the session, restart and run again from the top.
3. The data archive is downloaded automatically from this repository. (If you opened a local
   copy of the notebook instead, upload `glowstick_data.zip` with the file browser on the left.)

### Local installation

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/peroxides-to-qubits.git
cd peroxides-to-qubits
python -m venv .venv && source .venv/bin/activate     # Python >= 3.11
pip install -r requirements.txt
jupyter lab Peroxides_to_Qubits.ipynb
```

The notebook unpacks `glowstick_data.zip` itself and writes every figure (PDF and PNG) to a
`figures/` folder.

### Computing time

About 30 min on a free Colab instance and 10–15 min on a recent laptop, most of it in the
orbital-optimization part (Part 6). Parts 1–5 take a few minutes and fit in one class session.

## Reproducibility

All numbers in the article were obtained with PySCF 2.14 and PennyLane 0.45 (noise-free
`lightning.qubit` state-vector simulation). Results from variational optimizations (VQE,
SSVQE, SA-OO-VQE) can differ by a few tenths of a kcal/mol between computers because the
optimizer path depends on floating-point details; this is discussed with students in Part 6.

## Citation

If you use this module in teaching or research, please cite the article above and this
archive (see `CITATION.cff`, or use the Zenodo DOI).

## License

- Code: [MIT](LICENSE)
- Notebook text, questions, figures and data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## Contact

Seenivasan Hariharan — QuasiQuantum, Leiden, The Netherlands — hseeni@gmail.com
