# Aamir Malik

Computational materials scientist (PhD, KAIST) working at the intersection of
machine learning and the physical sciences. My work spans molecular
representation learning, deep learning for electron microscopy, active learning
and uncertainty quantification, generative models, and classical statistics.
A consistent thread is building the core machinery from scratch, message passing
on molecular graphs, backpropagation, attention, Gaussian-process posteriors, and
a false-discovery-rate correction, and pairing every learned method against a
fair-tuned baseline. Each repository below has an honest README, a reproducible
demo that was actually run, and only real measured results, including the negative
ones.

## Molecular representation learning and generative modeling

- [graph-neural-networks-for-molecules](https://github.com/aamirmalik-dr/graph-neural-networks-for-molecules) - Message passing neural networks (MPNN and GCN) for molecular property prediction, written from scratch in PyTorch with no graph-learning framework, benchmarked on public MoleculeNet ESOL with a message-passing depth ablation.
- [molecular-property-prediction](https://github.com/aamirmalik-dr/molecular-property-prediction) - A controlled comparison of three molecular representations, Morgan fingerprint MLP, SMILES 1D-CNN, and SMILES LSTM, on one codebase, with RDKit-computed targets.
- [molecular-generative-models](https://github.com/aamirmalik-dr/molecular-generative-models) - A from-scratch SMILES GRU autoencoder and variational autoencoder with reparameterization and KL annealing, scored on validity, uniqueness, and novelty.

## Deep learning for electron microscopy imaging

- [stem-atom-finder](https://github.com/aamirmalik-dr/stem-atom-finder) - Atomic column detection in simulated HAADF-STEM images: a Laplacian-of-Gaussian detector versus a compact U-Net across a 2000x electron dose range, with sub-pixel refinement and an oracle-tuned baseline as the fairness control.
- [stem-denoising-restoration](https://github.com/aamirmalik-dr/stem-denoising-restoration) - Restoration of low-dose electron microscope images, scored by image fidelity and by downstream atom detection against exact ground truth. Variance-stabilized classical denoisers versus a residual U-Net trained supervised and as self-supervised Noise2Noise, with fair-tuning and off-distribution checks that map where the learned advantage ends.
- [stem-defect-segmentation](https://github.com/aamirmalik-dr/stem-defect-segmentation) - Pixel-level segmentation of simulated STEM into five classes (background, lattice, vacancy, dopant, disordered) with exact per-pixel ground truth. A threshold-and-morphology baseline and a random-forest pixel classifier versus a multi-class U-Net, scored on per-class IoU and Dice plus a boundary-localization error, with a class-imbalance analysis.

## Machine learning for diffraction and spectroscopy

- [diffraction-structure-classifier](https://github.com/aamirmalik-dr/diffraction-structure-classifier) - Crystal-structure classification from simulated kinematical electron diffraction, comparing a tuned classical baseline, a 1D radial-profile CNN, and a 2D rotation-invariant polar-Fourier CNN, with confidence intervals, paired significance tests, and a shortcut control that measures how much accuracy is material identity rather than structure-type geometry.
- [eels-spectrum-unmixing](https://github.com/aamirmalik-dr/eels-spectrum-unmixing) - Unsupervised decomposition of simulated STEM-EELS spectrum images into endmember spectra and abundance maps, scored against exact ground truth. PCA, NMF, and a from-scratch VCA versus a constrained linear-unmixing autoencoder across dose, energy-drift, and spectral-overlap sweeps, with a fair-tuning audit of the baseline.
- [4d-stem-orientation-mapping](https://github.com/aamirmalik-dr/4d-stem-orientation-mapping) - Orientation and phase mapping from simulated 4D-STEM datacubes: virtual imaging, template matching with sub-step refinement, a symmetry-aware CNN, and unsupervised grain clustering against exact ground truth. The headline is a negative result reported plainly: fair-tuned template matching beats the CNN at every dose on in-model data, and a forward-model-mismatch benchmark measures where that gap nearly closes.

## Active learning and uncertainty quantification

- [active-learning-microscopy](https://github.com/aamirmalik-dr/active-learning-microscopy) - A simulation study of the autonomous-experiment loop: when does a Gaussian-process-steered probe beat a competent space-filling scan at mapping a property field or finding rare defects, scored against exact ground truth. A from-scratch GP with exact rank-one sequential posterior updates and expected-exceedance defect hunting, with measured failure regimes reported plainly, including where a misspecified surrogate makes active sampling the worst strategy in the comparison.
- [gaussian-process-flow-modeling](https://github.com/aamirmalik-dr/gaussian-process-flow-modeling) - Gaussian-process regression reconstructing a divergence-free 2D velocity field from sparse noisy samples, with RK4 particle advection and a calibrated uncertainty map. This is the uncertainty-quantification counterpart to the active-learning study, GP posteriors without an acquisition loop.

## Computer vision: classification, generation, and adversarial robustness

- [image-classification-pytorch](https://github.com/aamirmalik-dr/image-classification-pytorch) - A CIFAR-10 architecture study (MLP, CNN, VGG-style, ResNet-style) compared under one training budget, with a regularization ablation.
- [medical-image-classification](https://github.com/aamirmalik-dr/medical-image-classification) - Chest X-ray pneumonia screening on the public MedMNIST PneumoniaMNIST dataset, comparing a from-scratch CNN with a transfer-learning ResNet-18 and reporting accuracy, recall, and ROC-AUC. A teaching example, not a clinical tool.
- [gan-image-generation](https://github.com/aamirmalik-dr/gan-image-generation) - A DCGAN generating handwritten digits from noise, with a clean training loop, sample grids, and training-loss curves.
- [adversarial-attacks](https://github.com/aamirmalik-dr/adversarial-attacks) - FGSM, iterative, and least-likely-class attacks on an image classifier, with robustness-versus-epsilon curves on MNIST.

## Sequence modeling and NLP

- [text-sentiment-lstm](https://github.com/aamirmalik-dr/text-sentiment-lstm) - A bidirectional LSTM sentiment classifier in PyTorch with a from-scratch tokenizer and optional GloVe embeddings, on public Rotten Tomatoes data.
- [neural-machine-translation](https://github.com/aamirmalik-dr/neural-machine-translation) - A sequence-to-sequence model with Bahdanau attention, built from scratch in PyTorch, demonstrated on a date-normalization task with interpretable attention alignments.

## Time series and quantitative finance

- [yield-curve-factor-analysis](https://github.com/aamirmalik-dr/yield-curve-factor-analysis) - PCA and NMF of the US Treasury yield curve, recovering the classic level, slope, and curvature factors, with a resilient offline-capable data pipeline.
- [time-series-forecasting](https://github.com/aamirmalik-dr/time-series-forecasting) - STL decomposition and ARIMA/SARIMAX forecasting with a walk-forward backtest reporting RMSE and MAPE.

## Neural networks and classical ML from scratch

- [neural-network-from-scratch](https://github.com/aamirmalik-dr/neural-network-from-scratch) - A feedforward network in pure NumPy: backpropagation, SGD/Momentum/Adam, He and Xavier initialization, L2 and dropout, and numerical gradient checking as the correctness proof, demonstrated on a two-moons task.
- [classical-ml-from-scratch](https://github.com/aamirmalik-dr/classical-ml-from-scratch) - Linear and logistic regression, k-nearest neighbors, a CART decision tree, Gaussian naive Bayes, a kernel SVM, k-means, PCA, and Gaussian-mixture EM in NumPy, each unit-tested against scikit-learn.

## Statistical and probabilistic modeling

- [high-dimensional-genomics-ml](https://github.com/aamirmalik-dr/high-dimensional-genomics-ml) - PCA, clustering, and cross-validated classification on the public Golub leukemia gene-expression set, plus differential expression with a from-scratch Benjamini-Hochberg FDR correction.
- [tabular-ml-pipeline](https://github.com/aamirmalik-dr/tabular-ml-pipeline) - A reusable scikit-learn pipeline for messy tabular data: ColumnTransformer imputation and encoding, LASSO feature selection, and a tuned multi-model comparison, on the public UCI Adult dataset.
- [temporal-network-analysis](https://github.com/aamirmalik-dr/temporal-network-analysis) - Per-phase structure and degree, betweenness, and eigenvector centrality trajectories in a time-varying network with networkx, validated on a synthetic role-planted graph, with an optional path to the public SNAP CollegeMsg dataset.
- [statistical-methods-in-r](https://github.com/aamirmalik-dr/statistical-methods-in-r) - Hypothesis testing, ANOVA, regression, PCA and factor analysis, and from-scratch association-rule mining, all in base R with no external packages.

## Skills and tools

- Languages: Python, R
- Frameworks and libraries: PyTorch, scikit-learn, NumPy, RDKit, statsmodels, networkx, pandas, Matplotlib
- Methods: message passing neural networks, variational autoencoders, GANs, U-Net semantic segmentation, CNNs, LSTMs, sequence-to-sequence with attention, Gaussian-process regression, active learning, PCA/NMF/VCA and other unsupervised decompositions, ARIMA/SARIMAX time-series forecasting, backpropagation and optimizers from scratch, Benjamini-Hochberg FDR correction and multiple-testing control

## Contact

- GitHub: [aamirmalik-dr](https://github.com/aamirmalik-dr)
- LinkedIn: [aamirmalik-dr](https://www.linkedin.com/in/aamirmalik-dr)
