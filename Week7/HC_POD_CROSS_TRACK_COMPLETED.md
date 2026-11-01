# HC-POD Cross-Track Validation - Completed

**Data Science intern:** Takudzwa Jeffrey Gumbo  
**Collaborating track:** Data Analytics  
**Collaborator:** Agu Precious  
**Date:** 1 November 2026

## Test
Review the Week 6 hospital-admission model features against validated Data Analytics findings and determine whether a safer prediction-time feature set changes model performance.

## Finding
- Supported: Gender, HasChronicCondition, VisitType; Age with appointment-date calculation.
- Retain with caveats: FacilityID, DepartmentID.
- Further validation required: MaritalStatus, Education, BloodGroup, BMI.
- Hold because of prediction-time leakage risk: Diagnosis, Severity.
- Suggested time-safe additions: PriorVisits, appointment month and weekday.
- Attendance/no-show outcome is not present in the appointment data.

## Action
Prediction point defined as **patient arrival / before initial clinical assessment**. Re-test feature set:
`AgeAtAppointment, Gender, HasChronicCondition, VisitType, FacilityID, DepartmentID, PriorVisits, AppointmentMonth, AppointmentWeekday`.

## Re-test
- Gradient Boosting holdout ROC-AUC: **0.5189**
- Gradient Boosting 5-fold CV ROC-AUC: **0.5237 +/- 0.0246**
- Balanced Logistic Regression holdout ROC-AUC: **0.5024**
- Balanced Logistic Regression 5-fold CV ROC-AUC: **0.4986 +/- 0.0322**

## Validated outcome
The cross-track activity improved feature governance and reduced leakage risk, but the model remained close to chance and is **not suitable for operational deployment**.

## Evidence
See the `Evidence/` folder for the collaborator validation summary, feature-review response, review sheet, completed cross-track record and model re-test CSV.
