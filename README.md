# Carve-out-Event-Study
Impact of equity carve-out of corporate performance

**Overview**

The code performs an event study analysis on a set of firms to determine the effect of a spin-off on the parent company's stock price. Event study analysis helps to measure the effect of an event on the value of a firm. Here, the event of interest is a "spin-off".

**Requirements**

Python 3 Libraries: pandas statsmodels matplotlib numpy scipy sklearn

**Inputs**

dummy.xlsx: Contains information about each company, including the listing board and industry they belong to.
event_date.csv: Contains the event date for each company (the date of the spin-off).
stock.csv: Contains stock prices for each company.
ff_factors: Not provided in the code but seems to contain Fama-French factors.

**Workflow**

Data Loading and Pre-processing:
  Load dummy, event, and stock data.
  Perform necessary transformations like setting indices, dropping rows, changing data types, etc.
  Merge datasets and filter relevant columns.
Event Study Function:
  For each firm, establish a window around the event date.
  Compute expected returns using the Fama-French 3-factor model (Market, SMB, HML).
  Subtract the expected return from the actual return to get abnormal returns.
Adjusting for Factors:
  Adjust abnormal returns for company-specific variables like 'Non-SOE', 'GEM', etc. using linear regression.
Visualization:
  Plot abnormal returns for individual firms.
  Plot the mean of abnormal returns (AAR) with 95% confidence intervals.
  Compute cumulative abnormal returns (CAR) and its standard error (SE) for visualizations.

**Functions**

eventstudy: Generates abnormal returns around the event window for each company.
CAR_se: Computes the standard error of Cumulative Abnormal Return (CAR) for each stock.
CAAR_se: Computes the standard error of Cumulative Average Abnormal Return (CAAR) for the entire sample.

**Visualizations**

Abnormal Returns: Plots abnormal returns for each firm across the event window. Plots 95% confidence intervals.
Cumulative Abnormal Returns (CAR): Plots CAR for each firm across the event window. Plots 95% confidence intervals.

**Notes**

Ensure that the Fama-French factors dataset (ff_factors) is loaded before running the script.
Adjust the event and estimation windows (event_win and est_win) if necessary.
Ensure data consistency and accuracy in input files for better results.

**Future Enhancements**

Outliers and missing values handling can be incorporated for better results. Extend the analysis to consider other factors or events and incorporate more robust statistical methods.
