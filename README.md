# Aamir Malik

Computational materials scientist (PhD, KAIST) working at the intersection of
machine learning and the physical sciences. I build models for molecules and
materials, and I like understanding methods well enough to implement them from
scratch. The repositories below are original work: each one has an honest README,
a reproducible demo that was actually run, and only real measured results.

A recurring theme across these projects is building the core machinery directly
rather than calling a high-level wrapper, from message passing on molecular
graphs to backpropagation, attention, and a false-discovery-rate correction.

## Molecules and materials ML

- [graph-neural-networks-for-molecules](https://github.com/aamirmalik-dr/graph-neural-networks-for-molecules) - Message passing neural networks (MPNN and GCN) for molecular property prediction, written from scratch in PyTorch with no graph-learning framework. Benchmarked on public MoleculeNet ESOL.
- [molecular-property-prediction](https://github.com/aamirmalik-dr/molecular-property-prediction) - A controlled comparison of three molecular representations (Morgan fingerprints, SMILES CNN, SMILES RNN) on one codebase, with RDKit-computed targets.
- [molecular-generative-models](https://github.com/aamirmalik-dr/molecular-generative-models) - A SMILES autoencoder and variational autoencoder with reparameterization and KL annealing, scored on validity, uniqueness, and novelty.
- [stem-atom-finder](https://github.com/aamirmalik-dr/stem-atom-finder) - Atomic column detection in simulated scanning transmission electron microscope images: a Laplacian-of-Gaussian detector versus a compact U-Net across a 2000x electron dose range, with an oracle-tuned baseline as the fairness control.
- [stem-denoising-restoration](https://github.com/aamirmalik-dr/stem-denoising-restoration) - Restoration of low-dose electron microscope images, scored by image fidelity and by downstream atom detection against exact ground truth. Variance-stabilized classical denoisers versus a residual U-Net trained supervised and as self-supervised Noise2Noise, with fair-tuning, cross-dose, and off-distribution geometry checks that map where the learned advantage ends.
- [stem-defect-segmentation](https://github.com/aamirmalik-dr/stem-defect-segmentation) - Pixel-level segmentation of point defects and local structure in simulated STEM into five classes (background, lattice, vacancy, dopant, disordered), with exact per-pixel ground truth. A threshold-and-morphology baseline and a random-forest pixel classifier versus a multi-class U-Net, scored on per-class IoU and Dice plus a boundary-localization error, with a class-imbalance analysis and an oracle-tuning fairness check showing where the U-Net recovers rare classes that a local method cannot.
- [diffraction-structure-classifier](https://github.com/aamirmalik-dr/diffraction-structure-classifier) - Crystal structure classification from simulated kinematical electron diffraction patterns, comparing a tuned classical baseline, a 1D radial-profile CNN, and a 2D rotation-invariant polar-Fourier CNN with confidence intervals and paired significance tests. Systematic absences derived from first-principles structure factors, and a shortcut control that measures how much accuracy is material identity rather than structure-type geometry.
- [eels-spectrum-unmixing](https://github.com/aamirmalik-dr/eels-spectrum-unmixing) - Unsupervised decomposition of simulated STEM-EELS spectrum images into endmember spectra and abundance maps, scored against exact ground truth. PCA, NMF, and a from-scratch VCA versus a constrained linear-unmixing autoencoder across dose, energy-drift, and spectral-overlap sweeps, with a fair-tuning audit of the baseline and a seed-stability analysis showing which failure modes reconstruction error can and cannot detect.

## Deep learning and classical ML from scratch

- [neural-network-from-scratch](https://github.com/aamirmalik-dr/neural-network-from-scratch) - A feedforward network in pure NumPy: backpropagation, SGD/Momentum/Adam, He and Xavier initialization, L2 and dropout, and numerical gradient checking, demonstrated on a two-moons classification task with the gradient check as the correctness proof.
- [classical-ml-from-scratch](https://github.com/aamirmalik-dr/classical-ml-from-scratch) - Linear and logistic regression, k-nearest neighbors, a CART decision tree, Gaussian naive Bayes, a kernel SVM, k-means, PCA, and Gaussian-mixture EM in NumPy, each validated against scikit-learn.

## Computer vision

- [image-classification-pytorch](https://github.com/aamirmalik-dr/image-classification-pytorch) - A CIFAR-10 architecture study (MLP, CNN, VGG-style, ResNet-style) with a regularization ablation.
- [medical-image-classification](https://github.com/aamirmalik-dr/medical-image-classification) - Chest X-ray pneumonia screening on the public MedMNIST PneumoniaMNIST dataset, comparing a from-scratch CNN with a transfer-learning ResNet-18 and reporting sensitivity and specificity. A teaching example, not a clinical tool.
- [gan-image-generation](https://github.com/aamirmalik-dr/gan-image-generation) - A DCGAN generating handwritten digits, with a clean training loop and sample grids.
- [adversarial-attacks](https://github.com/aamirmalik-dr/adversarial-attacks) - FGSM, iterative, and least-likely-class attacks on an image classifier, with robustness-versus-epsilon curves.

## Natural language processing

- [text-sentiment-lstm](https://github.com/aamirmalik-dr/text-sentiment-lstm) - A bidirectional LSTM sentiment classifier with a from-scratch tokenizer and optional GloVe embeddings, on public Rotten Tomatoes data.
- [neural-machine-translation](https://github.com/aamirmalik-dr/neural-machine-translation) - A sequence-to-sequence model with Bahdanau attention, built from scratch, with interpretable attention alignments.

## ML for finance

- [yield-curve-factor-analysis](https://github.com/aamirmalik-dr/yield-curve-factor-analysis) - PCA and NMF of the US Treasury yield curve, recovering the classic level, slope, and curvature factors from live data.
- [time-series-forecasting](https://github.com/aamirmalik-dr/time-series-forecasting) - ARIMA and SARIMAX forecasting with a walk-forward backtest on public macro and environmental series.

## Statistics, methodology, and scientific ML

- [high-dimensional-genomics-ml](https://github.com/aamirmalik-dr/high-dimensional-genomics-ml) - PCA, clustering, and classification on gene-expression data, plus differential expression with a from-scratch Benjamini-Hochberg FDR correction.
- [tabular-ml-pipeline](https://github.com/aamirmalik-dr/tabular-ml-pipeline) - A reusable scikit-learn pipeline for messy tabular data: imputation, encoding, LASSO selection, and a tuned multi-model comparison.
- [gaussian-process-flow-modeling](https://github.com/aamirmalik-dr/gaussian-process-flow-modeling) - Gaussian process reconstruction of a divergence-free velocity field from sparse samples, with particle advection and an uncertainty map.
- [temporal-network-analysis](https://github.com/aamirmalik-dr/temporal-network-analysis) - Centrality trajectories and emergent-actor detection in a time-varying network, validated on a synthetic role-planted graph, with an optional path to a public temporal network.
- [statistical-methods-in-r](https://github.com/aamirmalik-dr/statistical-methods-in-r) - Hypothesis testing, ANOVA, regression, PCA and factor analysis, and association-rule mining in base R.

## Contact

- GitHub: [aamirmalik-dr](https://github.com/aamirmalik-dr)
- LinkedIn: [dr-aamirmalik](https://linkedin.com/in/dr-aamirmalik)
