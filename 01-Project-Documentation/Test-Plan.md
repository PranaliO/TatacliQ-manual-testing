# Tata CLiQ – Manual Test Plan

| Document Attribute | Details |
| :--- | :--- |
| **Project Name** | Tata CLiQ Web Application – Manual Testing Portfolio |
| **Author** | Manual QA Candidate (2026 B.Tech Computer Science Fresher) |
| **Document Version** | 1.0 |
| **Application Under Test** | Tata CLiQ Web Application (https://www.tatacliq.com) |
| **Testing Approach** | 100% Manual Testing (Zero Automation) |
| **Last Updated** | September 2026 |

---

## 1. Introduction
This Test Plan outlines the testing strategy, scope, environment, and execution criteria for performing independent black-box manual testing on the publicly accessible **Tata CLiQ** web application ([https://www.tatacliq.com](https://www.tatacliq.com)). 

Tata CLiQ is a premier Indian multi-category e-commerce platform offering fashion, footwear, electronics, and luxury goods. This project represents an independent portfolio initiative designed by a 2026 B.Tech Computer Science graduate to demonstrate practical, industry-standard software testing methodologies, rigorous test case design, and defect reporting.

---

## 2. Objective
The primary objectives of this manual testing initiative are:
1. Validate that core user journeys (Search, Filter, Product Details, Wishlist, Shopping Bag, and Checkout Address Validation) operate in accordance with expected e-commerce functional behavior.
2. Verify frontend input validations, boundary values, error messages, and usability across desktop browsers.
3. Identify, isolate, and document reproducible functional and UI defects with complete reproduction steps and supporting evidence.
4. Establish bidirectional traceability between Functional Requirements, Test Scenarios, Test Cases, and Defects via a Requirement Traceability Matrix (RTM).
5. Demonstrate hands-on test planning, execution tracking, and defect management without relying on automated frameworks.

---

## 3. Application Under Test (AUT)
* **Application Name:** Tata CLiQ Web Platform
* **Primary URL:** `https://www.tatacliq.com`
* **Architecture:** Single Page Application (SPA) built using React.js, interacting with Tata Digital SSO for authentication.
* **Access Level:** Public web interface via desktop browsers. No internal database, server console, or proprietary API access is available or claimed.

---

## 4. Scope

### 4.1 In-Scope Functionality
The scope is strictly limited to manually verifiable, publicly accessible features:
* **Authentication & Account:** Mobile number field validation, OTP trigger screen UI, countdown timer, authenticated session persistence, and logout.
* **Product Search:** Keyword search (brand, category), partial search with auto-suggest dropdown, special characters, whitespace trimming, and zero-result error handling.
* **Filter & Sorting:** Single/multi-facet filtering (Brand, Price, Discount, Color), filter chip removal, *Clear All*, and sorting (Price: Low to High, High to Low, Popularity).
* **Product Details Page (PDP):** Information display consistency, mandatory size selection validation before adding to bag, 6-digit delivery pincode serviceability check, and size guide modal.
* **Wishlist Management:** Guest user authentication prompt on wishlist addition, authenticated wishlist persistence, item removal, and moving items to bag.
* **Shopping Bag (Cart):** Bag counter synchronization, quantity modifications (boundaries 1 to 5), line item removal confirmation, price summary calculation ($Total = MRP - Discount + Delivery$), coupon code validation, and empty bag state.
* **Checkout Address Validation:** Navigation to checkout address step, blank form validation, mandatory field checks, 6-digit pincode format, and 10-digit mobile number validation.

### 4.2 Out-of-Scope Functionality
To preserve professional authenticity and avoid fabricated test passes:
* **Payment Gateway Transactions:** Actual payment authorization via Credit/Debit cards, Net Banking, or UPI is excluded because Tata CLiQ does not provide a public mock payment sandbox. Real money will not be spent.
* **Post-Order Management:** Order tracking, cancellation, and returns are excluded as they require genuine paid commercial orders.
* **Backend Database Testing:** Direct SQL queries against Tata CLiQ's production database are out of scope due to lack of internal database access.
* **Automated Testing:** Selenium, Playwright, Cypress, Postman automation, and CI/CD pipelines are strictly excluded per the manual testing charter.

---

## 5. Testing Approach
Testing is conducted strictly using **Black-Box Manual Testing** methodologies. Testing design techniques applied include:
* **Equivalence Partitioning (EP):** Dividing inputs into valid and invalid classes (e.g. mobile number formats, search terms, coupon codes).
* **Boundary Value Analysis (BVA):** Testing boundary values on input fields ($Min - 1, Min, Min + 1, Max - 1, Max, Max + 1$) such as 10-digit mobile numbers, 6-digit pincodes, and 1–5 cart quantities.
* **Decision Table Testing:** Documenting logical combinations of inputs and business conditions determining cart checkout eligibility and delivery fees.
* **Error Guessing:** Formulating test cases based on typical user misbehaviors (empty submissions, rapid clicks, special characters).
* **Exploratory Testing:** Performing charter-based sessions to uncover unscripted edge-case bugs.

---

## 6. Testing Types
The following testing types are executed within the scope:
1. **Functional Testing:** Verifying that features perform according to specified requirements.
2. **UI / Usability Testing:** Checking labels, layout, button states, modal popups, and visual alignment.
3. **Positive Testing:** Validating expected workflows using valid inputs.
4. **Negative Testing:** Verifying graceful error handling when invalid, boundary-violating, or unexpected data is provided.
5. **Smoke Testing:** Executing a dedicated 9-case suite to ensure critical application paths function before detailed testing.
6. **Sanity Testing:** Performing focused checks on specific modified or defective components (e.g., cart quantity adjustments).
7. **Regression Testing:** Executing a 12-case regression subset to ensure core functionalities remain unbroken.
8. **Retesting:** Re-executing failed test cases once defects are simulated or resolved.

---

## 7. Test Environment

| Component | Specification |
| :--- | :--- |
| **Operating System** | Microsoft Windows 11 Home / Pro (64-bit) |
| **Primary Browser** | Google Chrome (Latest Stable v128.0+, 1920x1080 resolution) |
| **Secondary Browser** | Microsoft Edge (Chromium-based Latest Stable v128.0+) |
| **Network** | High-speed broadband connection (50+ Mbps) |
| **Tools Used** | Microsoft Excel, Markdown Editor, Git, GitHub, Snipping Tool / Greenshot |

---

## 8. Test Data
All test data is prepared beforehand and stored in `03-Test-Design/Test-Data.xlsx`:
* **Valid Data:** Real personal 10-digit Indian mobile number, authentic product keywords (e.g. *"Puma"*, *"Running Shoes"*), valid delivery pincodes (e.g. `400001` Mumbai, `110001` Delhi).
* **Invalid Data:** Short mobile numbers (9 digits), alphanumeric phone inputs, non-existent 6-digit pincodes (`000000`), non-existent search keywords (`xyznonexistent999`), invalid coupon codes (`FAKEDISCOUNT999`).

---

## 9. Entry Criteria
Manual test execution commences only when:
1. The Tata CLiQ web application (`https://www.tatacliq.com`) is online and accessible.
2. The Test Plan, Requirements, and Test Cases are reviewed and finalized.
3. Desktop test environment (Chrome/Edge browsers) is configured with clean cache/cookies.
4. Test data dictionary is verified.

---

## 10. Exit Criteria
Testing concludes when:
1. 100% of planned test cases (52 test cases) have been manually executed and logged.
2. All critical Smoke test cases have passed.
3. All identified defects have been logged with reproduction steps, severity, priority, and screenshots in `05-Defect-Management/`.
4. Requirement Traceability Matrix (RTM) shows 100% mapping coverage.
5. Test Summary Report is authored and delivered.

---

## 11. Assumptions
1. Tata CLiQ's public web servers remain operational with typical network uptime during testing sessions.
2. Public product catalog data (prices, discounts, stock availability) remains accessible without administrative restrictions.
3. Personal mobile number is available to receive genuine SMS OTPs for authentication testing.

---

## 12. Risks and Mitigation

| Risk | Impact | Likelihood | Mitigation Strategy |
| :--- | :---: | :---: | :--- |
| **Product Out of Stock During Testing:** An item selected for testing becomes unavailable mid-run. | High | Medium | Identify 2–3 alternate fashion products with active stock across multiple sizes as backups. |
| **OTP Rate Limiting:** Rapid login attempts trigger temporary SMS blocking on Tata Digital SSO. | Medium | Medium | Space out authentication test cases; execute search and navigation tests between login attempts. |
| **UI Updates by Tata CLiQ:** Live website layout or DOM changes during project timeline. | Medium | Low | Record execution dates clearly and capture dated screenshot evidence immediately during execution. |
| **Dynamic Price Fluctuations:** Live discounts or prices change during multi-day testing. | Low | High | Verify mathematics relative to current displayed MRP and discounts, rather than hardcoded rupees. |
| **Inability to Test Live Payments:** Lack of payment sandbox prevents end-to-end checkout execution. | High | High | Explicitly define scope boundary at Address Form validation; document payment as *Out of Scope*. |

---

## 13. Limitations
* **Zero Backend Access:** Testers cannot inspect internal database tables (`ORDERS`, `USERS`, `PAYMENTS`) or server application logs.
* **No Payment Sandbox:** Order placement, payment confirmation, and post-order tracking cannot be executed.
* **Browser Scope:** Manual testing is conducted on Windows 11 using Google Chrome and Microsoft Edge. Mobile browsers (iOS Safari / Android Chrome) are excluded from the primary desktop suite.

---

## 14. Deliverables
At the conclusion of this project, the following artifacts are produced:
1. **Test Plan** (`01-Project-Documentation/Test-Plan.md`)
2. **Scope & Objectives** (`01-Project-Documentation/Scope-and-Objectives.md`)
3. **Test Environment Specification** (`01-Project-Documentation/Test-Environment.md`)
4. **Functional Requirements** (`02-Requirements/Functional-Requirements.md`)
5. **Test Scenarios** (`03-Test-Design/Test-Scenarios.xlsx` and `.md`)
6. **Manual Test Cases** (`03-Test-Design/Test-Cases.xlsx` and `.md`)
7. **Test Data Dictionary** (`03-Test-Design/Test-Data.xlsx` and `.md`)
8. **Test Design Techniques Guide** (`03-Test-Design/Test-Design-Techniques.md`)
9. **Test Execution Report** (`04-Test-Execution/Test-Execution-Report.xlsx` and `.md`)
10. **Defect Management Log & Summary** (`05-Defect-Management/Bug-Reports.xlsx` and `Defect-Summary.md`)
11. **Requirement Traceability Matrix** (`06-RTM/Requirement-Traceability-Matrix.xlsx` and `.md`)
12. **Test Summary Report** (`07-Test-Summary/Test-Summary-Report.md`)
13. **Execution Evidence Guidelines** (`08-Test-Evidence/README.md`)
