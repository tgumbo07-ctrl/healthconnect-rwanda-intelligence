# HealthConnect Rwanda - Week 6 Data Science

**Intern:** Takudzwa Jeffrey Gumbo (TJ)  
**Track:** Data Science  
**Project:** Healthcare Predictive Analytics and Population Health Intelligence

## Headline results
- Patients: 20,000
- Enterprise appointments (2026 summary): 60,809
- Enterprise revenue (2026 summary): RWF 1,132,677,500
- Detailed appointment sample: 5,000
- Sample admission rate: 11.7%
- Mean satisfaction: 2.99/5
- Best admission ROC-AUC: 0.497 (Gradient Boosting)
- Best satisfaction R2: -0.022

## Important limitations
1. The Health Facilities master was not supplied; facility outputs use anonymised FacilityIDs.
2. DepartmentID-FacilityID pairs are inconsistent across appointments/staff relative to the department master.
3. The detailed Appointments sheet has 5,000 rows while full diagnosis/billing tables extend to 60,000 AppointmentIDs. Appointment-level models therefore use the matched 5,000 detailed sample.
4. All patients have an InsuranceID, so insured-vs-uninsured comparison is unsupported.
5. All supplied beds are marked Available, so true bed utilization cannot be estimated.
6. Predictive outputs are educational only and are not clinical advice.

## Structure
- `Notebook/Week6_DataScience.ipynb` - self-contained Colab-compatible notebook
- `Data/Integrated/Integrated_Healthcare_Dataset.csv` - 5,000-row appointment-level analytical dataset
- `Reports/` - data quality, EDA, statistics, predictive analytics and executive summary
- `Analysis/` - reproducible result tables
- `Visualizations/` - 26 figures
- `Presentation/Executive_Presentation.pptx` - 12-slide executive deck
