# HealthConnect Rwanda - Week 8 Data Science Final Package

**Intern:** Takudzwa Jeffrey Gumbo  
**Track:** Data Science  
**Programme:** AnalystLab Africa Experience Lab - Batch E  

## Final modelling outcome
The final documented candidate is a leakage-safer **Gradient Boosting** admission classifier using a patient-arrival feature set validated through Data Analytics collaboration.

- Dataset: 5,000 integrated appointment records
- Admission positives: 586 (11.72%)
- Holdout ROC-AUC: **0.5189**
- 5-fold CV ROC-AUC: **0.5237 +/- 0.0246**
- Final decision: **NOT suitable for clinical or operational deployment**

The model is retained as a reproducible final project artifact, not as a production model.

## Final feature set
AgeAtAppointment, Gender, HasChronicCondition, VisitType, FacilityID, DepartmentID, PriorVisits, AppointmentMonth, AppointmentWeekday

Prediction point: **patient arrival / before initial clinical assessment**. Diagnosis and Severity are excluded because their timing may introduce leakage.

## Cross-track integration
Agu Precious (Data Analytics) provided validated feature and data-quality findings that directly changed the Data Science feature set and final interpretation. The collaboration improved feature governance but did not produce a deployable model.

## Attendance limitation
The supplied Rwanda appointment data does not contain an attendance/no-show outcome. No attendance target or attendance model has been fabricated.

## Package contents
- `Notebook/Week8_Final_DataScience_Model.ipynb` - final reproducible notebook
- `Models/` - serialized final documented candidate with deployment warning
- `Reports/` - full final report and executive model summary
- `Evidence/` - final metrics, error analysis, feature decisions, integration/readiness records
- `Visualizations/` - final evaluation visuals
- `Presentation/` - final slide deck and 5-10 minute presentation script
- `References/` - official assignment and cross-track source evidence

## Reproducibility
The notebook searches recursively under `/content/drive/MyDrive/Analyst Lab Africa` when run in Google Colab and fails clearly on missing or duplicate copies of the integrated dataset.

## Ethical / operational statement
This is an educational/portfolio Data Science project. The final model has not achieved the predictive performance required for clinical or operational use.
