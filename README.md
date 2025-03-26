## Introduction
Welcome to the Cyclistic bike-share analysis case study! In this case study, you work for a fictional company, Cyclistic, along with some key team members. The objective is to answer critical business questions by following the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act. The Case Study Roadmap tables — including guiding questions and key tasks — will guide you through this journey to ensure a structured and effective analysis.

## Scenario
You are a junior data analyst on the marketing analyst team at Cyclistic, a bike-share company based in Chicago. The director of marketing believes that the company’s future success hinges on maximizing annual memberships. Your team’s mission is to understand how casual riders (non-members) and annual members use Cyclistic bikes differently. These insights will inform a new marketing strategy aimed at converting casual riders into annual members. To gain approval from Cyclistic executives, your recommendations must be supported by compelling data insights and professional visualizations.

## Objectives
- Compare ride length and usage patterns between casual riders and members.
- Identify trends in rideable type preferences (classic bike, electric bike, electric scooter).
- Provide data-driven recommendations to increase annual membership subscriptions.

## Dataset
The dataset consists of 12 CSV files, one for each month from February 2024 to January 2025, sourced from the `Trip Data` directory:
- `202402-divvy-tripdata.csv`
- `202403-divvy-tripdata.csv`
- ...
- `202501-divvy-tripdata.csv`

Each file contains the following columns:
- `ride_id`: Unique identifier for each trip
- `rideable_type`: Type of bike/scooter (classic_bike, electric_bike, electric_scooter)
- `started_at`: Trip start timestamp
- `ended_at`: Trip end timestamp
- `start_station_name`, `start_station_id`, `end_station_name`, `end_station_id`: Station details (dropped in analysis)
- `start_lat`, `start_lng`, `end_lat`, `end_lng`: Geographic coordinates (dropped in analysis)
- `member_casual`: User type (member or casual)

Total rows after concatenation: **5,854,384**

## Prerequisites
To run this analysis, you'll need the following:
- Python 3.10+
- Jupyter Notebook or JupyterLab
- Required Python libraries:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `plotly`

Install the dependencies using pip:
```bash
pip install pandas numpy matplotlib seaborn plotly
```

## Project Structure
```
Cyclistic-Bike-Share-Analysis/
│
├── Trip Data/   
│   ├── 202402-divvy-tripdata.csv
│   ├── 202403-divvy-tripdata.csv
│   └── ...
├── analysis.ipynb          
└── README.md               
```

## Methodology
1. **Data Loading and Cleaning**:
   - Loaded 12 CSV files and concatenated them into a single DataFrame using `pd.concat()`.
   - Dropped unnecessary columns (station names, IDs, and coordinates) to focus on ride duration and user type.
   - Checked for duplicates (none found) and missing values (handled implicitly by dropping irrelevant columns).
   - Converted `started_at` and `ended_at` columns to `datetime64[ns]` type for time-based analysis.

2. **Feature Engineering**:
   - Created a new column `ride_length` (in minutes) by calculating the difference between `ended_at` and `started_at`.

3. **Analysis**:
   - Analyzed average ride length by day of the week and user type.
   - Examined rideable type usage distribution between casual riders and members.
   - Visualized findings using Plotly bar charts.


## How to Run the Analysis
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/Cyclistic-Bike-Share-Analysis.git
   cd Cyclistic-Bike-Share-Analysis
   ```
2. Ensure the `Trip Data` directory contains all 12 CSV files.
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open `analysis.ipynb` and run all cells to reproduce the analysis and visualizations.


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
