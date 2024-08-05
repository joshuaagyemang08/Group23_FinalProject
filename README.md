﻿# Group23_FinalProject
#Drug Interaction Prediction Application
This application predicts drug-drug interactions and visualizes the relationships between drugs using a web interface. It leverages a neural network model trained on drug interaction data and displays the interaction levels graphically.

Table of Contents
Project Description
Installation
Usage
Endpoints

Project Description
This project predicts the interaction levels between drugs based on their common names or synonyms using a neural network model. Additionally, it visualizes the drug interactions in a graph, highlighting different interaction levels (minor, moderate, and major).

Installation
Clone the repository:

sh
Copy code
git clone https://github.com/your-username/drug-interaction-prediction.git
cd drug-interaction-prediction
Create and activate a virtual environment:

sh
Copy code
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install the required packages:

sh
Copy code
pip install -r requirements.txt
Ensure you have the required CSV files in the project directory:

drugbank vocabulary.csv
ddinter_downloads_code_A.csv
ddinter_downloads_code_B.csv
ddinter_downloads_code_V.csv
Ensure you have the trained model and encoders:

drug_interaction_model.h5
label_encoder.pkl
onehot_encoder.pkl
Usage
Run the Flask application:

sh
Copy code
flask run
Access the application:

Open your web browser and go to http://127.0.0.1:5000.

Endpoints
Home Page

URL: /
Method: GET
Description: Renders the homepage of the application.
Predict Interaction

URL: /predict

Method: POST

Description: Predicts the interaction level between two drugs.

Request Body:

json
Copy code
{
  "drug_a": "DrugNameA",
  "drug_b": "DrugNameB"
}
Response:

json
Copy code
{
  "prediction_ab": "InteractionLevel",
  "prediction_ba": "InteractionLevel"
}
Graph Interaction

URL: /graph

Method: POST

Description: Generates a graph showing interactions between drugs.

Request Body:

json
Copy code
{
  "Drug_A": "DrugNameA",
  "Drug_B": "DrugNameB",
  "Level": "InteractionLevel"
}
Response: HTML string containing a base64 encoded image of the graph.
