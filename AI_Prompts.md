# AI Prompts for Excel Movie Financial Analysis

## 1. Data Understanding

I'm new to this dataset, so walk me through it step by step. Explain how `Budget USD` is calculated from `Budget`, `Unit`, and `Currency`. Help me understand which columns contain original data and which are derived. Identify any data quality issues. Present all findings in plain, simple sentences in Excel. Do not modify the data yet.

## 2. Data Cleaning

### Remove Empty Column

Remove the completely empty column G from the Movies table. Do not change any other data.

### Review and Remove Duplicates

Review the duplicate records for *Thor: Love and Thunder*. Compare the records, keep one correct entry, and remove the confirmed duplicate.

Review the duplicate record for *Parasite*. Compare the records and remove the duplicate if confirmed, keeping one correct entry. Do not remove records simply because their titles are similar.

### Clean Text Fields

Remove leading and trailing spaces and unnecessary extra spaces from movie titles and studio names. Preserve the original spelling and intended names.

## 3. Data Transformation

### Create ROI%

In the `MovieFinancials` table, create a new column named `ROI%` immediately after `Revenue (USD mm)`.

Calculate ROI using:

`ROI% = (Revenue USD - Budget USD) / Budget USD`

If the budget or revenue is missing, or if the budget is zero, leave the result blank. Ensure no formula errors appear in the worksheet.

Format ROI as a percentage with no decimal places. Apply conditional formatting to highlight loss-making movies with negative ROI in red and movies with ROI above 1000% in amber. Preserve existing data.

### Create Watch Verdict

Create a new column named `Watch Verdict` immediately after the `ROI%` column.

Assign verdicts using these rules:
- Must Watch: IMDb rating is 8 or above.
- Worth a Watch: IMDb rating is 6 or above but below 8.
- Skip: IMDb rating is below 6.
- Not Rated: IMDb rating is missing.

Use a formula that updates automatically when the IMDb rating changes. Handle missing ratings without formula errors.

## 4. Data Analysis

### Create Language Summary

Create a new worksheet named `Language Summary`. Summarize the movies by language name, not language ID.

Include these columns:
- Language
- Number of Movies
- Average IMDb Rating
- Total Profit (USD)

Calculate total profit as:

`Total Profit = Revenue USD - Budget USD`

Use consistent currency units, exclude missing IMDb ratings when calculating averages, avoid counting confirmed duplicate records, and handle missing financial values appropriately. Keep the summary clearly structured and easy to read.

## 5. Data Visualization

### Create Total Profit Chart

On the `Language Summary` worksheet, create a chart showing total profit by language. Use `Language` for the categories and `Total Profit (USD)` for the values.

### Format the Chart

- Sort languages by total profit in descending order.
- Remove the numerical scale and labels from the Y-axis.
- Remove the X-axis and Y-axis titles.
- Add data labels to display profit values.
- Set the chart title to `Total Profit by Language`.
- Keep the chart clean, readable, and easy to compare.
- Do not modify the underlying summary data.

## 6. Validation and Quality Assurance

Review the completed workbook and perform the following checks:

1. **Row Count:** Compare the total movie count in `MovieFinancials` with the total represented in `Language Summary`. Confirm whether they match.
2. **Manual ROI Verification:** Calculate the ROI for *The Godfather* manually using its revenue and budget in USD. Compare the result with the Excel calculation.
3. **Summary Reconciliation:** Compare movie counts by language in `Language Summary` against the corresponding records in `MovieFinancials`.
4. **Filter Test:** Filter `Watch Verdict` to show only `Must Watch` movies. Verify that all displayed movies have IMDb ratings of 8 or above.
5. **Formula and Formatting Check:** Check for formula errors, incorrect number formatting, unintended changes, and missing values that could affect the analysis.
6. **Final Report:** Present the results of each check in plain, simple sentences. Identify any discrepancies and explain the proposed correction before making further changes.
