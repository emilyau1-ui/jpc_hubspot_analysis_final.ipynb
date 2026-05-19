# JPC HubSpot Contact Analysis

This notebook analyzes an exported HubSpot contact dataset for Justin Panzer Consulting (JPC), a boutique B2B marketing consultancy. The goal is to use existing CRM data to identify patterns in contact engagement, pipeline movement, and customer conversion. Findings are meant to support recommendations around follow up prioritization and pipeline management.

---

## Libraries Used

- pandas: loading, cleaning, filtering, and grouping the contact data
- matplotlib.pyplot: creating bar charts and histograms

Both libraries are available by default in Google Colab. 

---

## File Structure

```
jpc_hubspot_analysis_final.ipynb                   # Main analysis notebook
hubspot-crm-exports-all-contacts-2026-04-10.csv    # Required data file 
README.md                                          # Project documentation
```

The notebook expects the HubSpot CSV export to be in the same directory.

---

## Notebook Sections

1. Import libraries and load the data
2. Select relevant columns
3. Clean the data
4. Pipeline overview
5. Conversion funnel
6. Sales activity vs. conversion
7. Activity rate groups
8. Lead status performance
9. Time to close
10. Recent activity and inactive contacts
11. Probability analysis
12. Final takeaways and limitations

---

## Notes

- Built in Google Colab.
- The dataset had a limited number of converted customers, so probability estimates should be treated as exploratory rather than definitive.
- April 10, 2026 is used as the reference date for calculating days since last activity.
