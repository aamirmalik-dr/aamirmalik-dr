# Aamir Malik

Data-Driven Materials Scientist (PhD, KAIST) working at the intersection of
machine learning and the physical sciences. My work spans the evaluation of
tool-using LLM agents, density-functional calculations, machine-learned
interatomic potentials, deep learning for electron microscopy, active
learning and uncertainty quantification, molecular representation learning,
generative models, quantitative finance, and classical statistics.

Two habits run through everything here. I build the core machinery from
scratch, periodic neighbor lists, message passing, backpropagation, attention,
Gaussian-process posteriors, and I benchmark every learned method against a
fair-tuned classical baseline. Each repository has an honest README, a
reproducible demo that was actually run, and only real measured results,
including the negative ones.

## Agentic AI and evaluation

- [evidence-ledger-agent](https://github.com/aamirmalik-dr/evidence-ledger-agent) ([v0.3.0](https://github.com/aamirmalik-dr/evidence-ledger-agent/releases/tag/v0.3.0)) - An evidence agent that checks narrow materials-science claims against a local corpus, binding every quote to a document hash and character offsets. With both models tested, one well-retrieved model call matched or beat the iterative agent at a fraction of the tokens.
- [agent-contract-bench](https://github.com/aamirmalik-dr/agent-contract-bench) ([v0.2.0](https://github.com/aamirmalik-dr/agent-contract-bench/releases/tag/v0.2.0)) - A harness for tool-using LLM agents under capability contracts, with fault and prompt injection, counting attempted, blocked and executed violations apart. One pre-registered prompt rule lifted completion from 5 to 17 of 20; a rule-based baseline still finished every task.
- [budgeted-discovery-agent](https://github.com/aamirmalik-dr/budgeted-discovery-agent) ([v0.2.0](https://github.com/aamirmalik-dr/budgeted-discovery-agent/releases/tag/v0.2.0)) - An LLM running budgeted, multi-fidelity screening campaigns on synthetic response surfaces, with every assay unit recorded as a receipt in a cost ledger. A single planning call and a tuned GP-UCB rule both beat the iterative agent, which mostly hit its token cap.
- [scientific-recovery-agent](https://github.com/aamirmalik-dr/scientific-recovery-agent) ([v0.2.0](https://github.com/aamirmalik-dr/scientific-recovery-agent/releases/tag/v0.2.0)) - An agent that diagnoses failed toy numerical runs and repairs them with allowlisted, approval-gated patches tested on a copy. It never beat a single model call: 15 against 16 of 20 with the smaller model, tied at 10 of 10 with a stronger one.
- [reproducible-experiment-agent](https://github.com/aamirmalik-dr/reproducible-experiment-agent) ([v0.2.0](https://github.com/aamirmalik-dr/reproducible-experiment-agent/releases/tag/v0.2.0)) - An experiment-planning agent for tabular ML with a pipeline allowlist, leakage traps, one-shot holdout scoring, and byte-identical reproduction of every frozen candidate. Both LLM planners beat a fixed pipeline and random search, but iterating added little over a single planning call.

## First-principles calculations and machine learning interatomic potentials

- [pd-hydrogen-diffusion-dft](https://github.com/aamirmalik-dr/pd-hydrogen-diffusion-dft) ([v0.3.0](https://github.com/aamirmalik-dr/pd-hydrogen-diffusion-dft/releases/tag/v0.3.0)) - Hydrogen diffusion in fcc palladium from CP-PAW density-functional calculations: a translation-invariant reaction coordinate, the octahedral-to-tetrahedral energy profile, and harmonic transition-state theory, with every input and protocol committed. The diffusion constant comes within a factor of seven of experiment, with its convergence limits stated plainly.
- [alloy-mlip-bench](https://github.com/aamirmalik-dr/alloy-mlip-bench) ([v0.1.1](https://github.com/aamirmalik-dr/alloy-mlip-bench/releases/tag/v0.1.1)) - Machine-learned potentials for BCC TiZrNb deployed as ASE calculators and benchmarked against CHGNet and MACE-MP-0 small on equation of state, elastic constants, RDFs, thermal expansion, and vacancy formation. The compact distilled model nearly matches its teacher at 14.6x the MD speed.
- [graph-neural-forcefield](https://github.com/aamirmalik-dr/graph-neural-forcefield) ([v0.1.1](https://github.com/aamirmalik-dr/graph-neural-forcefield/releases/tag/v0.1.1)) - A SchNet-style message-passing potential for TiZrNb, benchmarked head to head against a Behler-Parrinello descriptor network and a ridge baseline. The headline is data efficiency: it matches the linear baseline's full-data force accuracy with 102 of 882 training frames.
- [mlip-descriptor-potential](https://github.com/aamirmalik-dr/mlip-descriptor-potential) ([v0.1.1](https://github.com/aamirmalik-dr/mlip-descriptor-potential/releases/tag/v0.1.1)) - A Behler-Parrinello neural network potential from scratch in PyTorch: periodic neighbor lists, atom-centered symmetry functions, per-element networks, and autograd forces, benchmarked at matched budget against a tuned ridge model and a Morse pair potential with a leakage-safe group split.
- [forcefield-active-learning](https://github.com/aamirmalik-dr/forcefield-active-learning) ([v0.1.1](https://github.com/aamirmalik-dr/forcefield-active-learning/releases/tag/v0.1.1)) - Query-by-committee active learning for these potentials, against a random buyer at identical label budget. The honest headline is a measured negative: random selection wins on a well-mixed pool, while the same committee earns a 2.2x label saving on a redundancy-heavy one.

## Deep learning for electron microscopy

- [stem-atom-finder](https://github.com/aamirmalik-dr/stem-atom-finder) ([v0.2.1](https://github.com/aamirmalik-dr/stem-atom-finder/releases/tag/v0.2.1)) - Atomic column detection in simulated HAADF-STEM images: a Laplacian-of-Gaussian detector versus a compact U-Net across a 2000x electron dose range, with sub-pixel refinement and an oracle-tuned baseline as the fairness control.
- [active-learning-microscopy](https://github.com/aamirmalik-dr/active-learning-microscopy) ([v0.1.1](https://github.com/aamirmalik-dr/active-learning-microscopy/releases/tag/v0.1.1)) - A simulation study of the autonomous-experiment loop, asking when a Gaussian-process-steered probe beats a competent space-filling scan against exact ground truth, built on a from-scratch GP with sequential posterior updates and measured failure regimes.
- [stem-denoising-restoration](https://github.com/aamirmalik-dr/stem-denoising-restoration) ([v0.1.1](https://github.com/aamirmalik-dr/stem-denoising-restoration/releases/tag/v0.1.1)) - Restoration of low-dose electron microscope images, scored by image fidelity and by downstream atom detection: variance-stabilized classical denoisers versus a residual U-Net trained supervised and as self-supervised Noise2Noise, with off-distribution checks.
- [stem-defect-segmentation](https://github.com/aamirmalik-dr/stem-defect-segmentation) ([v0.1.1](https://github.com/aamirmalik-dr/stem-defect-segmentation/releases/tag/v0.1.1)) - Pixel-level segmentation of simulated STEM into five defect classes with exact ground truth: a threshold-and-morphology baseline and a random-forest pixel classifier versus a multi-class U-Net, scored on per-class IoU, Dice, and boundary error.
- [diffraction-structure-classifier](https://github.com/aamirmalik-dr/diffraction-structure-classifier) ([v0.1.1](https://github.com/aamirmalik-dr/diffraction-structure-classifier/releases/tag/v0.1.1)) - Crystal-structure classification from simulated electron diffraction: a tuned classical baseline versus 1D radial-profile and 2D rotation-invariant polar-Fourier CNNs, with a shortcut control measuring how much accuracy is material identity rather than structure.
- [eels-spectrum-unmixing](https://github.com/aamirmalik-dr/eels-spectrum-unmixing) ([v0.1.1](https://github.com/aamirmalik-dr/eels-spectrum-unmixing/releases/tag/v0.1.1)) - Unsupervised decomposition of simulated STEM-EELS spectrum images into endmember spectra and abundance maps: PCA, NMF, and a from-scratch VCA versus a constrained linear-unmixing autoencoder, across dose, energy-drift, and spectral-overlap sweeps.
- [4d-stem-orientation-mapping](https://github.com/aamirmalik-dr/4d-stem-orientation-mapping) ([v0.1.1](https://github.com/aamirmalik-dr/4d-stem-orientation-mapping/releases/tag/v0.1.1)) - Orientation and phase mapping from simulated 4D-STEM datacubes: template matching with sub-step refinement, a symmetry-aware CNN, and unsupervised grain clustering. The plainly reported negative result: fair-tuned template matching beats the CNN at every dose.

## Molecular representation learning and generative modeling

- [graph-neural-networks-for-molecules](https://github.com/aamirmalik-dr/graph-neural-networks-for-molecules) - Message passing neural networks (MPNN and GCN) for molecular property prediction, written from scratch in PyTorch with no graph-learning framework, benchmarked on public MoleculeNet ESOL with a message-passing depth ablation.
- [molecular-property-prediction](https://github.com/aamirmalik-dr/molecular-property-prediction) - A controlled comparison of three molecular representations for property prediction in PyTorch, a Morgan fingerprint MLP, a SMILES 1D-CNN, and a SMILES LSTM, trained on one shared codebase with RDKit-computed targets.
- [molecular-generative-models](https://github.com/aamirmalik-dr/molecular-generative-models) - A from-scratch SMILES GRU autoencoder and variational autoencoder in PyTorch with reparameterization and KL annealing, scored on the validity, uniqueness, and novelty of the molecules they generate.

## Quantitative finance and time series

- [neural-option-pricing](https://github.com/aamirmalik-dr/neural-option-pricing) - Classical option-pricing engines from scratch (Black-Scholes, binomial, Crank-Nicolson, variance-reduced Monte Carlo, Heston), plus a neural pricing surrogate and a CVaR-trained deep hedging policy, benchmarked honestly on simulated markets against tuned classical baselines that close much of the neural gap.
- [financial-forecasting-benchmarks](https://github.com/aamirmalik-dr/financial-forecasting-benchmarks) - A walk-forward benchmark of ML models against fair-tuned classical baselines for daily return and volatility forecasting on eight US ETFs over two decades. The defended null result: next-day returns are essentially unforecastable, and GARCH(1,1) beats LightGBM and an LSTM at volatility.
- [yield-curve-factor-analysis](https://github.com/aamirmalik-dr/yield-curve-factor-analysis) - PCA and NMF factor analysis of the US Treasury yield curve, recovering the classic level, slope, and curvature factors from public rates data, with a resilient, offline-capable data pipeline.
- [time-series-forecasting](https://github.com/aamirmalik-dr/time-series-forecasting) - Classical time-series forecasting end to end: STL decomposition into trend and seasonal components, ARIMA and SARIMAX models, and a walk-forward backtest reporting RMSE and MAPE.

## Foundations and applied deep learning

- [neural-network-from-scratch](https://github.com/aamirmalik-dr/neural-network-from-scratch) - A feedforward network in pure NumPy: backpropagation, SGD/Momentum/Adam, He and Xavier initialization, L2 and dropout, and numerical gradient checking as the correctness proof, demonstrated on a two-moons task.
- [classical-ml-from-scratch](https://github.com/aamirmalik-dr/classical-ml-from-scratch) - Linear and logistic regression, k-nearest neighbors, a CART decision tree, Gaussian naive Bayes, a kernel SVM, k-means, PCA, and Gaussian-mixture EM in NumPy, each unit-tested against scikit-learn.
- [gan-image-generation](https://github.com/aamirmalik-dr/gan-image-generation) - A DCGAN in PyTorch generating handwritten-digit images from random noise, with a clean adversarial training loop, generator and discriminator loss curves, and sample grids tracking output quality over training.
- [neural-machine-translation](https://github.com/aamirmalik-dr/neural-machine-translation) - A sequence-to-sequence translation model with Bahdanau attention, built from scratch in PyTorch and demonstrated on a date-normalization task with 100 percent exact-match accuracy and interpretable attention alignment maps.
- [adversarial-attacks](https://github.com/aamirmalik-dr/adversarial-attacks) - FGSM, iterative, and least-likely-class adversarial attacks on an MNIST image classifier in PyTorch, with robustness-versus-epsilon curves showing how accuracy degrades as the perturbation budget grows.
- [image-classification-pytorch](https://github.com/aamirmalik-dr/image-classification-pytorch) - A CIFAR-10 architecture study in PyTorch comparing an MLP, a plain CNN, and VGG-style and ResNet-style networks under one shared training budget, with a regularization ablation isolating what each technique contributes.
- [text-sentiment-lstm](https://github.com/aamirmalik-dr/text-sentiment-lstm) - A bidirectional LSTM sentiment classifier in PyTorch on public Rotten Tomatoes data, with a from-scratch tokenizer and vocabulary pipeline and optional pretrained GloVe embeddings in place of learned ones.
- [medical-image-classification](https://github.com/aamirmalik-dr/medical-image-classification) - Chest X-ray pneumonia screening on public MedMNIST data, comparing a from-scratch CNN with a transfer-learning ResNet-18 and reporting accuracy, recall, and ROC-AUC. A teaching example, not a clinical tool.

## Data science and statistics

- [tabular-ml-pipeline](https://github.com/aamirmalik-dr/tabular-ml-pipeline) - A reusable scikit-learn pipeline for messy tabular data: ColumnTransformer imputation and encoding, LASSO feature selection, and a tuned multi-model comparison, on the public UCI Adult dataset.
- [high-dimensional-genomics-ml](https://github.com/aamirmalik-dr/high-dimensional-genomics-ml) - PCA, clustering, and cross-validated classification on the public Golub leukemia gene-expression set, plus differential expression with a from-scratch Benjamini-Hochberg FDR correction.
- [temporal-network-analysis](https://github.com/aamirmalik-dr/temporal-network-analysis) - Per-phase structure and centrality trajectories in a time-varying network with networkx, validated on a synthetic role-planted graph, with an optional path to the public SNAP CollegeMsg dataset.
- [gaussian-process-flow-modeling](https://github.com/aamirmalik-dr/gaussian-process-flow-modeling) - Gaussian-process regression reconstructing a divergence-free 2D velocity field from sparse noisy samples, with RK4 particle advection and a calibrated uncertainty map. The uncertainty-quantification counterpart to the active-learning study.
- [statistical-methods-in-r](https://github.com/aamirmalik-dr/statistical-methods-in-r) - A collection of statistical analyses in base R: hypothesis testing, ANOVA, regression, PCA and factor analysis, and from-scratch association-rule mining, fully reproducible with no external packages.

## Skills and tools

- Languages: Python, R
- Frameworks and libraries: PyTorch, scikit-learn, NumPy, ASE, RDKit, statsmodels, networkx, pandas, Matplotlib, pydantic
- Simulation codes: CP-PAW (density-functional theory, projector augmented wave method)
- Learned methods: message passing neural networks, interatomic potentials with autograd forces, U-Net segmentation, CNNs, LSTMs, sequence-to-sequence with attention, variational autoencoders, GANs
- Statistical methods: Gaussian-process regression, active learning, PCA/NMF/VCA decompositions, ARIMA/SARIMAX and GARCH modeling, walk-forward evaluation with Diebold-Mariano tests and block bootstrap, multiple-testing control with Benjamini-Hochberg FDR
- LLM agents and evaluation: tool-calling loops with typed tool schemas and policy gates, checkpointed resumable episodes, pre-registered held-out evaluation, paired task-level bootstrap intervals

## Contact

- GitHub: [aamirmalik-dr](https://github.com/aamirmalik-dr)
- LinkedIn: [aamirmalik-dr](https://www.linkedin.com/in/aamirmalik-dr)
