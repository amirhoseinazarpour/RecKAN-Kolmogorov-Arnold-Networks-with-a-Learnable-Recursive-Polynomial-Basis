# RecKAN — Notebooks

This repo splits the original monolithic Kaggle-style notebooks (each with several large, self-contained cells) into one clean notebook per experiment, organized by topic.

## Structure

```
basis/                      Core recursive polynomial basis module + visualizations
├── recursive_poly_basis_v1.ipynb
├── recursive_poly_basis_v2.ipynb            (documented / cleaner version)
├── recurrence_basis_visualization_2d.ipynb
└── recurrence_basis_visualization_3d.ipynb

mnist_experiments/           RecKAN vs. MLP baseline on MNIST
├── reckan_mnist_v1.ipynb
├── reckan_mnist_v2.ipynb                    (train/val split)
└── mlp_baseline_mnist.ipynb

cnn_reckan/                  CNN + RecKAN hybrid, multiple configs and seeds
├── cnn_reckan_epochs20_seed42.ipynb
├── cnn_reckan_epochs20_seed1.ipynb
├── cnn_reckan_epochs20_seed2.ipynb
├── cnn_reckan_epochs50_v1_seed42.ipynb
├── cnn_reckan_epochs50_v1_seed1.ipynb
├── cnn_reckan_epochs50_v1_seed2.ipynb
├── cnn_reckan_epochs50_v2_seed42.ipynb
├── cnn_reckan_epochs50_v2_seed1.ipynb
└── cnn_reckan_epochs50_v2_seed2.ipynb

multi_dataset_benchmark/     RecKAN vs. ChebyKAN/JacobiKAN/SplineKAN across datasets
├── reckan_vs_baselines_main.ipynb           (core models + argparse-based main())
├── run_ecg5000.ipynb
├── run_all_datasets.ipynb
├── reckan_vs_baselines_seed1.ipynb
├── reckan_vs_baselines_seed2.ipynb
└── reckan_vs_baselines_etth1_forecast.ipynb

results_visualization/       Loading and plotting benchmark results
├── plot_results_from_csv.ipynb
└── plot_results_bar_chart.ipynb

figures/                     Paper-ready figures for the recursive basis
├── recursive_basis_figures.ipynb
├── degree_analysis.png
├── piecewise_1d_comparison.png
├── recursive_basis_experiments.png
└── selected_experiments.png
```

## Notes

- Each notebook is self-contained (imports + code it needs), copied as-is from the
  original notebooks — no logic was changed, only split apart and renamed.
- Files with the same base experiment but different `SEED` or `EPOCHS` are kept as
  separate notebooks since they were run independently (e.g. `..._seed1` / `..._seed2`).
- `multi_dataset_benchmark/reckan_vs_baselines_main.ipynb` defines the shared model
  classes and the `main()` entry point used by the `run_*` notebooks in that same folder.
