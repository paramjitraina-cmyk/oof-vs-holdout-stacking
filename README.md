# Fixed Hold-Out versus Out-of-Fold Meta-Learning

This repository contains the reproducibility artifacts for the matched
cross-domain comparison of fixed hold-out and five-fold out-of-fold stacking
protocols on CIFAR-10 and chest CT classification.

## Repository structure

- `artifacts/cifar10/`
  - saved OOF probabilities
  - fixed hold-out probabilities
  - test probabilities
  - fold identifiers
  - split indices
  - development, hold-out and test labels
  - combined meta-feature matrices
  - archived and regenerated result tables
  - saved meta-learner predictions and models

- `artifacts/ct/`
  - saved OOF probabilities
  - fixed hold-out probabilities
  - test probabilities
  - fold identifiers
  - split indices and labels
  - combined meta-feature matrices
  - archived and regenerated result tables
  - saved meta-learner predictions and models

- `notebooks/`
  - cleaned experiment and statistical-analysis notebooks

- `SHA256SUMS.csv`
  - SHA-256 checksum and file size for each repository artifact

## Verified matrix dimensions

### CIFAR-10

- OOF meta-features: `(50000, 40)`
- fixed hold-out meta-features: `(10000, 40)`
- test meta-features: `(10000, 40)`
- development labels: `(50000,)`
- test labels: `(10000,)`

### CT

- OOF meta-features: `(1984, 4)`
- fixed hold-out meta-features: `(397, 4)`
- test meta-features: `(497, 4)`
- development labels: `(1984,)`
- test labels: `(497,)`

## Reproduction notes

The reconstructed CIFAR-10 OOF, test and fixed hold-out meta-feature matrices
were byte-for-byte identical to the archived corrected matrices, including
matching SHA-256 checksums.

For both datasets, soft voting and Logistic Regression reproduced the archived
accuracy results exactly. Regenerated LightGBM outputs showed small differences
from the archived primary results under the current software environment.

For CIFAR-10, fixed hold-out LightGBM changed by 14 predictions and OOF
LightGBM changed by 13 predictions out of 10,000 test cases.

For CT, regenerated OOF LightGBM differed from the archived result by one
prediction out of 497 test cases.

The archived result tables are retained as the manuscript-authoritative
outputs. Regenerated results and direct comparison tables are included
separately for transparency.

## Data availability

Raw chest CT images are not redistributed. The repository includes derived
probability matrices, labels, split identifiers, meta-features, predictions,
statistical outputs and analysis code needed to reproduce the stacking and
evaluation stages.
