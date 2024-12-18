# F1 Qualifying Analysis

For my final project I plan to focus on track-based and driver-based qualifying performance, I am currently working on code to obtain the track data.

## Setup

1. Clone repository:
```bash
git clone https://github.com/mvnye/F1-Qualifying-Analysis.git
cd F1-Qualifying-Analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Scripts Overview

So far this project provides two main scripts:

### data_collection.py
Downloads and organizes F1 qualifying data into CSV files for each year specified (since 2018). The script allows you to specify several options:
- `--years` (Required): A list of years to fetch data for (e.g., 2021 2022 2023)
- `--cache-dir`: Directory for FastF1's cache (default: f1_cache)
- `--output-dir`: Directory to save fetched data (default: data/original_data)
- `--reload`: Whether to reload existing data (default: False)

Example usage:
```bash
python data_collection.py --years 2020 2021 2022 2023 --cache-dir custom_cache --output-dir custom_output_dir --reload True
```

### data_cleaning.py
Processes and combines the collected data into a comprehensive dataset. The script allows you to specify options such as input and output directories:
- `--input-dir`: Directory containing raw data files to be cleaned (default: data/original_data)
- `--output-dir`: Directory where the cleaned data will be saved (default: data)

Example usage:
```bash
python data_cleaning.py --input-dir data/original_data --output-dir data/cleaned_data
```

Example data is provided in the data and original_data folders.

## Research Objectives

### 1. Track-Specific Performance Analysis
Using FastF1's track metadata, we examine how circuit characteristics shape qualifying performance by:
- Analyzing historical best lap times at each circuit
- Identifying correlations between track features and qualifying times
- Identifying which drivers excel at specific track types
- Determining patterns in track-specific performance

### 2. Driver Evolution Study
Track drivers' qualifying performance trajectories by:
- Mapping performance changes throughout their F1 careers
- Analyzing the possible impact of team transitions on qualifying results
- Identifying periods of peak, and not so peak, performance
- Comparing performance trends across different career stages

For more information about project goals, motivations, and background, see `ProjectProposal.pdf`
