# 📦 **Genzen Pharmaceutical Trading Inventory System – Overview**
*User-Friendly Guide (v2.0)*

---

## 🧭 **Overview**

This Inventory Excel System is designed to:

Record and manage inventory entries
Store data in a centralized database sheet
Use buttons/macros to automate tasks (no manual encoding in DB)

## 🚀 **Getting Started**
```
- **Enable Macros (IMPORTANT)**
- When opening the file:
- Click "Enable Content"
- If you don’t → buttons will not work
```

## 🧾 **Main Workflow**
➤ Step 1: Go to Inventory_Form
```
- This is where all inputs happen.
- Fill in required fields such as:
- Item Name
- Quantity
- Category / Type
- Date / Other details (depending on your setup)
⚠️ Do NOT leave required fields blank
```

➤ Step 2: Click Add Record Button
```
- Saves your input into Inventory_DB
- Automatically:
- Finds next available row
- Generates ID (if implemented)
- Transfers form data → database
```

➤ Step 3: Verify Entry
```
- Go to Inventory_DB
- Confirm that your data was added correctly
```

➤ Step 4: Clear / Reset Form (if applicable)
```
- Some versions auto-clear after submission
- If not, use Clear Button (if available)
```

## 🧠 System Logic (Simple Explanation)
Inventory_Form = Input Layer
Inventory_DB = Storage Layer
Buttons = Trigger VBA Macros


*You never edit the DB manually unless fixing errors.*

# ⚠️ Do’s and Don’ts
## ✅ DO:
- Always input data through the form
- Double-check entries before submitting
- Keep sheet names unchanged
- 
## ❌ DON’T:
- Rename sheets (breaks macros)
- Delete hidden/config sheets
- Edit VBA unless you know what you’re doing
- Insert rows manually in DB (can break ID logic)
- 
## 🛠 Common Issues
**❌ Button not working**
→ Macros are disabled

**❌ Data not saving**
→ Missing required fields OR macro error

**❌ Wrong data placement**
→ Form mapping mismatch (dev issue)
