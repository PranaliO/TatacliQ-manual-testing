# Tata CLiQ – Test Evidence Repository & Guidelines

## 1. Purpose
This directory stores visual evidence (screenshots and video captures) obtained during manual test execution of the **Tata CLiQ** web application. 

Visual evidence serves as objective proof of test execution, verifies expected UI behavior, and provides developers with immediate visual reproduction evidence for reported defects.

---

## 2. Standardized File Naming Conventions
To maintain strict organization, all captured screenshot files must adhere to the following naming format:

### Test Case Evidence:
```text
TC_<MODULE>_<NUMBER>_<brief_description>.png
```
* *Examples:*
  * `TC_AUTH_001_signin_modal_display.png`
  * `TC_SRCH_001_brand_puma_results.png`
  * `TC_FLTR_003_multifacet_filter.png`
  * `TC_PROD_002_missing_size_alert.png`
  * `TC_CART_007_price_calculation_summary.png`
  * `TC_CHK_002_blank_address_validation.png`

### Defect Evidence:
```text
BUG_<MODULE>_<NUMBER>_<brief_description>.png
```
* *Examples:*
  * `BUG_CART_001_qty_mismatch.png`
  * `BUG_SRCH_002_dropdown_overlap.png`

---

## 3. Screenshot Capture Standards
When taking screenshots during manual execution:
1. **Full Viewport / Clean Context:** Include relevant header and URL indicators so the page context is clear, while avoiding capturing unnecessary background desktop items.
2. **Annotation:** Where helpful, use red bounding boxes or arrows to highlight the specific element (e.g. error message, incorrect subtotal, active filter chip).
3. **Image Format:** Save in clean `.png` format to preserve text readability and sharp font rendering.
4. **Zero Vanity Files:** Capture evidence only for key validation milestones, boundary edge-cases, and every failing test case / defect report. Do not flood the directory with duplicate repetitive images.

---

## 4. Current Directory Status
> **Status:** Pending Manual Execution. Evidence files will be populated here as you manually run test cases on live Tata CLiQ using Windows Snipping Tool or Greenshot.
