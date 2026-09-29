# Tata CLiQ – Test Environment Specification

## 1. Overview
A controlled and standardized test environment is essential for consistent and reproducible manual testing. This document defines the exact hardware, operating system, web browsers, display configurations, and network settings used during manual test execution for the Tata CLiQ portfolio project.

---

## 2. Hardware Configuration

| Component | Specification |
| :--- | :--- |
| **Device Type** | Laptop / Desktop PC |
| **Processor** | Intel Core i5 / AMD Ryzen 5 or equivalent |
| **RAM** | 8 GB / 16 GB DDR4 |
| **Storage** | 512 GB NVMe SSD |
| **Display Resolution** | 1920 x 1080 (Full HD, 100% DPI Scaling) |

---

## 3. Software & Operating System

| Component | Specification |
| :--- | :--- |
| **Operating System** | Microsoft Windows 11 Home / Pro (64-bit) |
| **Build Version** | Version 23H2 / 24H2 |
| **Spreadsheet Tool** | Microsoft Excel 2021 / Office 365 / OpenPyXL |
| **Documentation Editor** | Visual Studio Code / Markdown Editor |
| **Version Control** | Git 2.40+ & GitHub Desktop |
| **Evidence Tool** | Windows Snipping Tool / Greenshot |

---

## 4. Browser Environment Matrix

To ensure realistic cross-browser evaluation without over-claiming unsupported browsers, manual testing is executed across the two most widely used modern desktop browsers in India:

| Browser Name | Engine | Version | Testing Role | Status |
| :--- | :--- | :--- | :--- | :---: |
| **Google Chrome** | Chromium / Blink | v128.0+ (64-bit) | **Primary Test Browser** (100% of cases) | Active |
| **Microsoft Edge** | Chromium / Blink | v128.0+ (64-bit) | **Secondary Cross-Check** (Smoke & UI cases) | Active |
| **Mozilla Firefox** | Gecko | Latest | Out of Scope (Not explicitly executed) | Excluded |
| **Apple Safari** | WebKit | Latest | Out of Scope (macOS environment not used) | Excluded |

> **Authenticity Note:** Only Google Chrome and Microsoft Edge on Windows 11 were used for execution. Firefox and Safari are explicitly excluded to maintain portfolio integrity.

---

## 5. Network & Connectivity

| Parameter | Configuration |
| :--- | :--- |
| **Connection Type** | High-Speed Fiber Broadband (Wi-Fi 802.11ac / Ethernet) |
| **Bandwidth** | 50 Mbps – 100 Mbps download & upload |
| **Latency** | < 25 ms ping to Indian CDN edge servers |
| **Location / Region** | India (Domestic Indian IP address, required for Tata CLiQ's domestic storefront) |

---

## 6. Test Environment Hygiene & Pre-Execution Steps

To avoid caching artifacts or stale session states impacting test results:
1. **Cache & Cookie Clear:** Browser cache, local storage, and cookies are cleared prior to starting a test execution run.
2. **Incognito / Guest Browsing:** Authentication and unauthenticated guest test cases are verified in clean Incognito/Private browsing windows to guarantee zero residual session cookies.
3. **Browser Zoom:** Browser zoom is strictly locked at 100% (`Ctrl + 0`) to ensure UI alignment and responsive layout accuracy.
4. **Third-Party Extensions:** Ad-blockers, script-blockers, and translation extensions are completely disabled during testing to avoid interference with Tata CLiQ's scripts.
