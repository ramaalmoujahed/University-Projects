# SAP Warehouse Management II Case Study – Detailed Procedures
**Step-by-Step Process for User 563**

---

## Overview

| Field | Details |
|---|---|
| Product | SAP S/4HANA 2023 – Global Bike |
| Focus | Warehouse Management II (Internal Stock Transfer) |
| Level | Beginner |
| Estimated Time | 90 minutes |
| User Number | 563 |

### Scenario
Due to increasing sales output in the San Diego distribution center, management has decided to install a Warehouse Management System. The system needs to be tested by requesting finished goods from the Dallas manufacturing facility and putting them into stock in San Diego using the new WMS.

### Employees Involved
| Role | Name |
|---|---|
| Warehouse Supervisor | Carolin Bruzik |
| Plant Manager | Jennifer Brown |
| Warehouse Employee | Sanjay Datar |
| Goods Receipt Clerk | Yoshi Agawa |

### Material
| Field | Value |
|---|---|
| Material | DXTR1563 |
| Quantity | 10 units |
| Supplying Plant | DL00 (Dallas) |
| Receiving Plant | SD00 (San Diego) |
| Storage Location | FG00 (Finished Goods) |
| Destination Bin | STBN-7-563 |
| Storage Type | 002 (Pallet Storage) |

---

## Step 1: Display Material Inventory
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Stock – Single Material

### Procedure:
1. Navigate to the **Warehouse Management** area on the SAP Fiori Launchpad
2. Open the **"Stock – Single Material"** app
3. Enter **DXTR1563** in the Material field and press **Enter**
4. Write down the stock overview for each plant:

| Plant | Stock Quantity |
|---|---|
| Dallas (DL00) | _______________ |
| Heidelberg | _______________ |
| Hamburg | _______________ |
| Miami | _______________ |
| San Diego (SD00) | _______________ |

5. Click to return to the SAP Fiori Launchpad

> **Expected Outcome:** Current stock levels recorded before ordering

---

## Step 2: Create Stock Transport Order
**Duration:** 10 minutes
**Role:** Plant Manager (Jennifer Brown)
**App:** Create Purchase Order

### Procedure:
1. In the **Warehouse Management** area, open the **"Create Purchase Order"** app
2. Change the purchase order type to **Stock Transport Order**
3. Accept any warning messages by pressing **Enter**
4. Fill in the header details:

| Field | Value |
|---|---|
| Purchasing Org. | US00 |
| Purchasing Group | N00 |
| Company Code | US00 |
| Supplying Plant | DL00 (Dallas) |

5. Press **Enter**
6. Expand the **Item Overview** section
7. Enter the item details:

| Field | Value |
|---|---|
| Material | DXTR1563 |
| PO Quantity | 10 |
| Plant | SD00 (San Diego) |
| Storage Location | FG00 (Finished Goods) |
| Delivery Date | 8 days from today |

8. Confirm entries by pressing **Enter**
9. Click **Save** — the system will assign a unique Stock Transport Order number
10. Note the Stock Transport Order number: _______________
11. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Stock Transport Order created and number assigned

---

## Step 3: Display Material Inventory
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Display Stock Overview

### Procedure:
1. Open the **"Display Stock Overview"** app
2. Enter **DXTR1563** as Material
3. Ensure all other search criteria fields are blank
4. Click **Search/Execute**
5. Observe that Dallas stock remains the same
6. Double-click on **SD00 DC San Diego** to see that **On-Order Stock** is now **10 units**
7. Return to the SAP Fiori Launchpad

> **Expected Outcome:** San Diego shows On-Order Stock of 10 units; Dallas unchanged

---

## Step 4: Display Material Inventory Value
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Display Warehouse Stock

### Procedure:
1. Open the **"Display Warehouse Stock"** app
2. Enter **DXTR1563** as Material
3. Ensure all other search criteria fields are blank
4. Click **Search**
5. Observe that there is **no total value** associated with San Diego yet
6. Return to the SAP Fiori Launchpad

> **Expected Outcome:** No inventory value shown for San Diego

---

## Step 5: Create Goods Issue
**Duration:** 10 minutes
**Role:** Warehouse Employee (Sanjay Datar)
**App:** Post Goods Movement

### Procedure:
1. Open the **"Post Goods Movement"** app
2. Change the Material Document dropdown to **Goods Issue**
3. Adjust the type of Goods Issue to **Purchase Order**
4. Enter your **Stock Transport Order Number** in the blank field
5. Enter **351** as Movement Type
6. If you don't have the TO number, use **F4 help**:
   - Go to the **"Purchasing Documents for Material"** tab
   - Enter **DXTR1563** as Material and search
   - Double-click your order to auto-fill the number
