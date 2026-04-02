# 🧊 Cube Letter ML Model

A compact neural network experiment for learning structured cube-face labeling from textual descriptions, with full training pipeline and visual validation.

---

## 🚀 Overview

This project demonstrates how a lightweight neural network can learn a symbolic mapping between structured cube descriptions and their corresponding face labels.

Each cube is described using:

```
front=A, right=B, top=C
```

The model predicts:

```
ABC
```

This mapping is learned for multiple cube instances and later visualized in a 3D-style layout.

---

## 🧠 Key Features

- Character-level encoding of structured inputs  
- Minimal PyTorch model (embedding + linear layer)  
- Full training pipeline implemented in Google Colab  
- Accurate prediction of cube face labels  
- 2D isometric visualization of 3D cubes  
- Comparison between incorrect and corrected outputs  

---

## 📓 Training Notebook

The full training process is implemented in:

👉 **cube_face_labeling_3d_model.ipynb**

This notebook includes:

- data preparation and encoding  
- model definition (`TinyModel`)  
- training loop (Adam + CrossEntropyLoss)  
- prediction testing  
- cube visualization using Matplotlib  

The model learns mappings like:

```
front=A, right=B, top=C → ABC
front=G, right=H, top=I → GHI
```

---

## 🏗 Model Architecture

The model is intentionally simple:

- Embedding layer (character-level)
- Mean pooling over sequence
- Linear layer predicting output sequence

This design keeps the model:

- lightweight  
- interpretable  
- fast to train  

---

## 📊 Training Results

Training converges quickly:

- Loss decreases steadily over epochs  
- Model achieves perfect predictions on training set  
- Outputs are consistent across all test cases  

Example predictions:

```
front=A, right=B, top=C → ABC
front=P, right=Q, top=R → PQR
```

---

## 🧩 Visual Results

### ✅ Correct Visualization

**Predicted Cube Face Labels in 2x3 Grid**

Clean and correct mapping of cube faces.

![Correct visualization](./Predicted%20Cube%20Face%20Labels%20in%202x3%20Grid.png)

---

### ❌ Incorrect Visualization

**Incorrect Cube Face Prediction with Labeling Errors**

Example of flawed output with duplicated or misplaced labels.

![Incorrect visualization](./Incorrect%20Cube%20Face%20Prediction%20with%20Labeling%20Errors.png)

---

## 📂 Repository Structure

```
├── README.md
├── cube_face_labeling_3d_model.ipynb
├── data_preparation.md
├── model_training.md
├── training_logs.md
├── execution_guide.md
├── Predicted Cube Face Labels in 2x3 Grid.png
├── Incorrect Cube Face Prediction with Labeling Errors.png
```

---

## ▶️ How to Run

1. Open the notebook:
   ```
   cube_face_labeling_3d_model.ipynb
   ```

2. Install dependencies:
   ```
   pip install torch matplotlib
   ```

3. Run all cells:
   - data encoding  
   - training  
   - prediction  
   - visualization  

4. Observe outputs and generated cube plots

---

## 🔬 Reproducibility

This project is fully reproducible:

- deterministic dataset  
- explicit training loop  
- clear logs  
- complete notebook included  

---

## 🎯 Purpose

This repository serves as:

- a minimal ML experiment  
- a symbolic reasoning prototype  
- a base for spatial AI tasks  
- a candidate structure for Parameter Golf-style submissions  

---

## ⚠️ Note

This is a prototype repository.  
To be submitted to a formal benchmark (e.g., Parameter Golf), it would require:

- structured `/records/...` folder  
- `submission.json`  
- standalone training script  
- strict size constraints  

---

## 👤 Author

Terraforming-Planet

Exploring AI, structured reasoning, and systems that can evolve toward real-world applications.
