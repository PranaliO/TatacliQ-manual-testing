# Tata CLiQ – Test Execution Summary & Manual Execution Checklist

## 1. Execution Overview
This document outlines the execution governance, current status, and manual step-by-step checklist for the **Tata CLiQ Manual Testing Project**.

* **Master Test Suite Count:** 52 Test Cases
* **Execution Status:** **Pending Execution** (Baseline Initialized)
* **Testing Model:** 100% Manual Execution on live public web application ([https://www.tatacliq.com](https://www.tatacliq.com)).
* **Authenticity Principle:** Zero automated scripts and zero fabricated passes. All test cases are initialized with `Status = Not Executed` and `Actual Result = Not Executed` in `Test-Execution-Report.xlsx` to be executed manually by the candidate.

---

## 2. Test Execution Metrics Baseline

| Metric | Planned Count | Actual Execution Count | Percentage |
| :--- | :---: | :---: | :---: |
| **Total Test Cases Planned** | 52 | - | 100% |
| **Test Cases Executed** | 0 | 0 | 0% |
| **Test Cases Passed** | 0 | 0 | 0% |
| **Test Cases Failed** | 0 | 0 | 0% |
| **Test Cases Blocked** | 0 | 0 | 0% |
| **Test Cases Not Executed** | 52 | 52 | 100% |
| **Genuine Defects Logged** | 0 | 0 | - |

> *Note:* As you manually execute each test case on the live Tata CLiQ site, update the status in `Test-Execution-Report.xlsx` from `Not Executed` to `Pass`, `Fail`, or `Blocked`, and recalculate the execution summary metrics.

---

## 3. Step-by-Step Manual Execution Checklist

For every test case in the test suite, adhere to the following 13-step standard operating procedure:

```text
[1. Open Tata CLiQ] ────► [2. Navigate to Feature] ────► [3. Verify Preconditions]
                                                                    │
                                                                    ▼
[6. Compare Actual vs Expected] ◄── [5. Execute Steps] ◄── [4. Input Test Data]
          │
          ├───────────────┬────────────────────────┐
          ▼               ▼                        ▼
      [MATCH]         [MISMATCH]              [UNABLE TO PROCEED]
          │               │                        │
     Mark 'PASS'     Mark 'FAIL'             Mark 'BLOCKED'
          │               │                        │
          │         [7. Capture Screenshot]        │
          │         [8. Log Bug in Bug-Reports]    │
          │         [9. Assign Defect ID]          │
          │               │                        │
          ▼               ▼                        ▼
     [10. Update Test-Execution-Report.xlsx & Markdown]
     [11. Update Requirement Traceability Matrix (RTM)]
     [12. Update Test Summary Metrics]
     [13. File Evidence PNG in 08-Test-Evidence/]
```

### Detailed Procedure:
1. **Launch Browser:** Launch Google Chrome or Microsoft Edge at 100% zoom with clean cache/cookies.
2. **Navigate:** Open `https://www.tatacliq.com` and navigate to the specified feature module.
3. **Verify Preconditions:** Confirm all preconditions stated in the test case are satisfied (e.g., guest status, specific product in stock, cart empty).
4. **Input Test Data:** Copy the exact test data defined in `03-Test-Design/Test-Data.xlsx` (e.g., mobile number, search keyword, pincode).
5. **Execute Steps:** Follow the step-by-step instructions sequentially without skipping steps.
6. **Compare Results:** Compare the observed system behavior against the documented *Expected Result*.
7. **Record Actual Result:** Record the precise observed behavior in `Test-Execution-Report.xlsx`. Avoid vague phrases like "working"; write explicit observations (e.g., *"System displayed inline message 'Please select a size' in red font beneath size chips"*).
8. **Determine Status:**
   * **Pass:** Actual Result matches Expected Result completely.
   * **Fail:** Actual Result deviates from Expected Result or reveals a functional defect.
   * **Blocked:** A prerequisite failure prevents executing the steps (e.g., product page fails to load).
9. **Capture Screenshot Evidence:** If the test failed or produced key visual feedback, capture a clean screenshot using Snipping Tool and save to `08-Test-Evidence/` following naming convention `TC_<ID>_<description>.png`.
10. **File Defect (If Failed):** Open `05-Defect-Management/Bug-Reports.xlsx` and log a new defect entry with reproduction steps, severity, and priority.
11. **Update Test Execution Report:** Enter the assigned `Defect ID` in the execution log.
12. **Update RTM:** Update `06-RTM/Requirement-Traceability-Matrix.xlsx` with the final status and Defect ID.
13. **Finalize Record:** Save and commit spreadsheet updates.

---

## 4. Exploratory Testing Session Charter

In addition to scripted test cases, exploratory testing is performed to discover edge cases through unscripted investigation.

| Session Attribute | Details |
| :--- | :--- |
| **Session ID** | `EXP_SESSION_001` |
| **Charter** | Explore the Shopping Bag and Checkout transition under intermittent network lag and rapid UI interactions to discover race conditions or state synchronization bugs. |
| **Tester** | Manual QA Candidate |
| **Target Area** | Shopping Bag (`/cart`) & Checkout Address Form |
| **Time Box** | 45 Minutes |
| **Environment** | Windows 11, Google Chrome v128.0 (1920x1080) |
| **Execution Status** | **Pending Execution** (To be performed during execution phase) |
| **Planned Activities** | 1. Rapidly toggling item quantities between 1 and 5.<br>2. Opening multiple tabs with the same cart session.<br>3. Switching from Guest to Logged-in while item is in cart.<br>4. Entering partial addresses and clicking back in browser. |
| **Observations / Findings** | *(Pending Manual Execution - To be recorded upon session completion)* |
| **Defects Discovered** | *(Pending Manual Execution - To be linked if uncovered)* |
