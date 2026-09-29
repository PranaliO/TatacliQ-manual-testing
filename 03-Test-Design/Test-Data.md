# Tata CLiQ – Test Data Dictionary

| Data ID | Module | Data Parameter | Test Data Values | Testing Purpose |
| :--- | :--- | :--- | :--- | :--- |
| TD_AUTH_001 | Authentication | Valid Mobile Number | `Personal active Indian mobile number (e.g. 98XXXXXXXX)` | Positive testing for OTP triggering and authentication |
| TD_AUTH_002 | Authentication | Invalid Mobile - Short (9 digits) | `987654321` | Boundary Value Analysis (N-1) validation |
| TD_AUTH_003 | Authentication | Invalid Mobile - Long (11 digits) | `98765432101` | Boundary Value Analysis (N+1) validation |
| TD_AUTH_004 | Authentication | Invalid Mobile - Non Numeric | `98765ABCDE, test@phone` | Equivalence Partitioning negative testing |
| TD_AUTH_005 | Authentication | Empty Mobile Field | `'' (empty string)` | Mandatory required field validation |
| TD_SRCH_001 | Product Search | Valid Brand Keyword | `Puma, Nike, Titan, Fastrack, Westside` | Valid exact keyword product retrieval |
| TD_SRCH_002 | Product Search | Valid Generic Category Keyword | `Running Shoes, Cotton T-Shirt, Analog Watch` | Category catalog search validation |
| TD_SRCH_003 | Product Search | Partial Keyword | `den, snea, cas` | Auto-suggest recommendation trigger |
| TD_SRCH_004 | Product Search | Non-Existent Query | `xyznonexistent999, abcd1234efgh5678` | Zero-results handling validation |
| TD_SRCH_005 | Product Search | Special Characters | `!@#$%^&*()_+` | Input sanitization and resilience |
| TD_SRCH_006 | Product Search | Whitespaces | `   sneakers   ` | Whitespace trimming boundary test |
| TD_FLTR_001 | Filter & Sort | Single Brand Facet | `Brand: Levi's, Puma, U.S. Polo` | Single facet filtering accuracy |
| TD_FLTR_002 | Filter & Sort | Price Range Facet | `Rs. 1000 - Rs. 1999` | Numeric range constraint testing |
| TD_FLTR_003 | Filter & Sort | Multi-Facet Combination | `Brand: Puma + Discount: 40% and above` | Multi-condition filter conjunction (AND) |
| TD_FLTR_004 | Filter & Sort | Sorting Criteria | `Price -- Low to High, Price -- High to Low, Popularity` | Catalog sort order validation |
| TD_PROD_001 | Product Details | Valid Serviceable Pincode | `400001 (Mumbai), 110001 (Delhi), 560001 (Bangalore)` | Pincode serviceability & delivery date calculation |
| TD_PROD_002 | Product Details | Invalid Pincode - Short (5 digits) | `40001` | BVA lower boundary check (N-1) |
| TD_PROD_003 | Product Details | Invalid Pincode - Non-Existent | `000000, 999999` | Unserviceable / non-existent pincode error handling |
| TD_PROD_004 | Product Details | Apparel Size Selection | `S, M, L, XL, XXL` | Mandatory size selection validation |
| TD_CART_001 | Shopping Bag | Quantity Lower Boundary | `1` | Minimum permissible cart item quantity |
| TD_CART_002 | Shopping Bag | Quantity Upper Boundary | `5` | Maximum permissible cart item quantity (BVA max) |
| TD_CART_003 | Shopping Bag | Invalid Coupon Code | `FAKEDISCOUNT999, TATA100OFF` | Negative coupon validation |
| TD_CHK_001 | Checkout Address | Valid Delivery Address | `Name: Rahul Sharma, Phone: 9876543210, Pin: 400001, Flat: 402 Palm Heights, Street: MG Road` | Valid address creation and checkout advancement |
| TD_CHK_002 | Checkout Address | Empty Address Fields | `All fields blank` | Mandatory field validation highlighting |
