# SAP Warehouse Management Case Study - Detailed Procedures

## Step-by-Step Process for User 563

### Step 1: Create Purchase Order
**Duration**: 10 minutes
**Role**: Plant Manager (Jennifer Brown)
**App**: Manage Purchase Orders

**Procedure**:
1. Navigate to Manage Purchase Orders in the Warehouse Management area
2. Create a new purchase order with the following details:
   - Document Type: NB (Standard PO)
   - Supplier: 103563
   - Purchasing Group: N00
3. Add first item:
   - Material: KPAD1563
   - Plant: SD00 (San Diego)
   - Quantity: 50
   - Unit Price: 40 USD
4. Click to go to Purchase Order Item screen
5. In Delivery details tab, enter Storage Location: TG00
6. In Schedule lines tab, enter Delivery Date: 8 days from today
7. Click to add second item
8. Add second item:
   - Material: EPAD1563
   - Plant: SD00 (San Diego)
   - Quantity: 50
   - Unit Price: 40 USD
9. Repeat storage location and delivery date entries
10. Save the purchase order

**Expected Outcome**: Purchase order number assigned and confirmed

---

### Step 2: Display Material Inventory
**Duration**: 5 minutes
**Role**: Plant Manager (Jennifer Brown)
**App**: Stock - Single Material

**Procedure**:
1. Open the "Stock - Single Material" app
2. Enter Material: KPAD1563
3. Press Enter
4. Observe that unrestricted-use stock in San Diego is zero
5. Click on the Stock History icon for DC San Diego
6. View the stock history of material KPAD1563 in SD TG00
7. Repeat the same procedure for Material: EPAD1563
8. Return to SAP Fiori Launchpad

**Expected Outcome**: Stock confirmed as zero before goods receipt

---

### Step 3: Display Material Inventory Value
**Duration**: 5 minutes
**Role**: Plant Manager (Jennifer Brown)
**App**: Display Warehouse Stock

**Procedure**:
1. Open "Display Warehouse Stock" app
2. Enter Material: KPAD1563
3. Ensure all other search criteria fields are blank
4. Click search
5. Observe that all values are currently zero
6. Repeat for Material: EPAD1563
7. Return to SAP Fiori Launchpad

**Expected Outcome**: All inventory values show as zero

---

### Step 4: Receive Goods
**Duration**: 5 minutes
**Role**: Goods Receipt Clerk (Yoshi Agawa)
**App**: Post Goods Receipt for Purchasing Document

**Procedure**:
1. Open "Post Goods Receipt for Purchasing Document" app
2. In Purchasing document field, enter your purchase order number
3. If needed, use F4 help and search for your PO:
   - Enter search criteria: 563
   - Double-click on your purchase order to select it
4. Select "Individual slip" for printing
5. Click on Material KPAD1563 line to view details
6. Verify the following details:
   - Storage Location: Trading Goods (TG00)
   - Stock Type: Unrestricted-Use
7. Check the "Delivery Completed" checkbox
8. Click to confirm
9. Repeat for Material EPAD1563 with same verification steps
10. Ensure both lines are selected
11. Click to save the receipt
12. Note the Material Document Number assigned
13. Return to SAP Fiori Launchpad

**Expected Outcome**: Material document number assigned; goods in temporary bins

---

### Step 5: Display Material Inventory (After Receipt)
**Duration**: 5 minutes
**Role**: Plant Manager (Jennifer Brown)
**App**: Stock - Single Material

**Procedure**:
1. Open "Stock - Single Material" app
2. Enter Material: KPAD1563
3. Press Enter
4. Observe that unrestricted-use stock in San Diego has increased to 50 units
5. Click on the Stock History icon for SD San Diego
6. View the updated stock history
7. Repeat for Material: EPAD1563
8. Return to SAP Fiori Launchpad

**Expected Outcome**: Stock shows 50 units for each material

---

### Step 6: Display Material Inventory Value (After Receipt)
**Duration**: 5 minutes
**Role**: Plant Manager (Jennifer Brown)
**App**: Display Warehouse Stock

**Procedure**:
1. Open "Display Warehouse Stock" app
2. Enter Material: KPAD1563
3. Ensure all other search criteria are blank
4. Click search
5. Observe the inventory value: 50 units × 40 USD = 2,000 USD
6. Repeat for Material: EPAD1563
7. Expected value: 2,000 USD (50 × 40)
8. Return to SAP Fiori Launchpad

**Expected Outcome**: Inventory values updated to 2,000 USD each

---

### Step 7: Run Bin Status Report
**Duration**: 5 minutes
**Role**: Warehouse Supervisor (Carolin Bruzik)
**App**: Run Bin Status Report

**Procedure**:
1. Open "Run Bin Status Report" app
2. In the Initial Screen, enter:
   - Warehouse Number: 100 (San Diego Warehouse)
   - Storage Bin: STBN563
3. Click to execute
4. View the Bin Status Report Overview
5. Observe all storage bins for the warehouse
6. Double-click on one storage bin to get detailed information
7. Note: Ordered materials are in temporary bins, not yet in permanent bins
8. Return to SAP Fiori Launchpad

**Expected Outcome**: Bin status displayed; materials confirmed in warehouse

---

