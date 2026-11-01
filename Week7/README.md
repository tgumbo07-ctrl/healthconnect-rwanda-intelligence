# Week 7 - HealthConnect Model Testing, Error Analysis & Refinement

**AnalystLab Africa Experience Lab | Data Science Track**

## Purpose
This project continues the exact Week 6 HealthConnect Rwanda Data Science work. It does not start a new dataset or fabricate an attendance/no-show target.

AnalystLab Africa clarified that Week 7 should use the same dataset as Week 6. The supplied Week 6 Rwanda appointment data contains no attendance/no-show/cancellation outcome, so appointment attendance cannot be modelled directly. That limitation is documented explicitly.

The genuine Week 6 classification component - hospital admission prediction - is therefore the component tested in Week 7.

## Week 6 source preservation
Historical source package:
`Week6_DataScience_HealthConnect_TakudzwaGumbo_FINAL.zip`

SHA-256:
`123ccd7e70aa5161a2e4848ed03b8bdf5eeb2cfb13f175ad5c110577ff3a7a94`

The Week 6 ZIP is not modified by this project.

## Main Week 7 findings
- Detailed integrated sample: 5,000 records.
- Admission positive rate: 11.72%.
- Week 6 Gradient Boosting reproduction ROC-AUC: 0.4967.
- Week 7 final holdout candidate ROC-AUC: 0.4917.
- Candidate recall at threshold 0.50: 0.0085.
- Tested refinement: balanced Logistic Regression excluding FacilityID and DepartmentID, with threshold selected on validation data.
- Refined holdout ROC-AUC: 0.5420.
- Refined 5-fold cross-validated ROC-AUC: 0.4875 +/- 0.0257.
- Final decision: **no tested model is validated for operational deployment.** The refinement is rejected as unstable and operationally imprecise.

## Why the negative result matters
Week 7 is a testing and validation week. A model should not be called improved simply because one holdout metric rises. The apparent refinement gain did not survive cross-validation and generated an excessive false-positive burden. The project therefore preserves the evidence rather than forcing a success narrative.

## Folder structure
- `Notebook/` - executed Week 7 testing/refinement notebook.
- `Reports/` - main report and concise project summary in DOCX and PDF.
- `Evidence/` - model test results, error analysis, segment results, CV results, issue log, testing record and cross-track record and collaborator evidence.
- `Visualizations/` - model validation charts.
- `References/` - Week 7 assignment and AnalystLab clarification.
- `SUBMISSION_GUIDE.md` - Colab, Drive, GitHub and form workflow.
- `WEEK7_SUBMISSION_CHECKLIST.md` - final submission QA.
- `HC_POD_CROSS_TRACK_TEST_REQUEST.md` - exact genuine test request and evidence steps.

## Completed HC-POD cross-track validation
A genuine **Data Analytics -> Data Science** activity was completed with **Agu Precious**. Her validated analytics findings were used to review the admission-model features and prediction timing.

Key action:
- Prediction point defined as **patient arrival / before initial clinical assessment**.
- `Diagnosis` and `Severity` held out because their timing may introduce leakage.
- `Age` recalculated at appointment date.
- Time-safe `PriorVisits`, appointment month and weekday tested.
- `FacilityID` and `DepartmentID` retained with caveats rather than removed solely because rating differences were not significant.

Cross-track re-test:
- Gradient Boosting holdout ROC-AUC: **0.5189**
- Gradient Boosting 5-fold CV ROC-AUC: **0.5237 +/- 0.0246**
- Balanced Logistic Regression holdout ROC-AUC: **0.5024**
- Balanced Logistic Regression 5-fold CV ROC-AUC: **0.4986 +/- 0.0322**

The collaboration improved feature governance and leakage control, but did **not** validate an operationally useful model.

## Week 8 readiness
1. Preserve the completed HC-POD testing evidence and validated feature-governance decisions.
2. If appointment attendance remains the target, obtain a real attendance/no-show/cancellation outcome field.
3. Obtain stronger predictors available before the admission decision if admission modelling is to continue.
4. Keep the validated negative result in the project history.
5. Do not deploy the current candidate or tested refinement.
