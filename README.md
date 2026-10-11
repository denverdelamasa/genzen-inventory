# 📦 Genzen Inventory System (v2.0 - Archived)

> **Core Mission:** A hyper-efficient, lightweight Excel/VBA inventory manager designed to automate stock logging, eliminate manual entry errors, and run effortlessly on low-spec legacy hardware.

---

## 🧭 System Overview

### ✨ Key Capabilities
* **Automated Data Routing:** Transfers form entries into a centralized, protected database sheet without manual cell editing.
* **One-Click Macro Automation:** Fast stock-in and stock-out logging via embedded VBA macros.
* **Ultra-Low Hardware Footprint:** Specifically engineered and optimized to run on low-end dual-core laptops with just **2 GB RAM** on **Windows 7** and **Office 2010**.

---

## ⚙️ Minimum System Requirements

* **Software:** Microsoft Excel (Desktop: 2010, 2016, 2019, 2021, or M365). *Web browser versions are unsupported.*
* **File Format:** Macro-Enabled Workbook (`.xlsm`) or Binary Workbook (`.xlsb`).
* **OS:** Windows 7, 8, 10, or 11.
* **Hardware:** 2 GB RAM + Dual-Core CPU.

---

## 🚀 Quick Start & Workflow

### 1. Enable Macros
When opening the file, click **Enable Content** in the yellow warning bar. Without this, buttons will not function.

### 2. Standard Operating Steps
1. **Input Data:** Navigate to `Inventory_Form` and fill in required details (Item Name, Quantity, Category, Date).
2. **Commit Record:** Click the **Add Record** button to trigger the VBA macro, auto-generate records, and append them to `Inventory_DB`.
3. **Verify:** Check `Inventory_DB` to confirm the log.

---

## 🏗️ Architecture & Safety Rules

### 🧠 Logic Breakdown
$$\text{Inventory\_Form (UI)} \xrightarrow{\quad \text{VBA Macros} \quad} \text{Inventory\_DB (Storage)}$$

### ⚠️ Critical Rules
* **DO NOT** edit `Inventory_DB` manually unless correcting a typo.
* **DO NOT** rename or delete worksheets (breaks macro bindings).
* **DO NOT** insert/delete rows manually in the DB sheet.

---

## 🛠️ Quick Troubleshooting

| Issue | Cause | Solution |
| :--- | :--- | :--- |
| **Buttons fail to click** | Macros are disabled | Re-open workbook and select **Enable Content** |
| **Data fails to save** | Blank required fields / VBA error | Ensure all form fields are filled before submitting |
| **Data in wrong columns** | Mapping mismatch | Check cell references inside the VBA script |