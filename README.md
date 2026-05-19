# JPC HubSpot Contact Analysis

## Project Overview

This notebook analyzes an exported HubSpot contact dataset for Justin Panzer Consulting (JPC), a boutique B2B marketing consultancy. The goal is to use existing CRM data to identify patterns in contact engagement, pipeline movement, and customer conversion. The analysis is exploratory and meant to support actionable recommendations around follow-up prioritization and pipeline management.

---

## File Structure

```
jpc_hubspot_analysis_final.ipynb                        # Main analysis notebook
hubspot-crm-exports-all-contacts-2026-04-10.csv         # Required data file (not included in repo)
README.md                                               # Project documentation
```

The notebook expects the HubSpot CSV export to be in the same directory and named exactly:
`hubspot-crm-exports-all-contacts-2026-04-10.csv`

---

## Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Loading, cleaning, filtering, and grouping the HubSpot contact data |
| `matplotlib.pyplot` | Creating all bar charts and histograms used in the analysis |

Both libraries are available by default in Google Colab. If running locally, install them with:

```
pip install pandas matplotlib
```

---

## Notebook Sections

The notebook is organized into 12 sections:

1. **Import libraries and load the data** — reads the HubSpot CSV export into a pandas DataFrame
2. **Select columns** — filters down to only the fields relevant to lifecycle stage, sales activity, and contact engagement
3. **Clean the data** — converts date and numeric columns to proper types, fills missing values, and creates a customer flag
4. **Pipeline overview** — bar chart of contacts by current lifecycle stage
5. **Conversion funnel** — counts how many contacts have ever entered each stage (Lead through Customer)
6. **Sales activity vs. conversion** — compares average activity levels between contacts who became customers and those who did not
7. **Activity rate groups** — bins contacts by sales activity count and calculates customer rate per group
8. **Lead status performance** — summarizes customer rate and average activity by lead status
9. **Time to close** — describes and visualizes the distribution of days to close for converted contacts
10. **Recent activity and inactive contacts** — categorizes contacts by how recently they had activity
11. **Probability analysis** — calculates conditional probability of becoming a customer based on lead status, sales activity level, and contact frequency
12. **Final takeaways and limitations** — summarizes findings and notes constraints of the dataset

---

## Data Requirements

The analysis uses a single exported CSV file from HubSpot. Key columns include:

- `Lifecycle Stage`, `Lead Status`
- `Create Date`, `Last Activity Date`, `Last Contacted`, `Close Date`, `Days To Close`
- `Number of Sales Activities`, `Number of times contacted`, `Number of Associated Deals`
- `Marketing emails opened`, `Marketing emails clicked`, `Marketing emails replied`
- Pipeline stage date columns (e.g., `Date entered "Customer (Lifecycle Stage Pipeline)"`)

The notebook uses only columns that are present in the file, so it will not break if some fields are missing from a different export.

---

## Notes

- This notebook was built in Google Colab. A Colab badge link is included at the top for easy access.
- The analysis is exploratory. Because the dataset contains a limited number of converted customers, probability estimates should be treated as directional rather than statistically conclusive.
- The export date (April 10, 2026) is used as the reference point for calculating days since last activity.
