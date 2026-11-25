# Data source

This project uses the **City and County of Denver Open Checkbook**, calendar year 2025.

- Portal: https://www.denvergov.org/opendata
- Also mirrored via Colorado's open data hub

The raw file (~150k rows) isn't committed to this repo. To reproduce the analysis:

1. Download the 2025 checkbook CSV from the link above
2. Place it here as `data/City_of_Denver_Checkbook_2025.csv`, or set the `DENVER_CHECKBOOK_CSV` environment variable to wherever you saved it
3. Run `NoteBook/Transaction_Data_Analytics.ipynb` top to bottom