7. Press **Enter**
8. When the order appears, select **OK**
9. Enter **Finished Goods (FG00)** as Storage Location
10. Confirm by pressing **Enter**
11. Click **Save** — note the Material Document Number: _______________
12. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Goods issued from Dallas; Material Document number assigned

---

## Step 6: Display Material Inventory
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Display Stock Overview

### Procedure:
1. Open the **"Display Stock Overview"** app
2. Enter **DXTR1563** as Material
3. Click **Search/Execute**
4. Observe that **Dallas stock has decreased**
5. Double-click on **SD00 DC San Diego** — On-Order Stock of 10 is still showing (goods not yet arrived)
6. Optionally, open **"Stock – Single Material"** app for another view
7. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Dallas stock reduced; San Diego still shows On-Order Stock

---

## Step 7: Display Material Inventory Value
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Display Warehouse Stock

### Procedure:
1. Open the **"Display Warehouse Stock"** app
2. Enter **DXTR1563** as Material
3. Ensure all other search criteria fields are blank
4. Click **Search**
5. Observe that:
   - Dallas value has **decreased**
   - San Diego shows **Transit/Transfer value increased** (value of goods in transit)
6. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Dallas value decreased; San Diego Transit/Transfer value increased

---

## Step 8: Create Goods Receipt
**Duration:** 5 minutes
**Role:** Goods Receipt Clerk (Yoshi Agawa)
**App:** Post Goods Movement

### Procedure:
1. Open the **"Post Goods Movement"** app
2. Change the Material Document dropdown to **Goods Receipt**
3. Adjust type to **Purchase Order**
4. Enter your **Stock Transport Order Number** (use F4 help if needed)
5. Press **Enter**
6. When the order appears, select **OK**
7. Verify the following details:

| Field | Value |
|---|---|
| Plant | SD00 (San Diego) |
| Movement Type | 101 |
| Storage Location | FG00 (Finished Goods) |

8. Click **Save** — note the Material Document Number: _______________
9. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Goods received in San Diego; Material Document number assigned

---

## Step 9: Display Material Inventory
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Stock – Single Material

### Procedure:
1. Open the **"Stock – Single Material"** app
2. Enter **DXTR1563** as Material
3. Observe that **San Diego stock has increased**
4. Open **"Display Stock Overview"** and double-click **SD00 DC San Diego**:
   - On-Order Stock is now **zero**
   - Unrestricted Use stock has been **updated**
5. Return to the SAP Fiori Launchpad

> **Expected Outcome:** San Diego unrestricted stock increased; On-Order Stock = 0

---

## Step 10: Display Material Inventory Value
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Display Warehouse Stock

### Procedure:
1. Open the **"Display Warehouse Stock"** app
2. Enter **DXTR1563** as Material
3. Click **Search**
4. Observe that:
   - **Transit/Transfer value** for San Diego is now **zero**
   - **Unrestricted Amount and Total Value** has increased
5. Return to the SAP Fiori Launchpad

> **Expected Outcome:** San Diego total value updated; Transit value = 0

---

## Step 11: Run Bin Status Report
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Run Bin Status Report

### Procedure:
1. Open the **"Run Bin Status Report"** app
2. In the Initial Screen enter:

| Field | Value |
|---|---|
| Warehouse Number | 100 (San Diego) |
| Storage Bin | STBN*563 |

3. Click **Execute**
4. View the **Bin Status Report Overview** — a list of all storage bins
5. Double-click on one of your storage bins to get detailed information
6. Note: Goods are currently in **temporary bins**, not yet in permanent bins
7. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Bin report displayed; goods confirmed in warehouse but not yet in final bin

---

## Step 12: Create Transfer Order
**Duration:** 10 minutes
**Role:** Goods Receipt Clerk (Yoshi Agawa)
**App:** Display Transfer Requirement – List of Material

### Procedure:
1. Open the **"Display Transfer Requirement – List of Material"** app
   - If not visible, search for it using the search bar
2. Enter the following:

| Field | Value |
|---|---|
| Warehouse Number | 100 (San Diego) |
| Material | DXTR1563 |
| Plant | SD00 |

3. Press **Enter**
4. In the **Transfer Requirements for Material** screen, select the line item for the received goods
5. Click **"Create Transfer Order"**
6. In the **Create TO: Prepare for Putaway** screen, press **Enter** to copy quantity of 10 to the Items section
7. Enter the following details:

