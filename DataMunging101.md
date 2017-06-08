---
Title: Data Cleaning Tasks
Date: 06.08.2017
---

# Getting Started

1. Adjust Values: Open Refine and load in your browser. You should see `127.0.01.XXXX` in your address bar. Add `/preferences` to this address and adjust the `value` limit to 10,000. This means that we can perform operations on larger datasets.
2. Get Data: Go to the INFX 551 github repository, and find the `Data` tab. Download the file under `DataMunging101` titled `Building_Permits.csv` This is a from the City of Seattle open data portal (read more about it at [BUILDING PERMITS: CURRENT](https://data.seattle.gov/Permitting/Building-Permits-Current/mags-97de))
3. Load Data: Upload this data to Refine by selecting the file form your desktop (or whatever directory you downloaded to). Be sure to select ` commas (.csv)` as the upload option.

# Normalizing Data

1. Replace all missing values with `N/A`
2. For each column, trim leading and trailing whitespace
3. Convert values with all UPPERCASE to Name Case

# Summarizing Data

1. The `Category` and the `Status` columns have a series of codes. It would be helpful to know how many codes exist in this dataset. How would we find out?
2. The `Value` column could be summarized as a range. Create a new column directly to the left of `Value` and title it `Value Range` Now, cluster all values into High (> $1 million) Medium ($500,000 - 999,999) and Low ($1-499,999)


# Adding Relevant Data
1. The `Application Date` and the `Issue Date` tell us the lag time in city responding to applications for building permits. Use the values in these two columns to create a new third column titled `Permit Issue Period`
2. The `Location` field is static. We want these values to be linked to google maps so that a user coming to the dataset can simply click to see a housing permit site. Use the text string `"https://www.google.com/maps/place/"` (the quotations are important) to create this link.
