# Cube Letter ML Model

A compact experimental project for learning and visualizing cube-face letter assignments from structured text descriptions.

This repository presents a small neural prototype that maps visible cube faces (`front`, `right`, `top`) to the expected ordered letter triplet and compares an incorrect visualization against a corrected one. It is documented in a clean research-style format for clarity, reproducibility, and further iteration.

---

## Project Overview

The goal of this project is to test whether a lightweight neural model can learn a simple symbolic mapping between a cube description and the correct face-letter output.

Each sample follows the format:

- Input: `front=A, right=B, top=C`
- Output: `ABC`

The same structure is repeated for six cubes:

1. `A, B, C`
2. `D, E, F`
3. `G, H, I`
4. `J, K, L`
5. `M, N, O`
6. `P, Q, R`

The model is intentionally small and easy to inspect. The project emphasizes:

- clear data preparation,
- transparent model definition,
- readable training logs,
- visual comparison of incorrect vs corrected outputs,
- clean documentation for reproducibility.

---

## Repository Structure

- `README.md` — main project overview
- `data_preparation.md` — dataset format and preprocessing notes
- `model_training.md` — model architecture and training description
- `training_logs.md` — logs and metrics summary
- `execution_guide.md` — step-by-step run instructions
- `Predicted Cube Face Labels in 2x3 Grid.png` — corrected visualization
- `Incorrect Cube Face Prediction with Labeling Errors.png` — incorrect visualization for comparison

---

## Method

### 1. Data Representation
The dataset consists of structured text descriptions of cube faces and their expected ordered output labels.  
Each example is converted into indexed character tokens using a simple character-level vocabulary.

### 2. Model
The model is a minimal PyTorch network composed of:

- an embedding layer,
- mean aggregation over the input sequence,
- one linear projection layer producing the output sequence.

This architecture was chosen to keep the prototype small, interpretable, and fast to train.

### 3. Training
The model is trained using:

- **Optimizer:** Adam
- **Loss:** CrossEntropyLoss
- **Epochs:** 200

Loss values are printed during training to make optimization progress visible.

### 4. Evaluation
After training, the model is tested on the defined cube descriptions and returns the predicted 3-letter output for each case.

---

## Visual Results

## Corrected Visualization

**Predicted Cube Face Labels in 2x3 Grid**

This figure shows the corrected cube-face layout in a 2x3 grid.  
Each cube contains three distinct visible labels corresponding to the `front`, `right`, and `top` faces.  
This version reflects the intended structured mapping and serves as the clean reference visualization.

![Corrected cube visualization](./Predicted%20Cube%20Face%20Labels%20in%202x3%20Grid.png)

---

## Incorrect Visualization

**Incorrect Cube Face Prediction with Labeling Errors**

This figure shows an incorrect visualization containing label assignment errors.  
Some cubes contain repeated or misplaced letters, which makes the arrangement inconsistent with the intended mapping.  
It is included to document the failure case and clearly contrast it with the corrected version.

![Incorrect cube visualization](./Incorrect%20Cube%20Face%20Prediction%20with%20Labeling%20Errors.png)

---

## Why This Repository Exists

This repository is meant as a compact experimental showcase:

- to demonstrate a symbolic cube-label mapping task,
- to document a tiny neural baseline,
- to present both incorrect and corrected visual outputs,
- to provide a clean base for future improvements.

It can also serve as a small reference project for anyone exploring:
- symbolic-to-structured prediction,
- lightweight PyTorch experiments,
- visual verification of model outputs.

---

## Reproducibility

The project is split into separate markdown files so each part can be inspected quickly:

- dataset and preprocessing,
- model and training,
- logs and metrics,
- execution instructions.

This structure is designed to make the experiment easier to understand and extend.

---

## Notes

This repository is a documented prototype and visual experiment.  
If adapted into a formal challenge submission, it should be restructured to match the exact submission requirements of the target benchmark, including the required folder layout, metadata files, logs, and executable training script.

---

## Author

**Terraforming-Planet**

Focused on compact AI experimentation, structured reasoning tasks, and interpretable technical prototypes.
