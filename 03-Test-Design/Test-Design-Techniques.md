# Tata CLiQ – Test Design Techniques & Strategy Guide

## 1. Overview
In professional manual testing, test cases must not be written randomly. They must be systematically derived using formal **Black-Box Test Design Techniques** to maximize test coverage while minimizing redundant execution. This document details how **Boundary Value Analysis (BVA)**, **Equivalence Partitioning (EP)**, **Decision Tables**, and **Error Guessing** were practically applied to the Tata CLiQ web application, alongside our **Smoke**, **Sanity**, **Regression**, and **Retesting** frameworks.

---

## 2. Boundary Value Analysis (BVA)

BVA focuses on the boundaries of input domains, where defects frequently cluster due to off-by-one errors in conditional statements (`<` vs `<=`). BVA tests values at:
$$\text{Min} - 1,\quad \text{Min},\quad \text{Min} + 1,\quad \text{Max} - 1,\quad \text{Max},\quad \text{Max} + 1$$

### BVA Field 1: Indian Mobile Number (Authentication & Address Form)
* **Observed Boundary:** Must be exactly 10 numeric digits.

| Boundary Point | Value Tested | Nature | Expected Result | Related Test Case |
| :--- | :---: | :---: | :--- | :--- |
| **Min - 1 (9 digits)** | `987654321` | Invalid | Inline error: *"Please enter a valid 10-digit mobile number"*; submit disabled. | `TC_AUTH_002`, `TC_CHK_005` |
| **Min / Exact (10 digits)** | `9876543210` | Valid | Accepted; advances to OTP verification screen or saves address. | `TC_AUTH_005`, `TC_CHK_001` |
| **Max + 1 (11 digits)** | `98765432101` | Invalid | Field restricts typing to 10 characters or displays error on 11th digit. | `TC_AUTH_002` |

### BVA Field 2: Delivery Pincode (PDP & Address Form)
* **Observed Boundary:** Must be exactly 6 numeric digits.

| Boundary Point | Value Tested | Nature | Expected Result | Related Test Case |
| :--- | :---: | :---: | :--- | :--- |
| **Min - 1 (5 digits)** | `40001` | Invalid | Error: *"Please enter a valid 6-digit pincode"*; blocks auto-lookup. | `TC_PROD_005`, `TC_CHK_003` |
| **Min / Exact (6 digits)** | `400001` | Valid | Accepted; displays estimated delivery date and populates City/State. | `TC_PROD_004`, `TC_CHK_004` |
| **Max + 1 (7 digits)** | `4000012` | Invalid | Input field restricts typing beyond 6 digits. | `TC_PROD_005` |

### BVA Field 3: Shopping Bag Item Quantity Selector
* **Observed Boundary:** Tata CLiQ allows purchasing between 1 and 5 units per item in the cart.

| Boundary Point | Value Tested | Nature | Expected Result | Related Test Case |
| :--- | :---: | :---: | :--- | :--- |
| **Below Min (0 units)** | `0` | Invalid | Dropdown does not contain '0'. User must click 'Remove' button instead. | `TC_CART_005` |
| **Min (1 unit)** | `1` | Valid | Allowed. Calculates price for single unit. | `TC_CART_002` |
| **Min + 1 (2 units)** | `2` | Valid | Allowed. Multiplies price by 2; updates Order Summary. | `TC_CART_003` |
| **Max - 1 (4 units)** | `4` | Valid | Allowed. Multiplies price by 4. | `TC_CART_003` |
| **Max (5 units)** | `5` | Valid | Allowed. Maximum purchasable quantity per item reached. | `TC_CART_004` |
| **Max + 1 (6 units)** | `6` | Invalid | Dropdown stops at 5; values $>5$ are unavailable. | `TC_CART_004` |

---

## 3. Equivalence Partitioning (EP)

Equivalence Partitioning divides input data into partitions of equivalent data from which test cases can be derived. One test from each partition is sufficient to represent the entire class.

