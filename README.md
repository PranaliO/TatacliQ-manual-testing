# Tata CLiQ – Manual Testing Project

[![Manual Testing Only](https://img.shields.io/badge/Testing%20Type-100%25%20Manual%20Testing-blue.svg)](#)
[![No Automation](https://img.shields.io/badge/Automation-Zero%20Automation-red.svg)](#)
[![Candidate Profile](https://img.shields.io/badge/Candidate-2026%20B.Tech%20Fresher-green.svg)](#)
[![Execution Status](https://img.shields.io/badge/Status-Pending%20Manual%20Execution-orange.svg)](#)

A structured, industry-standard **Manual Testing Portfolio Project** conducted on the live, publicly accessible **Tata CLiQ** web platform ([https://www.tatacliq.com](https://www.tatacliq.com)). 

Designed by a **2026 B.Tech Computer Science graduate** aspiring for roles as **Manual Tester**, **QA Test Engineer**, and **Software Quality Assurance Fresher**.

---

## 📌 Project Overview
This project demonstrates practical, end-to-end **Manual Software Testing** competencies without relying on automated scripts or theoretical abstractions. It showcases complete software testing life cycle (STLC) deliverables: from live application exploration and functional requirement engineering, through black-box test design (BVA, EP, Decision Tables), to test case authoring, execution logging, defect tracking, and requirement traceability.

> **Authenticity Guarantee:** This is an independent portfolio project. It does not claim employment at Tata CLiQ, enterprise internal access, or fabricated test execution passes. All 52 test cases are initialized with `Status = Not Executed` to be tested manually on the live web application.

---

## 🎯 Project Objectives
* **Practical Application of STLC:** Execute a disciplined manual testing process on a high-traffic Indian e-commerce application.
* **Rigorous Test Case Design:** Move beyond trivial tests to design boundary value tests, multi-facet filtering scenarios, mathematical cart calculations, and input validation checks.
* **Defect Reporting & Lifecycle Mastery:** Document reproducible defects with complete environment details, clear reproduction steps, and proper severity/priority classification.
* **Bidirectional Traceability:** Maintain a 100% complete Requirement Traceability Matrix (RTM) linking requirements to test scenarios, test cases, and defects.
* **Interview Readiness:** Build a defensible project that can be explained naturally and thoroughly during technical QA interviews.

---

## 🌐 Application Under Test (AUT)
* **Application:** Tata CLiQ Web Application
* **Storefront URL:** [https://www.tatacliq.com](https://www.tatacliq.com)
* **Platform Type:** Multi-category B2C E-Commerce (Fashion, Footwear, Luxury, Accessories)
* **Interface:** Desktop Web Browser (Google Chrome, Microsoft Edge on Windows 11)

---

## 🧩 Modules / Features Tested
Following live application exploration, 7 core functional areas were verified as accessible and included in scope:

1. **Authentication & Account:** Tata Digital SSO modal, 10-digit mobile number validation, OTP trigger screen, 30s resend timer, authenticated session persistence, and logout.
2. **Product Search:** Exact brand queries, category searches, dynamic auto-suggest recommendations, zero-result handling, special characters, and whitespace trimming.
3. **Product Filtering & Sorting:** Faceted filter panels (Brand, Price, Discount, Color), filter chip removal, *Clear All* reset, and sorting (Price: Low-to-High, Price: High-to-Low, Popularity).
4. **Product Details Page (PDP):** Product attributes consistency, mandatory apparel size selection validation, 6-digit delivery pincode availability checker, and size guide modal.
5. **Wishlist Management:** Guest user authentication prompt, authenticated wishlist saving, item removal, and moving saved items to the Shopping Bag.
6. **Shopping Bag (Cart):** Bag counter synchronization, quantity boundary limits (Min: 1, Max: 5), deletion confirmation modal, empty cart state, order summary math ($Total = MRP - Discount + Delivery$), and coupon validation.
7. **Checkout Address Validation:** Navigation to Checkout, blank form mandatory validation, 6-digit pincode validation, auto-population of City/State, and 10-digit mobile boundary validation.

---

## 🔎 Testing Scope

### In-Scope:
* Functional Testing of all 7 modules on live desktop browsers.
* Frontend input validations, error messages, and negative boundary edge-cases.
* UI layout, alignment, button states, and modal popups.
* Smoke testing, Sanity testing strategy, and Regression suite selection.

### Out-of-Scope (Documented Boundaries):
* **Real Payment Gateway Transactions:** No credit/debit card or UPI payments will be completed. Tata CLiQ does not provide a public payment sandbox, and real money will not be spent solely to generate test passes.
* **Order Placement & Returns:** Order confirmation invoices, courier tracking, and return workflows are excluded as they require placing real paid orders.
* **Internal Database & Server Verification:** No direct SQL access to Tata CLiQ's private databases is available.
* **Automated Testing:** Selenium, Playwright, Cypress, Postman automation, and CI/CD pipelines are excluded per the Manual Testing charter.

---

## 🔬 Testing Types Applied
* **Functional Testing:** Validating features against functional requirement specifications.
* **UI / Usability Testing:** Checking visual labels, button states, modals, and error message clarity.
* **Positive Testing:** Verifying expected valid paths and success messages.
* **Negative Testing:** Testing invalid inputs, missing fields, and unexpected user actions.
* **Smoke Testing:** A dedicated 9-case suite verifying critical core functionality before detailed runs.
* **Sanity Testing:** Focused verification on narrow bug fixes (e.g. cart quantity decrementing).
* **Regression Testing:** A 12-case targeted regression pack ensuring existing features remain intact.
* **Retesting:** Systematic verification of resolved defects against original failed test cases.
* **Exploratory Testing:** A timeboxed session charter (`EXP_SESSION_001`) uncovering unscripted race conditions.

---

## 📐 Test Design Techniques
* **Boundary Value Analysis (BVA):** Applied to 10-digit mobile numbers (9, 10, 11 digits), 6-digit pincodes (5, 6, 7 digits), and Shopping Bag quantity limits (0, 1, 2, 4, 5, 6 units).
* **Equivalence Partitioning (EP):** Applied to search input classes (Valid Brand, Generic Category, Non-Existent, Special Characters) and coupon codes (Valid, Invalid, Blank).
* **Decision Table Testing:** Designed for Shopping Bag checkout eligibility and delivery fee waiver calculations based on login state, cart count, and order value threshold.
* **Error Guessing:** Formulated test cases for rapid button clicking, blank submissions, and session transitions.

---

## 📁 Repository Structure & Artifacts

```text
tatacliq-manual-testing-project/
│
├── README.md                                          <-- Master Project Documentation
│
├── 01-Project-Documentation/
│   ├── Test-Plan.md                                   <-- Master Manual Test Plan
│   ├── Scope-and-Objectives.md                        <-- Detailed Scope Boundaries & Questions
│   └── Test-Environment.md                            <-- Hardware, OS & Browser Configurations
│
├── 02-Requirements/
│   └── Functional-Requirements.md                     <-- 20 Functional Requirements Specification
│
├── 03-Test-Design/
│   ├── Test-Scenarios.xlsx & .md                      <-- 32 Test Scenarios (Excel + Markdown)
│   ├── Test-Cases.xlsx & .md                          <-- 52 Manual Test Cases (Master Suite)
│   ├── Test-Data.xlsx & .md                           <-- Test Data Dictionary (Valid/Invalid Sets)
│   └── Test-Design-Techniques.md                      <-- In-Depth BVA, EP, Decision Tables Guide
│
├── 04-Test-Execution/
│   ├── Test-Execution-Report.xlsx & .md               <-- Execution Log (Status = Not Executed)
│   └── Execution-Summary.md                           <-- Execution SOP & Manual Checklist
│
├── 05-Defect-Management/
│   ├── Bug-Reports.xlsx & .md                         <-- Defect Log (Template + 2 Simulated Bugs)
│   └── Defect-Summary.md                              <-- Severity, Priority & Defect Life Cycle
│
├── 06-RTM/
│   └── Requirement-Traceability-Matrix.xlsx & .md     <-- Bidirectional RTM (100% Traceability)
│
├── 07-Test-Summary/
│   └── Test-Summary-Report.md                         <-- Summary Metrics & Risk-Based Testing
│
└── 08-Test-Evidence/
    └── README.md                                      <-- Screenshot Naming & Capture Guidelines
```

---

## 📊 Test Case & Traceability Metrics Summary

| Module | Requirements | Scenarios | Test Cases | Priority Breakdown (H / M / L) |
| :--- | :---: | :---: | :---: | :---: |
| **Authentication & Account** | 3 | 5 | 8 | 5 High / 2 Medium / 1 Low |
| **Product Search** | 4 | 5 | 8 | 4 High / 3 Medium / 1 Low |
| **Filter & Sort** | 3 | 4 | 7 | 5 High / 2 Medium / 0 Low |
| **Product Details Page (PDP)** | 3 | 5 | 8 | 5 High / 2 Medium / 1 Low |
| **Wishlist Management** | 2 | 3 | 5 | 3 High / 2 Medium / 0 Low |
| **Shopping Bag (Cart)** | 4 | 6 | 10 | 6 High / 4 Medium / 0 Low |
| **Checkout Address Validation** | 1 | 4 | 6 | 6 High / 0 Medium / 0 Low |
| **Total Project Scope** | **20** | **32** | **52** | **34 High / 15 Medium / 3 Low** |

* **Traceability Coverage:** 100% ($20 / 20$ Requirements mapped to Scenarios and Test Cases).
* **Execution Status:** **Pending Manual Execution** by candidate on live browser.

---

## 🐛 Defect Management & Life Cycle
* Defects are documented in `05-Defect-Management/Bug-Reports.xlsx` using 15 standardized attributes including reproduction steps, severity, priority, and screenshots.
* To demonstrate deep understanding of the **Defect Life Cycle** and **Severity vs Priority** during technical interviews, two simulated defects (`BUG_SIM_001` and `BUG_SIM_002`) are included and explicitly labeled as interview teaching examples.

---

## 🛠️ Tools Used
* **Web Browsers:** Google Chrome (v128.0+), Microsoft Edge (v128.0+)
* **Spreadsheets:** Microsoft Excel / OpenPyXL (Cleanly formatted `.xlsx` workbooks)
* **Documentation:** Markdown (GitHub Flavored Markdown)
* **Version Control:** Git & GitHub Desktop
* **Evidence Capture:** Windows Snipping Tool / Greenshot

---

## 💡 Key Learnings & Skills Demonstrated
1. **Critical Thinking:** Moving from casual user exploration to structured QA thinking—identifying edge cases, boundary transitions, and race conditions.
2. **Systematic Test Design:** Applying BVA and EP to minimize redundant test cases while maximizing defect detection capability.
3. **Defect Lifecycle Communication:** Formulating clear, reproducible bug reports that facilitate immediate developer reproduction without back-and-forth ambiguity.
4. **Professional Integrity:** Recognizing and documenting scope limitations (payment gateways, backend access) honestly rather than fabricating fake passes.

---

## ⚠️ Limitations
* Public storefront access only; no backend database or application server log visibility.
* Absence of a public payment sandbox restricts checkout validation to the delivery address step.
* OTP rate-limiting on live production authentication gateways requires paced test execution.

---

## ⚖️ Disclaimer
*This is an independent Manual Testing portfolio project created solely for educational and professional learning purposes. It is not affiliated with, endorsed by, or performed on behalf of Tata CLiQ or Tata Unistore Limited.*
