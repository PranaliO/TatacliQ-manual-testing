# Tata CLiQ – Manual Test Scenarios

| Scenario ID | Requirement ID | Module | Scenario Description | Priority | Test Type |
| :--- | :--- | :--- | :--- | :---: | :--- |
| TS_AUTH_001 | REQ_AUTH_001 | Authentication | Verify Sign In modal opens correctly from the homepage header and renders all UI elements. | High | UI |
| TS_AUTH_002 | REQ_AUTH_001 | Authentication | Verify validation handling for invalid mobile number inputs (blank, <10 digits, >10 digits, non-numeric). | High | Negative |
| TS_AUTH_003 | REQ_AUTH_002 | Authentication | Verify entering a valid 10-digit mobile number successfully triggers the OTP verification step. | High | Positive |
| TS_AUTH_004 | REQ_AUTH_002 | Authentication | Verify OTP verification screen UI, 6-digit input boundary, and resend timer behavior. | Medium | Functional |
| TS_AUTH_005 | REQ_AUTH_003 | Authentication | Verify authenticated session persistence across navigation and successful logout functionality. | High | Positive |
| TS_SRCH_001 | REQ_SRCH_001 | Product Search | Verify searching with valid specific brand keywords and generic category terms returns accurate results. | High | Positive |
| TS_SRCH_002 | REQ_SRCH_002 | Product Search | Verify auto-suggest dropdown appears upon entering 2+ characters and allows direct keyword selection. | Medium | UI / Functional |
| TS_SRCH_003 | REQ_SRCH_003 | Product Search | Verify search behavior when searching for non-existent products, special characters, and empty spaces. | High | Negative |
| TS_SRCH_004 | REQ_SRCH_004 | Product Search | Verify search input resilience with leading/trailing whitespaces and mixed letter casing. | Low | Boundary |
| TS_SRCH_005 | REQ_SRCH_004 | Product Search | Verify search bar input clearing mechanism using the clear 'X' icon. | Medium | UI |
| TS_FLTR_001 | REQ_FLTR_001 | Filter & Sort | Verify applying a single facet filter (Brand, Price, Discount, Color) accurately filters product cards. | High | Positive |
| TS_FLTR_002 | REQ_FLTR_001 | Filter & Sort | Verify applying multi-facet filters simultaneously displays intersection of criteria. | High | Positive |
| TS_FLTR_003 | REQ_FLTR_002 | Filter & Sort | Verify individual filter tag removal and 'Clear All' functionality restoring default listing. | High | Functional |
| TS_FLTR_004 | REQ_FLTR_003 | Filter & Sort | Verify sorting products by Price (Low to High, High to Low) and Popularity reorders items correctly. | High | Functional |
| TS_PROD_001 | REQ_PROD_001 | Product Details | Verify Product Details Page displays consistent product info (Brand, Title, Price, MRP, Discount, Images). | High | UI |
| TS_PROD_002 | REQ_PROD_002 | Product Details | Verify mandatory size selection validation when attempting to add an apparel/footwear item to bag. | High | Negative |
| TS_PROD_003 | REQ_PROD_002 | Product Details | Verify selecting an available size enables successful addition to bag with visual feedback. | High | Positive |
| TS_PROD_004 | REQ_PROD_003 | Product Details | Verify delivery pincode checker with valid serviceable, unserviceable, and invalid format pincodes. | High | Validation |
| TS_PROD_005 | REQ_PROD_001 | Product Details | Verify Size Guide modal and product information accordion toggle functionality. | Low | UI |
| TS_WSHL_001 | REQ_WSHL_001 | Wishlist | Verify clicking Wishlist heart icon as unauthenticated guest redirects or prompts Sign In. | High | Negative |
| TS_WSHL_002 | REQ_WSHL_001 | Wishlist | Verify adding item to Wishlist as authenticated user updates header wishlist counter badge. | High | Positive |
| TS_WSHL_003 | REQ_WSHL_002 | Wishlist | Verify Wishlist page item management including item removal and moving item to Shopping Bag. | Medium | Functional |
| TS_CART_001 | REQ_CART_001 | Shopping Bag | Verify adding product from PDP updates Shopping Bag item counter badge and reflects in cart list. | High | Positive |
| TS_CART_002 | REQ_CART_001 | Shopping Bag | Verify cart line item attributes (Image, Title, Selected Size, Unit Price) accurately match PDP. | High | Functional |
| TS_CART_003 | REQ_CART_002 | Shopping Bag | Verify quantity increment and decrement operations recalculate item subtotal correctly. | High | Functional |
| TS_CART_004 | REQ_CART_002 | Shopping Bag | Verify quantity limits at boundaries (Min: 1, Max: 5) prevent invalid quantities. | High | Boundary |
| TS_CART_005 | REQ_CART_003 | Shopping Bag | Verify item deletion workflow from bag including confirmation modal and empty bag screen state. | Medium | Functional |
| TS_CART_006 | REQ_CART_004 | Shopping Bag | Verify Order Summary mathematical calculation and coupon code application validation. | High | Business Logic |
| TS_CHK_001 | REQ_CHK_001 | Checkout Address | Verify proceeding to Checkout from Shopping Bag navigates to the Delivery Address entry screen. | High | Positive |
| TS_CHK_002 | REQ_CHK_001 | Checkout Address | Verify submitting blank Delivery Address form highlights all mandatory fields with error messages. | High | Negative |
| TS_CHK_003 | REQ_CHK_001 | Checkout Address | Verify field format validation on Delivery Address form for 6-digit Pincode and 10-digit Mobile Number. | High | Boundary |
| TS_CHK_004 | REQ_CHK_001 | Checkout Address | Verify entering valid 6-digit pincode auto-fills City and State, and Order Summary matches Cart. | High | Functional |
