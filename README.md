# Distribution Management Dashboard

A two-page interactive dashboard to track nutrition product distribution across blocks, suppliers, vehicles and beneficiaries. Built for **Britannia Nutrition Foundation** <!-- Remove the organization name if your organization does not permit it -->.

> **Note:** All data shown in the screenshots is dummy data used for testing. The production dashboard is internal to the organization and its link cannot be shared publicly.

---

## Table of Contents
- [Problem Statement](#problem-statement)
- [Solution](#solution)
- [Features](#features)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [My Role](#my-role)
- [Impact](#impact)
- [Data Validation Notes](#data-validation-notes)
- [Future Improvements](#future-improvements)

---

## Problem Statement

Nutrition products such as food baskets, kitchen garden kits, mosquito nets and CBB were being distributed across multiple blocks and storage locations, but tracking was fragmented and largely manual. This caused several problems:

- **No single view of stock:** teams could not easily tell how much stock was received, how much was distributed and how much was still available at each block.
- **Stock mismatches went unnoticed:** without automatic calculations, errors such as distributing more than was received were hard to catch.
- **Weak supplier and vehicle tracking:** it was difficult to see which suppliers contributed the most or which vehicle types were used for deliveries.
- **Unclear beneficiary coverage:** there was no quick way to check which beneficiary groups (e.g., pregnant and lactating mothers) were being reached, or which blocks and ACs were covered.
- **Slow reporting:** consolidating data from different sources for review meetings took significant manual effort.

## Solution

A centralized dashboard that gives program teams visibility into received vs. distributed quantities, available stock, supplier contribution and beneficiary coverage, filterable by date range and block.

---

## Features

### Page 1: Distribution Overview
- **KPI cards:** total quantity received, total distribution entries, total blocks covered, products received
- **Quantity by block:** bar chart comparing blocks
- **Distribution management table:** product-wise quantity with heat-map shading
- **Type of vehicle used:** donut chart of transport modes
- **Distribution trend:** quantity over time
- **Supplier-wise quantity:** ranked supplier table with inline bars
- **Recent records:** latest entries with date, block, product and quantity

### Page 2: Stock & Beneficiary Analysis
- **KPI cards:** quantity received, quantity distributed, available stock, ACs covered, distribution transactions
- **Type of beneficiary covered:** donut chart (e.g., pregnant/lactating mothers)
- **Distribution by block officers:** quantity in vs. quantity out
- **Total ACs by block:** coverage comparison
- **Product-wise quantity distributed by AC**
- **AC distribution trend**
- **Product-wise available stock at block**
- **AC-level table:** received, distributed, available stock and distribution % with in-cell bars
- **Filters:** date range and block selector

---

## Screenshots

### Distribution Overview
<img width="691" height="518" alt="Screenshot 2026-11-11 194420" src="https://github.com/user-attachments/assets/46bbb467-1495-4bb1-8da7-309f57521719" />


### Stock & Beneficiary Analysis
<img width="553" height="416" alt="Screenshot 2026-11-11 194442" src="https://github.com/user-attachments/assets/951cb9fc-671e-4c50-a454-34e4847bc34a" />

---

## Tech Stack

| Layer | Tool |
|-------|------|
| Visualization | Looker Studio <!-- change if different --> |
| Data source | Google Sheets <!-- change if different --> |
| Data entry | Google Forms <!-- change if different --> |

### Why Looker Studio?

I evaluated a few options before choosing Looker Studio. The decision came down to the needs of a field-driven nonprofit team rather than raw feature count.

| Factor | Why it mattered | Looker Studio |
|--------|-----------------|---------------|
| **Cost** | Nonprofit budgets are limited, and per-user licenses add up quickly when many block officers need access | Free to use and share |
| **Data source fit** | Field data was already being collected in Google Sheets / Forms | Native, direct connectors with no extra ETL step |
| **Access for field teams** | Users are spread across blocks with varying devices and no IT support | Runs in the browser, with no installation needed, and works on mobile |
| **Sharing** | Program managers and block officers needed to view the dashboard without complicated setup | Share by link or email with view-only access |
| **Near real-time updates** | New distribution entries should appear without manual refreshes | Dashboard reflects Sheet updates automatically |
| **Ease of maintenance** | A small team needs to own and update it without specialist skills | Simple drag-and-drop editing and easy to hand over |
| **Interactivity** | Teams needed to slice data by date range and block | Built-in date range controls, filters and cross-chart interaction |

**Alternatives considered**

| Tool | Why I didn't choose it |
|------|------------------------|
| **Power BI** | Very powerful, but sharing dashboards generally requires paid licenses, and it adds setup overhead that wasn't justified for this scope |
| **Tableau** | Strong visuals, but higher cost and a steeper learning curve for a small team to maintain |
| **Excel / Google Sheets charts only** | Fine for quick checks, but hard to keep interactive, shareable and consistent across multiple users |

**Trade-offs I accepted:** Looker Studio has fewer advanced modeling and calculation features than Power BI or Tableau, and large datasets can load slower. For this project's data volume and reporting needs, those limits were acceptable.

---

## My Role

Sole developer of the dashboard. I:
- Designed the data structure and field definitions
- Defined KPIs and calculated fields
- Built both dashboard pages, including charts, tables and filters
- Tested the dashboard end to end with dummy data before go-live

---

## Impact

- **Centralized visibility:** replaces scattered records with one dashboard showing received quantity, distributed quantity and available stock by block, product and AC.
- **Faster reporting:** program teams can filter by date range and block instead of compiling reports manually. <!-- Add time saved once live, e.g., "reduced weekly reporting effort from X hours to Y minutes" -->
- **Better stock control:** the quantity in vs. out comparison for each block officer and AC makes shortages, excess stock and data-entry errors visible immediately.
- **Improved accountability:** distribution is traceable by supplier, block officer, vehicle type and date, with a recent-records table for quick audits.
- **Data-driven planning:** trend charts and block-wise comparisons help teams decide where to send stock next and which blocks need more attention.
- **Beneficiary tracking:** the beneficiary-type breakdown helps confirm distribution reaches the intended target groups.
- **Scalable design:** built and tested with dummy data, and designed to switch to live data without redesign. <!-- Add adoption details once live, e.g., "used by X block officers across Y blocks" -->

---

## Data Validation Notes

During testing, the dashboard surfaced a few entries where available stock appeared negative (distributed quantity greater than received quantity). This is expected with test data, and it shows how the dashboard highlights data-entry and stock mismatches. In production, this can be reduced by:
- Adding validation rules at the data-entry stage
- Flagging negative stock rows with conditional formatting
- Reconciling stock periodically against physical counts

---

## Future Improvements

- Alerts for low or negative stock
- Block-wise targets vs. achievement tracking
- Export to PDF for monthly review meetings
- Role-based views for block officers and program managers

---

## Disclaimer

This repository contains only documentation and screenshots of a dashboard built with dummy data. No real beneficiary, supplier or organizational data is included.
