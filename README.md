# RecKAN — Raw Notebooks (source files)

These are the original working notebooks (Kaggle-style), each containing several
large, self-contained cells (imports + model + training loop all in one cell).
This README describes what's inside each file before splitting.

> Note: `*-checkpoint.ipynb` files are Jupyter's auto-save copies of the notebook
> with the same name (e.g. `reckan-checkpoint.ipynb` = autosave of `reckan.ipynb`).
> They are identical/near-identical to their main counterpart and don't need to be
> tracked in git — add `*-checkpoint.ipynb` and `.ipynb_checkpoints/` to `.gitignore`.

## `cnn-reckan.ipynb` (3 cells)
CNN + RecKAN hybrid model, MNIST classification. Each cell is a full, independent
run of the same architecture with slightly different settings:
- **Cell 1** — `EPOCHS=20`, seed 42
- **Cell 2** — `EPOCHS=50`, seed 42 (adds separate `TEST_BATCH_SIZE`)
- **Cell 3** — `EPOCHS=50`, seed 42 (alternate variant of cell 2)

## `reckan.ipynb` (8 cells)
Core development notebook for the recursive polynomial basis and RecKAN.
- **Cell 1** — Kaggle environment boilerplate (lists `/kaggle/input` files) — not needed outside Kaggle
- **Cell 2** — `RecursivePolyBasis` module, v1
- **Cell 3** — `RecursivePolyBasis` module, v2 (documented version)
- **Cell 4** — Full RecKAN vs. MLP training script on MNIST, v1
- **Cell 5** — Same as above, v2 (adds train/val split via `random_split`)
- **Cell 6** — `RecurrenceBasis` module + 2D basis-function plots
- **Cell 7** — `RecurrenceBasis` module + 3D basis-function plots
- **Cell 8** — Parameter-matched MLP baseline for MNIST (for fair comparison)

## `reckan-ex.ipynb` (14 cells)
Extended experiments: RecKAN vs. 3 baseline KANs (ChebyKAN, JacobiKAN, SplineKAN)
across multiple datasets and seeds.
- **Cell 1** — Core framework: model definitions + `argparse`-based `main()` (used by other cells)
- **Cell 2** — Runs the benchmark on ECG5000 (`aeon` install + `main()` call)
- **Cell 3** — Loads/prints results table from CSV, with manual fallback data
- **Cell 4** — Bar chart of results (RecKAN vs. baselines, per dataset)
- **Cell 5** — Installs `aeon`, runs benchmark on all datasets
- **Cell 6** — Full benchmark run, `seed=1`
- **Cell 7** — Full benchmark run, `seed=2`
- **Cell 8** — ETTh1 forecasting benchmark, seeds 1/2/42
- **Cell 9** — CNN-RecKAN, `EPOCHS=20`, `seed=1`
- **Cell 10** — CNN-RecKAN, `EPOCHS=20`, `seed=2`
- **Cell 11** — CNN-RecKAN, `EPOCHS=50` (v1), `seed=1`
- **Cell 12** — CNN-RecKAN, `EPOCHS=50` (v1), `seed=2`
- **Cell 13** — CNN-RecKAN, `EPOCHS=50` (v2), `seed=1`
- **Cell 14** — CNN-RecKAN, `EPOCHS=50` (v2), `seed=2`

## `recplot_.ipynb` (1 cell)
Standalone plotting script for the recursive polynomial basis — generates the
paper-style figures (`degree_analysis.png`, `piecewise_1d_comparison.png`,
`recursive_basis_experiments.png`, `selected_experiments.png`).

## `cnn-reckan-checkpoint.ipynb`, `reckan-checkpoint.ipynb`, `reckan-ex-checkpoint.ipynb`
Jupyter autosave checkpoints of the three notebooks above. Same content, no new
information — safe to exclude from the GitHub repo.

---

For the same content already split into one clean notebook per experiment and
organized into folders (`basis/`, `mnist_experiments/`, `cnn_reckan/`,
`multi_dataset_benchmark/`, `results_visualization/`, `figures/`), see the
`reckan-repo.zip` shared earlier in this conversation — it has its own README.md.