### Step 8: Create Transfer Order
**Duration**: 10 minutes
**Role**: Warehouse Employee (Sunil Gupta)
**App**: Display Transfer Requirement – List for Material

**Procedure**:
1. Open "Display Transfer Requirement – List for Material" app
2. Enter the following:
   - Warehouse Number: 100 (San Diego)
   - Material: KPAD1563
   - Plant: SD00
3. Press Enter
4. View the Transfer Requirements for Material screen
5. Observe line item for purchase order received goods
6. Ensure the line is selected
7. Click the "Create Transfer Order" button
8. In the "Create TO" screen, the system shows Prepare for Putaway
9. Press Enter to copy quantity of 50 from Palletization to Items section
10. Enter the following:
    - Sec: 001
    - Destination Bin: STBN-1-563
    - Storage Type: Select "Shelf Storage" using F4
11. Press Enter to confirm entries
12. Click to save the transfer order
13. If warnings appear, ignore them by pressing Enter
14. Note the Transfer Order Number assigned
15. Repeat the entire procedure for Material: EPAD1563
    - Use same destination bin: STBN-1-563
    - Save second transfer order and note the number
16. Return to SAP Fiori Launchpad

**Expected Outcome**: Two transfer orders created with transfer order numbers

---

### Step 9: Confirm Transfer Order
**Duration**: 10 minutes
**Role**: Warehouse Employee (Sunil Gupta)
**App**: Confirm Transfer Order

**Procedure**:
1. Open "Confirm Transfer Order" app
2. In the Initial Screen, enter:
   - Transfer Order Number: [From Step 8 - first TO]
   - Warehouse Number: 100
3. Press Enter
4. View the Confirm Transfer Order Overview of Transfer Order Items screen
5. Review all details:
   - Verify correct material
   - Verify correct quantity (50)
   - Verify correct storage bin (STBN-1-563)
6. Click to confirm the transfer order
7. System returns success message
8. Repeat the process for the second transfer order:
   - Enter second Transfer Order Number
   - Enter Warehouse Number: 100
   - Press Enter
   - Verify all details
   - Click to confirm
9. Return to SAP Fiori Launchpad

**Expected Outcome**: Both transfer orders confirmed; goods physically placed in bins

---

### Step 10: Run Bin Status Report (Final Verification)
**Duration**: 5 minutes
**Role**: Warehouse Supervisor (Carolin Bruzik)
**App**: Run Bin Status Report

**Procedure**:
1. Open "Run Bin Status Report" app
2. In the Initial Screen, enter:
   - Warehouse Number: 100 (San Diego)
   - Storage Bin: STBN563
3. Click to execute
4. View the Bin Status Report Overview screen
5. Observe that Storage Bin STBN-1-563 now shows as filled
6. Double-click on storage bin STBN-1-563 for detailed information
7. Verify the contents:
   - Material KPAD1563: 50 units
   - Material EPAD1563: 50 units
8. Select a material and press to display quant information
9. Verify each material's exact storage location
10. Return to SAP Fiori Launchpad

**Expected Outcome**: Both materials confirmed in correct bin STBN-1-563

---

## WM I Challenge - Independent Exercise for User 563

### Challenge Scenario
**Supplier**: Spy Gear

**Product 1**: Water Bottles
- Quantity: 50 pieces
- Price: 11 USD each
- Total: 550 USD

**Product 2**: Road Helmets
- Quantity: 50 pieces
- Price: 27 USD each
- Total: 1,350 USD

**Delivery Details**:
- Delivery Date: 8 days from today
- Plant: SD00 (San Diego)
- Storage Location: TG00 (Trading Goods)

**Storage Bins**:
- Water Bottles Destination: STBN-2-563
- Road Helmets Destination: STBN-3-563

### Challenge Process
Follow the same 10-step procedure as WM I, but independently:
1. Create purchase order for both items from Spy Gear
2. Display inventory before receipt
3. Display inventory values before receipt
4. Receive goods
5. Display inventory after receipt
6. Display inventory values after receipt
7. Run bin status report
8. Create two separate transfer orders (one for each material in separate bins)
9. Confirm both transfer orders
10. Run final bin status report to verify placement

### Success Criteria
- Both materials ordered correctly from supplier
- Goods receipt completed successfully
- Water bottles in bin STBN-2-563
- Road helmets in bin STBN-3-563
- Bin status report confirms correct placement
- All procedures completed independently

---

## Data Summary for User 563

| Field | KPAD1563 | EPAD1563 |
|-------|----------|----------|
| Material Description | Keyboard Pad | Electronic Pad |
| Plant | SD00 (San Diego) | SD00 (San Diego) |
| Storage Location | TG00 (Trading Goods) | TG00 (Trading Goods) |
| Quantity | 50 units | 50 units |
| Unit Price | 40 USD | 40 USD |
| Total Value | 2,000 USD | 2,000 USD |
| Supplier | 103563 | 103563 |
| Supplier Name | Global Supplier | Global Supplier |
| Destination Bin (WM I) | STBN-1-563 | STBN-1-563 |
| Storage Type | 001 (Shelf Storage) | 001 (Shelf Storage) |
| Warehouse | 100 (San Diego) | 100 (San Diego) |

---

**Last Updated**: June 2026
**Case Study Version**: 4.3
**User ID**: 563