# Aamir Malik

Data-Driven Materials Scientist (PhD, KAIST) working at the intersection of
machine learning and the physical sciences. My work spans machine-learned
interatomic potentials, molecular representation learning, deep learning for
electron microscopy, active learning and uncertainty quantification,
quantitative finance, generative models, and classical statistics.

Two habits run through everything here. I build the core machinery from
scratch, periodic neighbor lists, message passing, backpropagation, attention,
Gaussian-process posteriors, and I benchmark every learned method against a
fair-tuned classical baseline. Each repository has an honest README, a
reproducible demo that was actually run, and only real measured results,
including the negative ones.

## Machine learning interatomic potentials

- [mlip-descriptor-potential](https://github.com/aamirmalik-dr/mlip-descriptor-potential) - A Behler-Parrinello neural network potential from scratch in PyTorch: periodic neighbor lists, atom-centered symmetry functions, per-element networks, and autograd forces, benchmarked at matched budget against a tuned ridge model and a Morse pair potential with a leakage-safe group split.
- [graph-neural-forcefield](https://github.com/aamirmalik-dr/graph-neural-forcefield) - A SchNet-style message-passing potential on the same chemistry, benchmarked head to head against the descriptor network and the ridge baseline. The headline is data efficiency: it matches the linear baseline's full-data force accuracy with 102 of 882 training frames.
- [alloy-mlip-bench](https://github.com/aamirmalik-dr/alloy-mlip-bench) - The potentials deployed as ASE calculators and benchmarked against CHGNet and MACE-MP-0 small on equation of state, elastic constants, RDFs, thermal expansion, and vacancy formation. The compact distilled model nearly matches its teacher at 14.6x the MD speed.
- [forcefield-active-learning](https://github.com/aamirmalik-dr/forcefield-active-learning) - Query-by-committee active learning for these potentials, against a random buyer at identical label budget. The honest headline is a measured negative: random selection wins on a well-mixed pool, while the same committee earns a 2.2x label saving on a redundancy-heavy one.

## Molecular representation learning and generative modeling

- [graph-neural-networks-for-molecules](https://github.com/aamirmalik-dr/graph-neural-networks-for-molecules) - Message passing neural networks (MPNN and GCN) for molecular property prediction, written from scratch in PyTorch with no graph-learning framework, benchmarked on public MoleculeNet ESOL with a message-passing depth ablation.
- [molecular-property-prediction](https://github.com/aamirmalik-dr/molecular-property-prediction) - A controlled comparison of three molecular representations for property prediction in PyTorch, a Morgan fingerprint MLP, a SMILES 1D-CNN, and a SMILES LSTM, trained on one shared codebase with RDKit-computed targets.
- [molecular-generative-models](https://github.com/aamirmalik-dr/molecular-generative-models) - A from-scratch SMILES GRU autoencoder and variational autoencoder in PyTorch with reparameterization and KL annealing, scored on the validity, uniqueness, and novelty of the molecules they generate.

## Deep learning for electron microscopy imaging

- [stem-atom-finder](https://github.com/aamirmalik-dr/stem-atom-finder) - Atomic column detection in simulated HAADF-STEM images: a Laplacian-of-Gaussian detector versus a compact U-Net across a 2000x electron dose range, with sub-pixel refinement and an oracle-tuned baseline as the fairness control.
- [stem-denoising-restoration](https://github.com/aamirmalik-dr/stem-denoising-restoration) - Restoration of low-dose electron microscope images, scored by image fidelity and by downstream atom detection: variance-stabilized classical denoisers versus a residual U-Net trained supervised and as self-supervised Noise2Noise, with off-distribution checks.
- [stem-defect-segmentation](https://github.com/aamirmalik-dr/stem-defect-segmentation) - Pixel-level segmentation of simulated STEM into five defect classes with exact ground truth: a threshold-and-morphology baseline and a random-forest pixel classifier versus a multi-class U-Net, scored on per-class IoU, Dice, and boundary error.

## Machine learning for diffraction and spectroscopy

- [diffraction-structure-classifier](https://github.com/aamirmalik-dr/diffraction-structure-classifier) - Crystal-structure classification from simulated electron diffraction: a tuned classical baseline versus 1D radial-profile and 2D rotation-invariant polar-Fourier CNNs, with a shortcut control measuring how much accuracy is material identity rather than structure.
- [eels-spectrum-unmixing](https://github.com/aamirmalik-dr/eels-spectrum-unmixing) - Unsupervised decomposition of simulated STEM-EELS spectrum images into endmember spectra and abundance maps: PCA, NMF, and a from-scratch VCA versus a constrained linear-unmixing autoencoder, across dose, energy-drift, and spectral-overlap sweeps.
- [4d-stem-orientation-mapping](https://github.com/aamirmalik-dr/4d-stem-orientation-mapping) - Orientation and phase mapping from simulated 4D-STEM datacubes: template matching with sub-step refinement, a symmetry-aware CNN, and unsupervised grain clustering. The plainly reported negative result: fair-tuned template matching beats the CNN at every dose.

## Active learning and uncertainty quantification

- [active-learning-microscopy](https://github.com/aamirmalik-dr/active-learning-microscopy) - A simulation study of the autonomous-experiment loop, asking when a Gaussian-process-steered probe beats a competent space-filling scan against exact ground truth, built on a from-scratch GP with sequential posterior updates and measured failure regimes.
- [gaussian-process-flow-modeling](https://github.com/aamirmalik-dr/gaussian-process-flow-modeling) - Gaussian-process regression reconstructing a divergence-free 2D velocity field from sparse noisy samples, with RK4 particle advection and a calibrated uncertainty map. The uncertainty-quantification counterpart to the active-learning study.

## Computer vision: classification, generation, and adversarial robustness

- [image-classification-pytorch](https://github.com/aamirmalik-dr/image-classification-pytorch) - A CIFAR-10 architecture study in PyTorch comparing an MLP, a plain CNN, and VGG-style and ResNet-style networks under one shared training budget, with a regularization ablation isolating what each technique contributes.
- [medical-image-classification](https://github.com/aamirmalik-dr/medical-image-classification) - Chest X-ray pneumonia screening on public MedMNIST data, comparing a from-scratch CNN with a transfer-learning ResNet-18 and reporting accuracy, recall, and ROC-AUC. A teaching example, not a clinical tool.
- [gan-image-generation](https://github.com/aamirmalik-dr/gan-image-generation) - A DCGAN in PyTorch generating handwritten-digit images from random noise, with a clean adversarial training loop, generator and discriminator loss curves, and sample grids tracking output quality over training.
- [adversarial-attacks](https://github.com/aamirmalik-dr/adversarial-attacks) - FGSM, iterative, and least-likely-class adversarial attacks on an MNIST image classifier in PyTorch, with robustness-versus-epsilon curves showing how accuracy degrades as the perturbation budget grows.

## Sequence modeling and NLP

- [text-sentiment-lstm](https://github.com/aamirmalik-dr/text-sentiment-lstm) - A bidirectional LSTM sentiment classifier in PyTorch on public Rotten Tomatoes data, with a from-scratch tokenizer and vocabulary pipeline and optional pretrained GloVe embeddings in place of learned ones.
- [neural-machine-translation](https://github.com/aamirmalik-dr/neural-machine-translation) - A sequence-to-sequence translation model with Bahdanau attention, built from scratch in PyTorch and demonstrated on a date-normalization task with 100 percent exact-match accuracy and interpretable attention alignment maps.

## Quantitative finance and time series

- [neural-option-pricing](https://github.com/aamirmalik-dr/neural-option-pricing) - Classical option-pricing engines from scratch (Black-Scholes, binomial, Crank-Nicolson, variance-reduced Monte Carlo, Heston), plus a neural pricing surrogate and a CVaR-trained deep hedging policy, benchmarked honestly on simulated markets against tuned classical baselines that close much of the neural gap.
- [financial-forecasting-benchmarks](https://github.com/aamirmalik-dr/financial-forecasting-benchmarks) - A walk-forward benchmark of ML models against fair-tuned classical baselines for daily return and volatility forecasting on eight US ETFs over two decades. The defended null result: next-day returns are essentially unforecastable, and GARCH(1,1) beats LightGBM and an LSTM at volatility.
- [yield-curve-factor-analysis](https://github.com/aamirmalik-dr/yield-curve-factor-analysis) - PCA and NMF factor analysis of the US Treasury yield curve, recovering the classic level, slope, and curvature factors from public rates data, with a resilient, offline-capable data pipeline.
- [time-series-forecasting](https://github.com/aamirmalik-dr/time-series-forecasting) - Classical time-series forecasting end to end: STL decomposition into trend and seasonal components, ARIMA and SARIMAX models, and a walk-forward backtest reporting RMSE and MAPE.

## Neural networks and classical ML from scratch

- [neural-network-from-scratch](https://github.com/aamirmalik-dr/neural-network-from-scratch) - A feedforward network in pure NumPy: backpropagation, SGD/Momentum/Adam, He and Xavier initialization, L2 and dropout, and numerical gradient checking as the correctness proof, demonstrated on a two-moons task.
- [classical-ml-from-scratch](https://github.com/aamirmalik-dr/classical-ml-from-scratch) - Linear and logistic regression, k-nearest neighbors, a CART decision tree, Gaussian naive Bayes, a kernel SVM, k-means, PCA, and Gaussian-mixture EM in NumPy, each unit-tested against scikit-learn.

## Statistical and probabilistic modeling

- [high-dimensional-genomics-ml](https://github.com/aamirmalik-dr/high-dimensional-genomics-ml) - PCA, clustering, and cross-validated classification on the public Golub leukemia gene-expression set, plus differential expression with a from-scratch Benjamini-Hochberg FDR correction.
- [tabular-ml-pipeline](https://github.com/aamirmalik-dr/tabular-ml-pipeline) - A reusable scikit-learn pipeline for messy tabular data: ColumnTransformer imputation and encoding, LASSO feature selection, and a tuned multi-model comparison, on the public UCI Adult dataset.
- [temporal-network-analysis](https://github.com/aamirmalik-dr/temporal-network-analysis) - Per-phase structure and centrality trajectories in a time-varying network with networkx, validated on a synthetic role-planted graph, with an optional path to the public SNAP CollegeMsg dataset.
- [statistical-methods-in-r](https://github.com/aamirmalik-dr/statistical-methods-in-r) - A collection of statistical analyses in base R: hypothesis testing, ANOVA, regression, PCA and factor analysis, and from-scratch association-rule mining, fully reproducible with no external packages.

## Skills and tools

- Languages: Python, R
- Frameworks and libraries: PyTorch, scikit-learn, NumPy, ASE, RDKit, statsmodels, networkx, pandas, Matplotlib
- Learned methods: message passing neural networks, interatomic potentials with autograd forces, U-Net segmentation, CNNs, LSTMs, sequence-to-sequence with attention, variational autoencoders, GANs
- Statistical methods: Gaussian-process regression, active learning, PCA/NMF/VCA decompositions, ARIMA/SARIMAX and GARCH modeling, walk-forward evaluation with Diebold-Mariano tests and block bootstrap, multiple-testing control with Benjamini-Hochberg FDR

## Contact

- GitHub: [aamirmalik-dr](https://github.com/aamirmalik-dr)
- LinkedIn: [aamirmalik-dr](https://www.linkedin.com/in/aamirmalik-dr)
