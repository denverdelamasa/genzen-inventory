# 📦 Genzen Pharmaceutical Trading Inventory System – Overview
## What It Is
A custom‑built Excel‑based inventory management system designed for a pharmaceutical stockroom. It replaces manual ledgers and scattered spreadsheets with a centralized, automated tool that handles incoming stock, outgoing sales, real‑time updates, and reporting.

## Why It Was Built
- Accuracy – Reduce human error in quantity tracking.

- Efficiency – Automate repetitive tasks (ID generation, total cost calculation, expiry status updates).

- Segregation – Separate exclusive and open market products for focused management.

- Mobile readiness – Works via Remote Desktop on a phone, allowing stockroom workers to update counts on the floor.

- Print readiness – One‑click, always‑up‑to‑date inventory list for physical stocktaking.

### 🔧 Core Features
## 1. Database (Inventory_DB)
- Columns: RecordID, Item, Batch, Quantity, Cost, Expiry, Type, Generic, Brand, Dosage, BoxCount, Total Cost, DateAdded, LastUpdated, Status, Remarks.

- Statuses: Active / Expired / Deleted (soft delete).

- Remarks: Exclusive or Open Market for filtering.
```
Total Cost formula: =Quantity * Cost per piece – updates automatically.
```
## 2. Data Entry Form (Inventory_Form)
- In‑Going: Add new stock (Generic, Brand, Dose, BoxCount, Batch, Quantity, Expiry, Type, Cost, Remarks).

- Out‑Going: Record sales – batch number, expiry date, quantity, total amount. Supports multi‑batch deduction (deducts from largest‑quantity rows first).

- Search: Find and load a record by Brand/Generic + Dose (displays item, batch, cost, remarks).

- Clear Form: Resets all fields.

## 3. Smart Combobox for Batch Numbers
- Filters as you type.

- Shows only active batches.

- Press Enter to move to next field.

## 4. Automatic Expiry Management
- UpdateExpiredStatus – Marks rows as "Expired" when expiry date passes.

- HighlightExpiryStatus – Colors rows: red for expired, yellow for expiring within 30 days.

## 5. Sorting & Filtering
- Macros to sort by: Generic, Quantity (desc), Total Cost (desc), Unit Price (desc), Type, Expiry, Date Added, Last Updated.

- Filters to show only Active, Expired, or Deleted items.

## 6. Dashboard (Dashboard)
- Quick Stock Lookup – Search by batch or item name; results show Item, Batch, Qty, Expiry, Unit Price, Last Updated.

- Minimal, focused layout – only what’s useful.

## 7. Exclusive & Open Market Sheets
- ExclusiveCount and OpenMarketCount sheets.

- Each shows RecordID, Item, Batch, Expiry, Current Qty, and a New Qty column.

- Refresh – pulls current data from main DB.

- Sync – writes new quantities back to Inventory_DB, updates Total Cost and LastUpdated.

- Keeps exclusive and open market items separate for easier management.

## 8. Outgoing Multi‑Batch Deduction
- When recording a sale, the macro finds all rows with the same batch number and expiry month/year.

- Deducts from the largest quantity row first.

- If one row isn't enough, it automatically uses multiple rows until the order is fulfilled.

- Logs a single outgoing record with total quantity and amount.

## 9. Print Inventory (PrintInventory)
- Automatically refreshed after any inventory change.

- Lists all active items, sorted alphabetically by Item.

- Data starts at row 9 (rows 1‑8 are free for custom headers/titles).

- Auto‑stamps current date in cell D7 (format: Wednesday, April 8, 2026).

- Ready to print at any time.

## 10. RecordID Generation
- Custom format: GZ-PHARMA-XXXX (e.g., GZ-PHARMA-0686).

- Numeric part stored in Config sheet and auto‑incremented.

## 11. Data Integrity & Helpers
- ProperCaseGenericNames – Formats generic names to proper case.

- GenerateItemForAllRows – Rebuilds the Item column from Generic, Brand, Dose, Type, BoxCount.

- ConvertTotalCostToFormula – Ensures Total Cost uses a formula, not static values.

### 🚀 How It All Connects
# Add/Update/Delete → updates main DB, refreshes batch dropdown, exclusive/open market lists, print inventory.

# Record Outgoing → reduces stock across one or multiple rows, logs to Outgoing_DB, refreshes dependent sheets.

# Dashboard → instant search without leaving the main view.

# Exclusive/Open Market sheets → focused editing for specific product groups.

# Print sheet → always‑ready, printer‑friendly list.

### ✅ Why This Works for You
# You can do everything from your phone (via Remote Desktop) – no VBA limitations on mobile.

# The system grows with you – easy to add columns (just update constants).

# No more manual calculations – formulas and macros handle the math.

# Separate exclusive/open market workflows reduce clutter.

# One click prints a complete, sorted inventory list.
