# Tata CLiQ – Defect Log & Bug Reports

> **Note on Authenticity:** In accordance with professional standards for a personal manual portfolio, defects are logged only when genuinely observed during execution. To illustrate technical understanding of the **Defect Life Cycle** and **Severity vs. Priority** during job interviews, two clearly labeled simulated defects are included below.

### BUG_SIM_001: Cart item subtotal fails to update dynamically when quantity is decreased from 2 to 1 without page refresh

- **Module:** Shopping Bag
- **Severity:** `High` | **Priority:** `High`
- **Status:** `[SIMULATED DEFECT FOR INTERVIEW DEMO] Closed (Verified after Retest)`
- **Associated Test Case:** `TC_CART_003`
- **Environment:** Windows 11, Google Chrome v128.0 (1920x1080)
- **Reproducibility:** Consistent (100%)

**Steps to Reproduce:**
```
1. Navigate to Shopping Bag.
2. Open Quantity selector dropdown for item.
3. Change quantity from 2 to 1.
4. Observe line total and Order Summary.
```

**Expected Result:** Item line total and Bag subtotal should immediately halve to reflect quantity 1 without requiring page refresh.

**Actual Result:** Item quantity displays 1 in selector, but subtotal and Total Payable retain the price for quantity 2 until page is manually reloaded.

**Evidence Reference:** `BUG_CART_001_qty_mismatch.png`

**QA Lead Note:** Simulated defect created to illustrate the Defect Lifecycle: New -> Assigned -> Fixed -> Retested -> Closed during technical interviews.

---

### BUG_SIM_002: Auto-suggest dropdown remains open and overlaps product grid when search field loses focus by clicking empty background

- **Module:** Product Search
- **Severity:** `Medium` | **Priority:** `Medium`
- **Status:** `[SIMULATED DEFECT FOR INTERVIEW DEMO] Open`
- **Associated Test Case:** `TC_SRCH_003`
- **Environment:** Windows 11, Microsoft Edge v128.0 (1920x1080)
- **Reproducibility:** Consistent (100%)

**Steps to Reproduce:**
```
1. Focus on search input on homepage header.
2. Type 'sho'.
3. Wait for auto-suggest recommendations dropdown to appear.
4. Click on the blank white space on the webpage outside the search bar.
```

**Expected Result:** Auto-suggest dropdown should immediately blur and close when focus moves outside the search input container.

**Actual Result:** Auto-suggest dropdown remains permanently floating over hero banner and category links until a link inside the dropdown is clicked or Escape key is pressed.

**Evidence Reference:** `BUG_SRCH_002_dropdown_overlap.png`

**QA Lead Note:** Simulated defect created to demonstrate Severity vs Priority distinction (UI overlay defect causing moderate annoyance but not blocking transaction).

---

