# AI Prompts for Excel Movie Financial Analysis

## 1. Data Understanding

I'm new to this dataset, so walk me through it step by step. Explain how Budget USD is calculated from Budget, Unit, and Currency. Help me understand which columns are entered directly and which are derived. Also, identify any data quality issues in the dataset. Present all the findings in plain, simple sentences in Excel.

## 2. Data Cleaning

Remove the empty column G from the Movies table.

Review the duplicate Thor: Love and Thunder record. Compare the records, keep one entry, and remove the duplicate. Do the same for Parasite. Make sure you retain one correct entry for each movie.

Remove extra spaces from movie titles and studio names while preserving their original spelling and names.

## 3. ROI Calculation and Formatting

In the MovieFinancials table, create a new column called `ROI%` immediately after `Revenue (USD mm)`.

Calculate ROI as (Revenue USD minus Budget USD) divided by Budget USD. If the budget or revenue is missing, leave the cell blank. If the budget is zero, leave the cell blank to avoid division errors. Make sure no formula errors appear in the sheet.

Format ROI as a percentage with no decimal places. Apply conditional formatting to highlight loss-making movies in red and movies with ROI above 1000% in amber.

## 4. Watch Verdict

Next to the ROI% column, create a new column called `Watch Verdict` based on the IMDb rating.

Set the verdict to Must Watch if the rating is 8 or above, Worth a Watch if the rating is 6 or above but below 8, Skip if the rating is below 6, and Not Rated if the rating is missing.

Use a formula so the verdict updates automatically when the IMDb rating changes. Make sure the formula handles missing ratings without errors.

## 5. Language Summary

Create a new sheet called `Language Summary` and build a summary by language name, not language ID.

For each language, show the number of movies, average IMDb rating, and total profit in USD. Calculate total profit as revenue in USD minus budget in USD. Use consistent currency units and handle missing values appropriately.

## 6. Chart Creation and Formatting

On the same Language Summary sheet, create a chart showing total profit by language. Arrange the languages in descending order of total profit. Remove the numerical scale and labels from the Y-axis, remove the titles from both the X-axis and Y-axis, and add data labels for better readability. Give the chart a suitable title: `Total Profit by Language`.

