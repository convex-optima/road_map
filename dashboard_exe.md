# Inventory Health Dashboard Requirement 📊

## Objective

Design an **Inventory Health Dashboard** to monitor inventory status by **SKU and warehouse**, identify stock risk/opportunity, and support replenishment / transfer decisions using current stock, short-term forecast, inbound pipeline, and target inventory policy.

## Dashboard Goal

The dashboard should help users answer:

* Do we have enough stock by SKU and warehouse?
* Which SKUs are at risk of stockout in the next 10 days?
* Which SKUs are overstocked versus required coverage?
* Will confirmed inbound arrivals solve the shortage?
* Where should operations prioritize replenishment, transfer, or escalation?

***

## Scope

The dashboard should cover inventory health at:

* **SKU–Warehouse level**
* Optional aggregation by:
* Warehouse
* Category / cluster
* Brand
* Seller / business unit
* Inventory status group

Time horizon:

* **Current stock**
* **Forecast for next 10 days**
* **New inbound for next 10 days**

***

## Required Data Inputs
### 1. Current Stock

At SKU–Warehouse level:

* SKU ID
* Warehouse ID / name
* Current on-hand stock
* Available stock
* Inventory snapshot date/time

### 2. Forecast Data for Next 10 Days

At SKU–Warehouse–Date level:
* Forecast date
* Forecasted outbound demand / sales
* Daily forecast quantity
* Cumulative forecast quantity for next 10 days

### 3. New Inbound for Next 10 Days

At SKU–Warehouse–ETA date level:
* ETA date
* Inbound quantity

### 4. SKU Information

At SKU master level:
* SKU ID
* Category / sub-category
* Brand
* Product status *(active/inactive)*
* Size / storage type *(if available)*

### 5. Inventory Policy / Target Parameters

At SKU–Warehouse level:

* Required DoC (Days of Cover)
* Safety stock DoC

***
## Dashboard Views

### 1. Summary View

High-level KPIs:

* Total SKUs monitored
* Number of SKU-WH combinations at stockout risk
* Number below safety stock
* Number below required DoC
* Number healthy
* Number overstocked
* Total shortage quantity
* Total excess quantity

### 2. SKU–Warehouse Detail View

Detailed table with:

* SKU ID
* SKU name
* Warehouse
* Current stock
* Forecast next 10 days
* Inbound next 10 days
* Net stock after 10 days
* Current DoC
* Required DoC
* Safety stock
* Gap to safety stock
* Inventory health status

### 3. Trend / Projection View

For selected SKU–Warehouse:

* Daily projected stock position for next 10 days
* Daily forecast consumption
* Daily inbound ETA
* Estimated stockout date

### 4. Warehouse Summary View

Aggregated by warehouse:

* Total SKUs at risk
* Top shortage SKUs
* Total shortage units
* Total excess units
* Risk rate by warehouse

***

## Required Filters

The dashboard should support filters for:
* Warehouse
* SKU
* Category
* Inventory health status
* Forecast date range *(default next 10 days)*

***

## Sorting / Prioritization

Users should be able to sort by:
* Highest shortage quantity
* Earliest projected stockout date
* Lowest projected DoC
* Highest forecast demand
* Highest excess quantity

***

## Alert / Highlighting Logic

Use conditional formatting to highlight:

* Red: stockout risk / below safety stock
* Yellow: below required DoC
* Green: healthy
* Blue / grey: overstock

Optional alerts:

* Projected stockout within 3 days

***

## Output / Deliverables

The dashboard should provide:

* Executive summary page
* Warehouse-level monitoring page
* SKU–Warehouse detailed page
* Exportable detailed table for operational follow-up

***
