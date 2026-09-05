# -Mobile-Price-Classification-Using-4-Models
📱 Mobile Price Classification: Benchmarking 4 ML Models
An end-to-end Machine Learning benchmark evaluating 4 classification models to predict mobile phone price tiers based on hardware specifications, battery life, display dynamics, and connectivity parameters.
📌 Executive Summary
Determining competitive pricing for mobile hardware requires balancing raw performance against manufacturing costs. This project builds a multi-class classification pipeline that analyzes mobile specifications (e.g., RAM, CPU speed, battery capacity, screen resolution) and categorizes devices into 4 distinct price tiers:
0: Low Cost
1: Medium Cost
2: High Cost
3: Very High Cost
By comparing four distinct algorithm families—ranging from simple parametric models to advanced ensemble methods—we establish clear performance baselines and isolate key hardware drivers behind device valuation.
🔬 Models Evaluated
Four distinct classification paradigms were trained, tuned, and evaluated on identical cross-validation splits:
Logistic Regression: Linear decision boundary baseline to evaluate linear separability.
K-Nearest Neighbors (KNN): Non-parametric instance-based classifier measuring feature space proximity.
Random Forest: Ensemble of decision trees leveraging bagging to reduce variance and capture non-linear relationships.
Support Vector Machine (SVM): Kernel-based classifier optimizing hyperplanes for maximal class margin separation.
🏆 Model Performance Benchmark
The models were evaluated using standard classification metrics across test splits. RAM consistently proved to be the single most influential predictor across all tree-based feature importance evaluations.
Model	Accuracy	Precision	Recall	F1-Score
SVM (RBF/Linear Kernel)	96.5%	0.97	0.96	0.96
Random Forest	88.2%	0.88	0.88	0.88
Logistic Regression	82.4%	0.82	0.82	0.82
K-Nearest Neighbors (KNN)	76.8%	0.77	0.77	0.77
(Note: SVM achieved peak performance after standardizing continuous features like RAM, Battery Power, and Pixel Dimensions).
💡 Key Analytical Insights
RAM Rules the Tiers: Feature importance analysis reveals that RAM capacity accounts for over 60% of the predictive variance in determining price bands.
Battery & Screen Matter Next: Battery power, pixel height (px_height), and pixel width (px_width) form the secondary cluster of high-impact features.
Connectivity Misconceptions: Features like 3G/4G capability, Bluetooth, and dual SIM support had minimal weight in isolating high-tier devices from budget options in this dataset.
🛠️ Project Architecture
Plaintext
├── data/
│   ├── train.csv              # Primary training dataset
│   └── test.csv               # Unlabeled test evaluation set
├── notebooks/
│   └── mobile_price_clf.ipynb # Full EDA, cleaning, scaling & model training
├── models/
│   └── best_svm_model.pkl     # Exported trained inference model
├── requirements.txt           # Python dependency manifest
└── README.md                  # Project documentation
🚀 Getting Started
Prerequisites
Ensure you have Python 3.8 or higher installed on your machine.
Installation
Clone the repository:
Bash
git clone https://github.com/your-username/mobile-price-classification.git
cd mobile-price-classification
Create a virtual environment:
Bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Install dependencies:
Bash
pip install -r requirements.txt
Run the Notebook or Training Pipeline:
Bash
jupyter notebook notebooks/mobile_price_clf.ipynb