### EP Table: Search Input Field
| Partition Class | Input Category | Representative Test Data | Expected Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- |
| **Valid Partition 1** | Recognized Brand | `"Puma"`, `"Levis"` | Renders matching branded products grid | `TC_SRCH_001` |
| **Valid Partition 2** | Generic Category | `"Running Shoes"`, `"T-Shirts"` | Renders category catalog products | `TC_SRCH_002` |
| **Valid Partition 3** | Partial Keyword | `"den"`, `"sne"` | Displays dynamic auto-suggest dropdown | `TC_SRCH_003` |
| **Invalid Partition 1** | Non-Existent String | `"xyznonexistent999"` | Displays *"No matching products found"* | `TC_SRCH_004` |
| **Invalid Partition 2** | Special Characters | `"!@#$%^&*()"` | Sanitizes input; displays no results safely | `TC_SRCH_005` |
| **Boundary Partition** | Whitespace Strings | `"   sneakers   "` | Automatically trims spaces and runs search | `TC_SRCH_006` |

### EP Table: Shopping Bag Coupon Code Field
| Partition Class | Input Category | Representative Test Data | Expected Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- |
| **Valid Partition** | Active Coupon Code | `"CLIQPICK10"` (when active) | Applies discount; subtracts from Bag Total | `TC_CART_007` |
| **Invalid Partition** | Fictitious / Expired Code | `"FAKEDISCOUNT999"` | Error: *"Coupon code is invalid or expired"* | `TC_CART_008` |
| **Blank Partition** | Empty String | `""` (Clicking Apply) | Prompt: *"Please enter a coupon code"* | `TC_CART_008` |

---

## 4. Decision Table Testing

Decision tables represent complex business rules where multiple input conditions combine to dictate system actions.

### Decision Table: Checkout Advancement & Free Delivery Business Rule
* **Conditions:**
  1. $C_1$: User Authentication Status (Guest vs Logged-In)
  2. $C_2$: Shopping Bag Item Count ($> 0$)
  3. $C_3$: Bag Total Value ($\ge ₹1499$ for Free Delivery threshold)
* **Actions:**
  1. $A_1$: Prompt User to Sign In
  2. $A_2$: Enable 'Checkout' button
  3. $A_3$: Apply Free Delivery (₹0 fee)
  4. $A_4$: Add Standard Delivery Fee (e.g. ₹99 fee)

| Rule # | $C_1$: Logged In? | $C_2$: Bag Items $> 0$? | $C_3$: Bag Total $\ge ₹1499$? | Action Taken | Related Test Cases |
| :---: | :---: | :---: | :---: | :--- | :--- |
| **R1** | No | No | No | Disable Checkout CTA; Show Empty Bag state ($A_1$ not triggered) | `TC_CART_009` |
| **R2** | No | Yes | No | Trigger Sign In modal on Checkout click ($A_1$) | `TC_WSHL_001`, `TC_CHK_001` |
| **R3** | No | Yes | Yes | Trigger Sign In modal on Checkout click ($A_1$) | `TC_CHK_001` |
| **R4** | Yes | Yes | No | Allow Checkout ($A_2$), Charge Standard Delivery Fee ($A_4$) | `TC_CART_007`, `TC_CHK_001` |
| **R5** | Yes | Yes | Yes | Allow Checkout ($A_2$), Grant Free Delivery ($A_3$) | `TC_CART_007`, `TC_CHK_001` |

---

## 5. Error Guessing

Error guessing relies on the tester's intuition, domain knowledge of e-commerce pitfalls, and analytical thinking about how users make mistakes.

| Error Guessing Scenario | Anticipated Risk / Failure | Verified Behavior on Tata CLiQ | Test Case ID |
| :--- | :--- | :--- | :--- |
| **1. Rapid Repeated Clicking on 'ADD TO BAG'** | Race condition causing item quantity to increment multiple times unintentionally. | System debounces button click; disables button briefly and adds only 1 item. | `TC_PROD_003` |
| **2. Adding Sized Apparel Without Selecting Size** | Application defaults to random size or adds null size to cart. | Application validates size selection and renders inline alert *"Please select a size"*. | `TC_PROD_002` |
| **3. Emptying Bag and Attempting Direct URL Checkout** | Unhandled exception or blank screen when navigating to checkout with 0 items. | Application detects empty cart state and redirects user back to Bag / Homepage. | `TC_CART_009` |
| **4. Entering Spaces-Only in Search Box** | Server treats spaces as valid query and returns erratic 500 error. | Search bar ignores submission or trims spaces, remaining on existing page. | `TC_SRCH_006` |
| **5. Pasting Letters into Phone Number Field** | Form submits corrupted non-numeric string to SMS gateway. | Field strips non-digits immediately on paste or highlights validation error. | `TC_AUTH_003` |
| **6. Clicking 'Remove' on Cart Item and Canceling** | Item disappears prematurely before confirmation. | Confirmation modal appears; clicking 'Cancel' preserves item and total intact. | `TC_CART_005` |

