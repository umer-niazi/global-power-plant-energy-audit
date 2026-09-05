# Global Power Plant Energy Audit

Exploratory data analysis and machine learning on the [Global Power Plant Database](https://datasets.wri.org/dataset/globalpowerplantdatabase) to investigate whether global infrastructure is shifting from fossil fuels toward renewable energy.

> **Note:** Originally developed as a group AI course project. I was responsible for the data pipeline, feature engineering, model development and analysis.

## Dataset

The project uses the World Resources Institute's Global Power Plant Database.

The analysis focuses on power plants with valid:

- Country
- Primary fuel type
- Installed capacity
- Commissioning year

## Methodology

After cleaning and filtering the dataset, four classical machine learning models were evaluated:

- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)

The models were trained to classify whether a power plant uses a renewable or non-renewable energy source based on plant capacity, age and country.

## Results

<p align="center">
  <img src="figures/confusion_matrix.png" width="300"/>
</p>

| Model | Accuracy |
| :--- | ---: |
| Support Vector Machine | ~0.78 |
| K-Nearest Neighbors | ~0.77 |
| Random Forest | ~0.76 |
| Logistic Regression | ~0.66 |

The top three models performed within one to two percentage points of each other, while Logistic Regression achieved ~0.66, suggesting that the selected features provide only limited separation between renewable and non-renewable plants. All models outperformed the majority-class baseline of 0.5262.

## Repository Structure

```text
├── notebooks/
│   └── energy_transition_audit.ipynb
├── figures/
│   ├── data_cleaning_audit.png
│   ├── capacity_pie.png
│   ├── fuel_bar.png
│   ├── age_trends.png
│   ├── renewable_breakdown_appendix.png
│   ├── confusion_matrix.png
│   └── feature_importance.png
├── README.md
└── requirements.txt
```

## Run Locally

```bash
git clone https://github.com/umerkniazi/global-power-plant-energy-audit.git
cd global-power-plant-energy-audit
pip install -r requirements.txt
jupyter notebook notebooks/energy_transition_audit.ipynb
```