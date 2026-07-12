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
