# Tata CLiQ – Functional Requirements Specification

## 1. Overview
This document specifies the 20 functional requirements established for the manual testing of the Tata CLiQ web application. Each requirement is derived directly from live application exploration and serves as the baseline for test scenario design, test case creation, and traceability mapping.

---

## 2. Requirements Matrix

| Requirement ID | Module | Requirement Statement | Priority | Type |
| :--- | :--- | :--- | :---: | :---: |
| **REQ_AUTH_001** | Authentication & Account | The system shall validate that the mobile number field in the Sign In modal accepts only a valid 10-digit Indian mobile number, rejecting blank submissions, lengths $<10$ or $>10$ digits, and non-numeric characters with inline error messages. | High | Validation |
| **REQ_AUTH_002** | Authentication & Account | Upon submission of a valid 10-digit mobile number, the system shall transition to the OTP verification screen, initiate a 30-second countdown timer, and disable the 'Resend OTP' action until the timer expires. | High | Functional |
| **REQ_AUTH_003** | Authentication & Account | The system shall maintain an authenticated user session across page navigation and provide a functional 'Sign Out' / 'Logout' option within the profile menu that terminates the session completely. | High | Functional |
| **REQ_SRCH_001** | Product Search | The system shall execute search queries for valid brand names (e.g. *Puma*, *Levi's*) and generic categories (e.g. *Running Shoes*), displaying relevant product cards with an accurate item count on the search results page. | High | Functional |
| **REQ_SRCH_002** | Product Search | The system shall display an auto-suggest recommendation dropdown beneath the search bar when 2 or more characters are entered, allowing users to click a suggestion to navigate to its results. | Medium | UI / Functional |
| **REQ_SRCH_003** | Product Search | The system shall handle non-existent, invalid, or gibberish search terms (e.g. *xyznonexistent999*) by displaying a clear 'No matching products found' message accompanied by suggested search tips or popular categories. | High | Negative / Error Handling |
| **REQ_SRCH_004** | Product Search | The system shall sanitize search inputs by automatically trimming leading and trailing whitespace and handling special characters without throwing system errors or application crashes. | Medium | Boundary / Validation |
| **REQ_FLTR_001** | Filter & Sort | The system shall allow users on a Product Listing Page (PLP) to apply single or multiple filter facets (Brand, Price Range, Discount, Color) and dynamically refresh the product catalog without a full page reload. | High | Functional |
| **REQ_FLTR_002** | Filter & Sort | The system shall display active filters as removable chips/tags at the top of the grid and provide a 'Clear All' button that resets all checkboxes and restores the full catalog. | High | Functional |
| **REQ_FLTR_003** | Filter & Sort | The system shall sort catalog products accurately according to selected sorting criteria, including 'Price: Low to High' (ascending order), 'Price: High to Low' (descending order), and 'Popularity'. | High | Functional |
| **REQ_PROD_001** | Product Details Page | The Product Details Page (PDP) shall present complete and consistent product data including Brand, Product Title, Selling Price (₹), MRP (strikethrough), Discount %, Tax inclusion disclaimer, and Image carousel. | High | UI / Functional |
| **REQ_PROD_002** | Product Details Page | The system shall enforce mandatory size selection for apparel and footwear products, displaying a prominent alert message if the user clicks 'ADD TO BAG' without choosing a size. | High | Validation |
| **REQ_PROD_003** | Product Details Page | The system shall validate 6-digit delivery pincodes, displaying estimated delivery dates and shipping fees for serviceable pincodes, and an error message for unserviceable or malformed pincodes. | High | Functional / Validation |
| **REQ_WSHL_001** | Wishlist | The system shall prompt unauthenticated users to authenticate via the Sign In modal when clicking the Wishlist heart icon, and add the product directly to Wishlist if the user is authenticated. | High | Functional |
| **REQ_WSHL_002** | Wishlist | The system shall allow authenticated users to view saved items on the dedicated Wishlist page, remove items, or transfer items directly into the Shopping Bag. | Medium | Functional |
| **REQ_CART_001** | Shopping Bag | When an item is added from the PDP, the system shall dynamically increment the header bag counter badge by 1 and display identical item details (Title, Brand, Selected Size, Unit Price) in the Shopping Bag. | High | Functional |
| **REQ_CART_002** | Shopping Bag | The system shall allow users to modify item quantity between a minimum boundary of 1 and a maximum boundary of 5, instantly recalculating line item totals and the Order Summary. | High | Boundary / Functional |
| **REQ_CART_003** | Shopping Bag | The system shall display a confirmation modal prior to removing an item from the bag and display a dedicated 'Your Bag is Empty' layout with a 'Continue Shopping' CTA when zero items remain. | Medium | UI / Functional |
| **REQ_CART_004** | Shopping Bag | The system shall calculate the Order Summary accurately based on: $Total = Bag MRP - Discount + Delivery Fee - Coupon$, and display an error message if an invalid coupon code is entered. | High | Business Logic / Validation |
| **REQ_CHK_001** | Checkout Address | The Delivery Address form shall enforce mandatory fields (Full Name, 10-digit Mobile Number, 6-digit Pincode, Address lines), auto-populate City and State upon valid pincode entry, and validate numerical boundaries. | High | Validation / Functional |

---

## 3. Requirement Verification & Traceability Note
Every requirement in this specification maps directly to at least one Test Scenario in `03-Test-Design/Test-Scenarios.xlsx` and at least one Manual Test Case in `03-Test-Design/Test-Cases.xlsx`. Traceability is tracked bidirectionally in `06-RTM/Requirement-Traceability-Matrix.xlsx`.