| Field | Value |
|---|---|
| Section (Sec) | 001 |
| Destination Bin | STBN-7-563 |
| Storage Type | 002 (Pallet Storage) — use F4 to select |

8. Confirm by pressing **Enter**
9. Click **Save** — note the Transfer Order Number: _______________
10. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Transfer Order created; number assigned

---

## Step 13: Confirm Transfer Order
**Duration:** 5 minutes
**Role:** Goods Receipt Clerk (Yoshi Agawa)
**App:** Confirm Transfer Order

### Procedure:
1. Open the **"Confirm Transfer Order"** app
2. In the Initial Screen enter:

| Field | Value |
|---|---|
| Transfer Order Number | *(from Step 12)* |
| Warehouse Number | 100 |

3. Press **Enter**
4. In the **Confirm Transfer Order Overview** screen, verify:
   - ✅ Material: DXTR1563
   - ✅ Quantity: 10
   - ✅ Destination Bin: STBN-7-563
5. Click **Confirm**
6. System returns a success message
7. Return to the SAP Fiori Launchpad

> **Expected Outcome:** Transfer Order confirmed; goods physically placed in bin STBN-7-563

---

## Step 14: Run Bin Status Report (Final Verification)
**Duration:** 5 minutes
**Role:** Warehouse Supervisor (Carolin Bruzik)
**App:** Run Bin Status Report

### Procedure:
1. Open the **"Run Bin Status Report"** app
2. Enter:

| Field | Value |
|---|---|
| Warehouse Number | 100 (San Diego) |
| Storage Bin | STBN*563 |

3. Click **Execute**
4. In the **Bin Status Report Overview**, observe that **STBN-7-563 is now filled**
5. Click on **STBN-7-563** for detailed information
6. Verify:
   - ✅ Material DXTR1563: **10 units**
   - ✅ Correct storage location confirmed
7. Return to the SAP Fiori Launchpad

> **Expected Outcome:** STBN-7-563 confirmed filled with 10 units of DXTR1563 ✅

---

## 🏆 WM II Challenge – Independent Exercise

### Scenario
The warehouse system is now live. The San Diego distribution center needs **50 silver Deluxe Touring Bikes** to start delivering customers. Since Dallas has no free resources (assembly line problems), the order must come from the **Heidelberg plant (Germany)**. Delivery time: max 10 days.

Upon arrival, goods must be stored in the **same bin as the black Touring Bikes** from this case study.

### Challenge Details

| Field | Value |
|---|---|
| Material | DXTR2### (Silver Deluxe Touring Bike) |
| Quantity | 50 units |
| Supplying Plant | HD00 (Heidelberg) |
| Receiving Plant | SD00 (San Diego) |
| Delivery Time | Max 10 days |
| Destination Bin | Same bin as black Touring Bikes (STBN-7-563) |

### Challenge Steps (Complete Independently)
1. Display material inventory (before ordering)
2. Create Stock Transport Order from Heidelberg (HD00)
3. Display material inventory (after ordering)
4. Display material inventory value
5. Create Goods Issue (from Heidelberg)
6. Display material inventory (after goods issue)
7. Display material inventory value (after goods issue)
8. Create Goods Receipt (in San Diego)
9. Display material inventory (after receipt)
10. Display material inventory value (after receipt)
11. Run Bin Status Report
12. Create Transfer Order → destination bin: **STBN-7-563**
13. Confirm Transfer Order
14. Run Final Bin Status Report → verify 50 units in STBN-7-563

### Success Criteria
- ✅ Stock Transport Order created from Heidelberg
- ✅ Goods Issue posted from Heidelberg
- ✅ Goods Receipt confirmed in San Diego
- ✅ Transfer Order created and confirmed
- ✅ 50 silver Deluxe Touring Bikes stored in bin STBN-7-563
- ✅ All steps completed independently

---

## SAP Transactions Reference

| Step | App Name | Transaction |
|---|---|---|
| Display Stock | Stock – Single Material | MMBE |
| Display Stock Overview | Display Stock Overview | MMBE |
| Display Warehouse Stock | Display Warehouse Stock | MB52 |
| Create Stock Transport Order | Create Purchase Order | ME21N |
| Create Goods Issue | Post Goods Movement | MIGO |
| Create Goods Receipt | Post Goods Movement | MIGO |
| Bin Status Report | Run Bin Status Report | LX01 |
| Create Transfer Order | Display Transfer Requirement | LT0A |
| Confirm Transfer Order | Confirm Transfer Order | LT12 |

---

*SAP UCC Magdeburg – Global Bike Inc. | S/4HANA 2023 | WM II Case Study | User 563*
