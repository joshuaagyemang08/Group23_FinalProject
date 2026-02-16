Drug Interaction Prediction & Safety Analysis
Neural Network Implementation for High-Stakes Medical Predictions



Project Overview
This project implements a neural network to predict interaction levels (Minor, Moderate, Major) between pharmaceutical compounds. Beyond simple prediction, the project focuses on algorithmic reliability and data visualization to make "black-box" model outputs more interpretable for safety analysis.


Technical Track Categories
Small ML Experiment: Training and evaluating an MLP on categorical chemical data.
Tooling & Scripting: Developing a Flask-based interface for real-time model interrogation and graph-based relationship mapping.


Model Architecture & Safety Features
Neural Network: A Multi-Layer Perceptron (MLP) built with Keras/TensorFlow using dense layers and Softmax activation for multiclass probability distribution.


Symmetry Consistency Check: A core safety feature ensuring that the interaction prediction for (Drug A + Drug B) remains consistent with (Drug B + Drug A), identifying potential model variance.
Visual Interpretability: Uses Matplotlib and NetworkX to generate interaction graphs, allowing researchers to audit the model's perceived relationship clusters.


Dataset & Preprocessing
Sources: Integrated data from DrugBank Vocabulary and DDInter (Codes A, B, and V).
Encoding: Implemented One-Hot Encoding for drug features and Label Encoding for interaction severity levels to ensure mathematical compatibility with the neural architecture.


Installation & Setup
Clone the repository:
bash
git clone https://github.com
cd Group23_FinalProject
Use code with caution.

Environment Configuration:
bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
Use code with caution.

Dependency Note: Ensure drug_interaction_model.h5, label_encoder.pkl, and onehot_encoder.pkl are present in the root directory before execution.
Usage
Run the Flask application to launch the safety audit interface:
bash
flask run
Use code with caution.

Access the local server at http://127.0.0.1:5000.
API Endpoints for Model Testing
POST /predict: Input two drug names to receive the interaction level. This endpoint returns dual predictions (A->B and B->A) to verify model robustness.
POST /graph: Generates a base64-encoded relational graph of the interaction network for manual inspection.