---

## 6. Smoke Testing Suite (9 Critical Cases)

Smoke testing (Build Verification Testing) verifies that the build is stable enough to proceed with comprehensive testing. 9 critical path test cases were selected from our master test suite:

| Case ID | Module | Title | Criticality Rationale |
| :--- | :--- | :--- | :--- |
| **TC_AUTH_001** | Authentication | Verify opening Sign In modal from header | Core gateway for user identity and authenticated features. |
| **TC_AUTH_007** | Authentication | Verify user logout from profile menu | Ensures session security and proper token destruction. |
| **TC_SRCH_001** | Product Search | Verify product search with valid brand keyword | Primary discovery mechanism for 70%+ of e-commerce shoppers. |
| **TC_FLTR_001** | Filter & Sort | Verify applying a single Brand filter | Core product listing refinement mechanism. |
| **TC_PROD_001** | Product Details | Verify mandatory product details displayed on PDP | Assures catalog correctness and pricing display integrity. |
| **TC_PROD_003** | Product Details | Verify adding product to bag with selected size | Primary conversion step connecting browsing to purchasing. |
| **TC_WSHL_002** | Wishlist | Verify adding item to Wishlist as authenticated user | Essential engagement workflow for user retention. |
| **TC_CART_001** | Shopping Bag | Verify product added to bag increments counter | Core cart state synchronization across application header. |
| **TC_CHK_001** | Checkout Address | Verify navigating from Cart to Checkout Address step | Critical checkout initiation path leading to conversion. |

---

## 7. Sanity Testing Strategy

* **Definition:** Sanity testing is a focused subset of testing executed to verify that a specific bug fix or narrow code modification works as intended, without testing the entire application.
* **Demonstrated Application (Simulated):**
  * *Scenario:* A developer reports fixing a bug where the cart subtotal failed to decrease when quantity was reduced from 2 to 1 (`BUG_SIM_001`).
  * *Sanity Execution:* The tester does **not** re-run all 52 test cases. Instead, the tester executes only `TC_CART_003` and `TC_CART_007` to verify that item quantity decrementing and price math recalculate correctly.
  * *Decision:* If sanity passes, the tester authorizes broader regression testing; if sanity fails, the build is immediately rejected.

---

## 8. Regression Testing Suite (12 Targeted Cases)

Regression testing ensures that recent modifications or bug fixes have not adversely affected existing un-modified functionality. 12 existing test cases from the master suite form our regression package:

| Regression TC ID | Module Covered | Regression Focus Area |
| :--- | :--- | :--- |
| **TC_AUTH_002** | Authentication | Validates that authentication input sanitization remains intact. |
| **TC_SRCH_003** | Product Search | Ensures auto-suggest dropdown functionality is unhindered. |
| **TC_SRCH_004** | Product Search | Confirms zero-results error handling continues to fail gracefully. |
| **TC_FLTR_003** | Filter & Sort | Tests multi-facet AND conjunction logic for regressions. |
| **TC_FLTR_005** | Filter & Sort | Verifies that 'Clear All' completely restores default product state. |
| **TC_PROD_002** | Product Details | Verifies mandatory size validation cannot be bypassed. |
| **TC_PROD_005** | Product Details | Confirms pincode boundary checks operate reliably. |
| **TC_CART_003** | Shopping Bag | Verifies line item quantity changes recalculate totals. |
| **TC_CART_005** | Shopping Bag | Confirms cart item removal confirmation modal behaves correctly. |
| **TC_CART_006** | Shopping Bag | Checks item deletion and cart counter decrementing. |
| **TC_CART_008** | Shopping Bag | Validates coupon error handling logic against regressions. |
| **TC_CHK_002** | Checkout Address | Ensures address form mandatory field checks remain active. |

---

## 9. Retesting Workflow

Retesting verifies that a specific defect reported in a previous execution run has been successfully resolved.
```text
Defect Reported (e.g. BUG_SIM_001 on TC_CART_003)
      │
      ▼
Developer Deploys Fix to Environment
      │
      ▼
Tester Re-Executes EXACT Same Steps in TC_CART_003
      │
      ├─► Actual Result = Expected Result? ──► YES ──► Mark Defect 'CLOSED'
      │
      └─► Actual Result != Expected Result? ─► NO  ──► Mark Defect 'REOPENED'
```
