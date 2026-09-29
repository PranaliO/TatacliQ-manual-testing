# Tata CLiQ – Test Execution Report

> **Status:** Pending Manual Execution by Candidate
> **Total Cases:** 52 | **Executed:** 0 | **Pending:** 52

| Test Case ID | Module | Priority | Type | Expected Result | Actual Result | Status | Defect ID |
| :--- | :--- | :---: | :--- | :--- | :--- | :---: | :---: |
| TC_AUTH_001 | Authentication | High | Positive | Sign In modal opens cleanly, displaying Tata Digital / Tata CLiQ logo, mobile number input field with +91 country prefix, and Continue CTA. | Not Executed | Not Executed | - |
| TC_AUTH_002 | Authentication | High | Negative | System displays inline validation error: 'Please enter a valid 10-digit mobile number' and 'Continue' button remains disabled or blocks progress. | Not Executed | Not Executed | - |
| TC_AUTH_003 | Authentication | Medium | Negative | The field does not accept non-numeric characters; only digits 0-9 are allowed to be typed, or inline error indicates invalid character input. | Not Executed | Not Executed | - |
| TC_AUTH_004 | Authentication | High | Negative | System displays validation message 'Please enter your mobile number' and does not proceed to OTP screen. | Not Executed | Not Executed | - |
| TC_AUTH_005 | Authentication | High | Positive | System transitions to OTP screen displaying 'Enter OTP sent to +91-XXXXX' with 6 OTP input boxes and active countdown timer. | Not Executed | Not Executed | - |
| TC_AUTH_006 | Authentication | Medium | Functional | 'Resend OTP' is disabled during active countdown and becomes active/clickable once the countdown completes. | Not Executed | Not Executed | - |
| TC_AUTH_007 | Authentication | High | Positive | User session is terminated, header reverts to display 'Sign In / Register', and restricted profile areas are no longer accessible without logging in. | Not Executed | Not Executed | - |
| TC_AUTH_008 | Authentication | Low | UI | Modal closes smoothly, background page becomes interactive again, and page URL/scroll position remains intact. | Not Executed | Not Executed | - |
| TC_SRCH_001 | Product Search | High | Positive | Search results page loads with URL containing search query; displays Puma branded products, item count header, and relevant brand filters pre-checked. | Not Executed | Not Executed | - |
| TC_SRCH_002 | Product Search | High | Positive | Search results page displays catalog of running shoes across multiple brands with accurate breadcrumb and total product count. | Not Executed | Not Executed | - |
| TC_SRCH_003 | Product Search | Medium | UI / Functional | Auto-suggest dropdown appears listing relevant suggestions (e.g. 'denim jacket', 'denim shirt', 'denims') with matching letters highlighted. | Not Executed | Not Executed | - |
| TC_SRCH_004 | Product Search | High | Negative | System displays user-friendly zero-results message: 'We couldn't find any matches for "xyznonexistent999"' and displays helpful suggestions/trending categories. | Not Executed | Not Executed | - |
| TC_SRCH_005 | Product Search | Medium | Negative | Application does not crash or throw unhandled exceptions (500 errors); sanitizes input and gracefully displays no results or ignores invalid characters. | Not Executed | Not Executed | - |
| TC_SRCH_006 | Product Search | Low | Boundary | Application trims whitespace and executes query for 'sneakers', displaying relevant sneakers search results identical to untrimmed query. | Not Executed | Not Executed | - |
| TC_SRCH_007 | Product Search | Medium | UI | Search field is instantly cleared, focus remains in input field, and auto-suggest dropdown closes. | Not Executed | Not Executed | - |
| TC_SRCH_008 | Product Search | Medium | Functional | Browser navigates directly to search results page for 'Watches for Men' displaying matching watches catalog. | Not Executed | Not Executed | - |
| TC_FLTR_001 | Filter & Sort | High | Positive | Product grid refreshes dynamically; only Levi's products are displayed, a 'Levis' filter chip appears at top, and total product count decreases accordingly. | Not Executed | Not Executed | - |
| TC_FLTR_002 | Filter & Sort | High | Positive | Every displayed product card shows discounted selling price between ₹1000 and ₹1999 inclusive. | Not Executed | Not Executed | - |
| TC_FLTR_003 | Filter & Sort | High | Positive | Two filter chips ('Puma', '40% and above') are displayed at top. All rendered products belong to Puma and have at least 40% discount. | Not Executed | Not Executed | - |
| TC_FLTR_004 | Filter & Sort | High | Functional | 'Red' chip disappears, 'Color' checkbox unchecks automatically, and product list expands to show Puma products in all colors. | Not Executed | Not Executed | - |
| TC_FLTR_005 | Filter & Sort | Medium | Functional | All filter chips are removed, all checkboxes in filter panel are cleared, and product grid restores original unfiltered listing and count. | Not Executed | Not Executed | - |
| TC_FLTR_006 | Filter & Sort | High | Positive | Products reload in ascending price order where Product 1 Price <= Product 2 Price <= Product 3 Price. | Not Executed | Not Executed | - |
| TC_FLTR_007 | Filter & Sort | Medium | Positive | Products reload in descending price order where Product 1 Price >= Product 2 Price >= Product 3 Price. | Not Executed | Not Executed | - |
| TC_PROD_001 | Product Details | High | UI | All product attributes display cleanly without broken images, overlapping text, or missing price values. | Not Executed | Not Executed | - |
| TC_PROD_002 | Product Details | High | Negative | System does not add item to bag; highlights size selection section with error/toast message 'Please select a size'. | Not Executed | Not Executed | - |
| TC_PROD_003 | Product Details | High | Positive | Button state changes to 'ADDED TO BAG' or 'GO TO BAG', header Bag icon badge increments by 1, and confirmation toast appears. | Not Executed | Not Executed | - |
| TC_PROD_004 | Product Details | High | Positive | System validates pincode and displays estimated delivery date (e.g. 'Delivery by 03 Oct') and delivery charges/free delivery notice. | Not Executed | Not Executed | - |
| TC_PROD_005 | Product Details | Medium | Negative | System blocks submission and displays inline error 'Please enter a valid 6-digit pincode'. | Not Executed | Not Executed | - |
| TC_PROD_006 | Product Details | Medium | Negative | System displays error message: 'Delivery not available for this pincode' or 'Please enter a valid pincode'. | Not Executed | Not Executed | - |
| TC_PROD_007 | Product Details | Low | UI | Size chart popup modal appears displaying measurements in cm/inches across sizes; closes cleanly when clicking 'X'. | Not Executed | Not Executed | - |
| TC_PROD_008 | Product Details | Low | UI | Section expands smoothly displaying detailed fabric/care specs, and collapses without page jump. | Not Executed | Not Executed | - |
| TC_WSHL_001 | Wishlist | High | Negative | Item is not saved secretly; Sign In / Register modal immediately appears prompting user to authenticate. | Not Executed | Not Executed | - |
| TC_WSHL_002 | Wishlist | High | Positive | Heart icon fills solid (active state), toast indicates 'Added to Wishlist', and header Wishlist icon badge increments by 1. | Not Executed | Not Executed | - |
| TC_WSHL_003 | Wishlist | High | Positive | Wishlist page loads displaying product thumbnail, brand, title, selling price, and 'MOVE TO BAG' button. | Not Executed | Not Executed | - |
| TC_WSHL_004 | Wishlist | Medium | Functional | Item is removed from page; page displays 'Your Wishlist is Empty' and header badge decrements to 0. | Not Executed | Not Executed | - |
| TC_WSHL_005 | Wishlist | Medium | Functional | Item is removed from Wishlist and added to Shopping Bag; Bag badge increments by 1. | Not Executed | Not Executed | - |
| TC_CART_001 | Shopping Bag | High | Positive | Bag icon counter updates from 0 to 1 immediately with visual notification. | Not Executed | Not Executed | - |
| TC_CART_002 | Shopping Bag | High | Positive | All attributes in Shopping Bag exactly match the selected product from PDP. | Not Executed | Not Executed | - |
| TC_CART_003 | Shopping Bag | High | Positive | Line total updates to ₹2000 (₹1000 x 2) and Order Summary subtotal doubles accordingly. | Not Executed | Not Executed | - |
| TC_CART_004 | Shopping Bag | High | Boundary | Dropdown lists quantities 1 through 5 only; values >5 are not selectable. | Not Executed | Not Executed | - |
| TC_CART_005 | Shopping Bag | Medium | UI / Functional | Modal closes; product remains intact in Shopping Bag and totals remain unchanged. | Not Executed | Not Executed | - |
| TC_CART_006 | Shopping Bag | High | Positive | Item is removed from bag, bag count decrements, and empty bag state or updated subtotal is displayed. | Not Executed | Not Executed | - |
| TC_CART_007 | Shopping Bag | High | Business Logic | Displayed Total Payable exactly equals (Bag MRP - Bag Discount + Delivery Fee) with zero rounding discrepancies. | Not Executed | Not Executed | - |
| TC_CART_008 | Shopping Bag | Medium | Negative | System displays error: 'Coupon code is invalid or expired' and does not deduct any discount from bag total. | Not Executed | Not Executed | - |
| TC_CART_009 | Shopping Bag | Medium | UI | Page displays empty bag illustration, text 'Your Bag is Empty! Explore our collections', and a prominent 'Continue Shopping' button that redirects to homepage. | Not Executed | Not Executed | - |
| TC_CART_010 | Shopping Bag | Medium | Functional | Item is removed from Shopping Bag, bag count badge decrements by 1, and header wishlist badge increments by 1. | Not Executed | Not Executed | - |
| TC_CHK_001 | Checkout Address | High | Positive | System navigates to Checkout URL, displaying Delivery Address section and order summary on the side. | Not Executed | Not Executed | - |
| TC_CHK_002 | Checkout Address | High | Negative | Validation messages appear under all mandatory fields: Full Name ('Please enter your name'), Mobile Number ('Please enter mobile number'), Pincode ('Please enter pincode'), Flat/House No ('Please enter flat/house no'). | Not Executed | Not Executed | - |
| TC_CHK_003 | Checkout Address | High | Boundary | Inline validation error displays: 'Please enter a valid 6-digit pincode' and prevents auto-fetching city/state. | Not Executed | Not Executed | - |
| TC_CHK_004 | Checkout Address | High | Positive | City field auto-populates with 'Mumbai' and State field auto-populates with 'Maharashtra'. | Not Executed | Not Executed | - |
| TC_CHK_005 | Checkout Address | High | Boundary | Error message displays: 'Please enter a valid 10-digit mobile number' and form submission is blocked. | Not Executed | Not Executed | - |
| TC_CHK_006 | Checkout Address | High | Positive | Checkout Order Summary amount exactly matches the Bag total with identical line-item itemization. | Not Executed | Not Executed | - |
