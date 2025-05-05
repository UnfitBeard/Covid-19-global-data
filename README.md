# COVID-19 Global Data Tracker 🌍📊

A Python-based data analysis project tracking global COVID-19 trends, including cases, deaths, recoveries, and vaccination progress. Built with pandas, matplotlib, and Plotly.

![Choropleth Map Example](images/choropleth.png) <!-- Add your own screenshot -->

---

## 📌 Features
- **Global Trends Analysis**: Track cases, deaths, and vaccinations over time.
- **Country Comparisons**: Compare metrics across regions (e.g., USA vs. India).
- **Interactive Visualizations**: Choropleth maps, line charts, and bar graphs.
- **Insights Report**: Automated Jupyter Notebook/PDF report with key findings.

---

## 🛠️ Installation
1. **Clone the repository**:
   git clone https://github.com/yourusername/covid19-global-tracker.git
   cd covid19-global-tracker

## Install dependencies:
  pip install pandas matplotlib seaborn plotly jupyterlab

# 🚀 Usage
## 1. Data Collection
The project uses the Our World in Data (OWID) dataset. The CSV is auto-downloaded, but you can manually fetch it:
  import pandas as pd
  url = "https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/owid-   covid-data.csv"
  df = pd.read_csv(url)
  
## 2. Run the Analysis
Execute the Jupyter Notebook:
  jupyter notebook COVID-19_Data_Analysis.ipynb
## 3. Key Workflow Steps
Data Cleaning:

# Filter countries and handle missing data
  countries = ['United States', 'India', 'Brazil', 'Kenya']
  filtered_df = df[df['location'].isin(countries)]
  filtered_df['date'] = pd.to_datetime(filtered_df['date'])
  
Generate Visualizations:
  import matplotlib.pyplot as plt
  plt.figure(figsize=(12, 6))
  for country in countries:
      country_data = filtered_df[filtered_df['location'] == country]
      plt.plot(country_data['date'], country_data['total_cases'], label=country)
  plt.title('COVID-19 Cases Over Time')
  plt.legend()
  plt.show()
  
## 4. Export the Report
Convert the Jupyter Notebook to PDF:
  jupyter nbconvert --to pdf COVID-19_Data_Analysis.ipynb
  
## 📂 Project Structure
covid19-global-tracker/
├── CovidDataset.ipynb/                                 
└── README.md

## 📊 Data Sources
Primary Dataset: Our World in Data (OWID)
Alternative: Johns Hopkins University
Vaccination Data: OWID Vaccination

📝 License
This project is licensed under the MIT License. See LICENSE.

🙏 Acknowledgments
Data providers: Our World in Data, Johns Hopkins University.
Inspired by Kaggle COVID-19 analysis notebooks.


  



