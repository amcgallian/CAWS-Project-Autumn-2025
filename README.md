# CAWS-Project-Autumn-2025
Repository for Andrew, John, and Joseph of their Chicago Area Waterway System project for Environmental Data Science I, Autumn 2025

Please use `requirements.txt` to ensure proper set up by using:
```{bash}
pip install -r requirements.txt
```

Our main notebook with our analysis, code, and plots is `CAWS_Analysis_Notebook.ipynb`.

Supplementary information surrounding parameters, our water quality index, our heavy metal pollution index, and various referred supplementary material can be found in our `supplementary_info` folder.

Our `data` folder consists of multiple subfolders: `original`, `processed`, `raw`, and `Waterways`.
- `original` contains all data from MWRD in the state recieved directly from downloaded, with no columned edited.
- `raw` contains all of the data from `original` which has been altered to get rid of extraneous non-data text in cells, extra rows, and convert station coordinates from DMS to DD. These files are what we call to start our analysis.
- `processed` contains saved water quality index and heavy metal pollution index (geo)dataframes that were made during the analysis.
- `Waterways` contains our shapefile of all Illinois waterways that we read into our analysis.