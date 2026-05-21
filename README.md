# MH6822-Individual-Assignment
FairLink Prototype - README

STUDENT INFORMATION
Name: WANG YUE
Matriculation Number: G2505294E
Email: yue024@e.ntu.edu.sg

PROJECT OVERVIEW:
This notebook (Task 3 Code.ipynb) implements the FairLink Prototype, a
cross-jurisdictional fairness auditing system for credit approval decisions.
It simulates how the same lending model would be evaluated under the
regulatory frameworks of Hong Kong (HK) and the United States (US).
The prototype focuses on gender fairness, using approval rate disparity as the key metric.

DATASET:
A synthetic dataset of 50 credit applications tailored to the Hong Kong
  market.
Features include: credit_score, gender, age, income_hkd, loan_amount_hkd,
  approved (binary target).
Gender labels: 'M' and 'F'.

JURISDICTION RULES:
Jurisdiction | Max Allowed Gender Disparity | Explanation Required | Compliance Standard
-------------|------------------------------|----------------------|---------------------
US           | 10% (0.10)                   | Yes                  | Strict Compliance
HK           | 18% (0.18)                   | No (verbal on ask)   | Outcome-Based Compliance

HOW IT WORKS:
1. Load Jurisdiction Rules - sets thresholds and requirements for US or HK.
2. Fairness Audit - calculates male/female approval rates and absolute
   disparity.
3. Compliance Check - compares disparity against the jurisdiction's max
   allowed value.
4. Explanation Logic - determines if a written explanation is mandated (US)
   or not (HK).

RUNNING THE PROTOTYPE:
Execute the first code cell in Task 3 Code.ipynb. The output will show two
separate results blocks - one for US and one for HK.
Example output (from the provided run):

FairLink Prototype Test Results:
[US Jurisdiction Results]
Jurisdiction: US
Compliance Standard: Strict Compliance
Male Approval Rate: 0.91
Female Approval Rate: 0.36
Gender Disparity (Absolute): 0.55
Compliance Result: Non-Compliant
Explanation Requirement: Detailed technical adverse action notice required

[HK Jurisdiction Results]
Jurisdiction: HK
Compliance Standard: Outcome-Based Compliance
Male Approval Rate: 0.91
Female Approval Rate: 0.36
Gender Disparity (Absolute): 0.55
Compliance Result: Non-Compliant
Explanation Requirement: No mandatory written explanation; brief verbal
explanation if customer asks

KEY OBSERVATIONS:
- The same model shows a large gender disparity (55%).
- It is non-compliant in both jurisdictions because the disparity exceeds
  even the more lenient HK threshold (18%).
- The main difference is the explanation requirement: US demands a detailed
  written notice, while HK only requires a brief verbal explanation if the
  customer asks.

LIMITATIONS & FUTURE WORK:
- The current prototype only checks gender fairness; other protected
  attributes (age, income brackets) are not yet included.
- Synthetic dataset - real-world data would require more careful
  preprocessing.
- No mitigation algorithm is applied (e.g., reweighting, equalized odds).
  This is a detection-only prototype.
- Future versions could incorporate HK's Code of Banking Practice and US
  ECOA/Reg B more comprehensively.

DEPENDENCIES
- Python 3.x
- pandas

No additional installation is required if running in a standard Anaconda
environment (the notebook uses conda-base-py kernel).
