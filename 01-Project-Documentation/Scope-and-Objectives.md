# Tata CLiQ – Scope and Objectives

## 1. Project Purpose
This document provides a comprehensive description of the functional scope, testing objectives, and operational boundaries for the independent manual testing portfolio project based on the **Tata CLiQ** e-commerce platform.

---

## 2. Primary Objectives
The manual testing effort is structured to address the following key questions about the application:

1. **System Accessibility & Landing:** Does the Tata CLiQ homepage load completely and render all primary navigation elements, search inputs, and department links cleanly?
2. **User Authentication:** Does the Tata Digital SSO modal handle valid 10-digit Indian mobile numbers, reject malformed or short numbers, and transition properly to the OTP verification screen?
3. **Session Management:** Does an authenticated user session persist across page reloads and internal navigation, and does logging out completely terminate the session?
4. **Search Accuracy & Resilience:** Does entering a brand or category keyword return relevant catalog items? Does the system gracefully handle non-existent queries without crashing or showing blank screens?
5. **Auto-Suggest Usability:** Does the search bar offer dynamic keyword recommendations upon typing 2+ characters, and can users navigate directly from suggestions?
6. **Filtering & Refinement:** Does selecting individual or multiple filter facets (Brand, Price, Discount, Color) dynamically update the product grid accurately? Do filter chips allow seamless individual removal and full *Clear All* reset?
7. **Sorting Order:** Does sorting products by *Price: Low to High* and *Price: High to Low* accurately arrange items in ascending and descending numeric order?
8. **Product Details Integrity:** Does the PDP present complete and consistent product information (Title, Images, Brand, Selling Price, MRP, Discount %, and Taxes)?
9. **Selection Validation:** Does the PDP prevent adding an apparel or footwear item to the shopping bag when a size has not been selected?
10. **Delivery Availability Check:** Does entering a 6-digit delivery pincode validate format boundaries and display estimated delivery dates accurately?
11. **Wishlist Interactions:** Are unauthenticated users prompted to sign in when clicking the wishlist icon, and do authenticated users experience accurate wishlist synchronization across pages?
12. **Cart Item Management:** Does adding an item to the shopping bag increment the header cart badge? Can users modify quantities within permissible boundaries (1 to 5)?
13. **Price Calculation Accuracy:** Does the Shopping Bag order summary calculate prices accurately according to the business rule:
   $$\text{Total Payable} = \text{Bag MRP} - \text{Bag Discount} + \text{Delivery Fee} - \text{Coupon Discount}$$
14. **Checkout Address Validation:** Does the delivery address form validate mandatory fields and correctly enforce 6-digit pincode and 10-digit mobile number boundaries?
15. **Traceability & Defect Documentation:** Are all functional requirements bidirectionally traced to test scenarios and test cases, and are all defects documented with clear reproduction steps?

---

## 3. In-Scope Modules & Verifiable Features

| Module | Features In Scope |
| :--- | :--- |
| **1. Authentication & Account** | Sign In modal trigger, 10-digit mobile number format validation, blank input validation, non-numeric character rejection, OTP screen UI, 30s countdown timer, logout workflow, session persistence. |
| **2. Product Search** | Brand keyword search, generic category search, partial search auto-suggest dropdown, zero-result keyword handling, special character input resilience, whitespace trimming, search clear icon. |
| **3. Filter & Sort** | Single facet filtering (Brand), price range filtering, multi-facet combination (Brand + Discount), filter chip removal, *Clear All* reset, sorting by Price (Low to High, High to Low), and Popularity. |
| **4. Product Details Page (PDP)** | Product information display, price/MRP consistency, image carousel, mandatory size selection prompt, 6-digit pincode serviceability check, Size Guide modal, product specs accordion. |
| **5. Wishlist** | Guest authentication prompt, authenticated wishlist addition, header badge increment, wishlist page item display, item deletion, and moving items to shopping bag. |
| **6. Shopping Bag (Cart)** | Header bag counter update, PDP-to-Cart data consistency, quantity modification (Min: 1, Max: 5), deletion confirmation modal, empty bag state, mathematical order summary calculation, coupon validation. |
| **7. Checkout Address Validation** | Navigation from bag to checkout, empty address form mandatory checks, 6-digit pincode validation, auto-population of City/State, 10-digit mobile validation, order summary match. |

---

## 4. Out-of-Scope Modules & Documented Boundaries

| Out-of-Scope Area | Technical Rationale for Exclusion |
| :--- | :--- |
| **Real Payment Transactions** | Tata CLiQ does not provide a public payment sandbox or test credit card gateway. Completing real payments requires spending personal funds for non-commercial purposes. Scope strictly halts at the Payment Method selection screen. |
| **Order Placement & Invoicing** | Generating commercial tax invoices and real order records cannot be done without payment. |
| **Order Tracking, Returns & Cancellations** | Requires actively dispatched commercial packages. Cannot be tested authentically without placing real orders. |
| **Internal Database Verification** | Direct SQL inspection (`SELECT * FROM orders`) is not possible as Tata CLiQ does not expose internal database access to the public. SQL skills are demonstrated separately in the interview preparation section. |
| **Internal APIs & Microservices** | Direct API payload testing via Postman is excluded; testing is strictly black-box UI testing. |
| **Automated Testing** | Selenium, Cypress, Playwright, and CI/CD pipelines are excluded per the Manual Testing portfolio charter. |
