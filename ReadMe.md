# F1 Qualifying Analysis
For my final project I plan to focus on track-based and driver-based qualifying performance, I am currently working on code to obtain the track data.

## Setup
1. Clone repository:
```bash
git clone https://github.com/mvnye/F1-Qualifying-Analysis.git
cd F1-Qualifying-Analysis
```

2. Install pipenv if not already installed:
```bash
pip install pipenv
```

3. Set up the virtual environment and install dependencies:
```bash
pipenv shell
pipenv install
```

4. Run the data pipeline:
```bash
cd src
python data_collection.py --years 2023 2024 --output-dir data
python data_processing.py --input-dir data --output-dir data
python dashboard.py
```

Note: The scripts will automatically create necessary directories.

## Scripts Overview
The project consists of three main Python scripts:

### data_collection.py
Downloads and organizes F1 qualifying data into CSV files for each year specified. Options:
- `--years` (Required): List of years (since 2018) to fetch data (e.g., 2021 2022 2023)
- `--cache-dir`: Directory for FastF1's cache (default: f1_cache)
- `--output-dir`: Directory to save fetched data (default: data)
- `--reload`: Whether to reload existing data (default: False)

Example usage:
```bash
python data_collection.py --years 2020 2021 2022 2023
```

### data_processing.py
Processes the raw qualifying data and creates the career timeline dataset. Options:
- `--input-dir`: Directory containing the raw CSV files (default: data)
- `--output-dir`: Directory for processed output (default: data)
- `--filename`: Name for the output file (default: career_timeline.json)

Example usage:
```bash
python data_processing.py 
```

Features:
- Combines qualifying data from multiple years
- Calculates gaps to pole position (P1 in qualifying)
- Computes teammate comparisons
- Generates season statistics

### dashboard.py
Creates an interactive dashboard visualization.

Example usage:
```bash
python dashboard.py 
```

## Dashboard Features and Usage
The interactive dashboard provides comprehensive qualifying analysis with several features:

### Main Features
- Driver career timeline with year-by-year analysis
- Qualifying position tracking throughout seasons (P1 indicates pole position)
- Gap to pole position analysis (time difference to P1)
- Teammate comparison metrics
- Best qualifying achievements per season
- Season summarization statistics
- Detailed race-by-race event analysis

### How to Navigate
1. **Driver Selection**: Use the dropdown menu at the top of the screen to switch between drivers
2. **Year Sections**: For each year in the selected driver's career, you'll see:
   - Team information
   - Best qualifying position and where it was achieved
   - Average performance metrics
   - Interactive position graph
   - Event-specific details
3. **Event Details**: Use the dropdown menu in the lower right of each year section to view specific qualifying session results

## Data Structure
- Raw data is stored in CSV files in the data directory
- Processed data is saved as career_timeline.json in the data directory
- FastF1 cache is stored in f1_cache directory

For more information about project goals, motivations, and background, see `ProjectProposal.pdf`
