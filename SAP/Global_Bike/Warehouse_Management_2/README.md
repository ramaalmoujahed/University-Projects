# SAP Warehouse Management Process Simulation (Stock Transport Order)

## 📖 Overview

This project demonstrates an end-to-end Warehouse Management (WM) process in SAP using the SAP Fiori Launchpad. The case study simulates the movement of finished goods between two company plants through a Stock Transport Order (STO), followed by warehouse put-away operations.

The scenario focuses on transferring inventory from the Dallas manufacturing plant to the San Diego distribution center after implementing a new Warehouse Management System (WMS).

---

## 🎯 Learning Objectives

- Understand the Stock Transport Order (STO) process
- Perform inter-plant inventory transfers
- Execute Goods Issue and Goods Receipt
- Manage warehouse transfer orders
- Confirm warehouse put-away
- Monitor inventory and warehouse stock
- Verify storage bin assignments

---

## 🛠 Technologies Used

- SAP S/4HANA
- SAP Fiori Launchpad
- SAP Warehouse Management (WM)
- Inventory Management (IM)
- Materials Management (MM)

---

## 📋 Business Scenario

Due to increased sales at the San Diego distribution center, a new Warehouse Management System has been implemented.

To validate the new system, finished goods are transferred from the Dallas manufacturing facility to San Diego through SAP's warehouse management process.

The project follows the complete logistics workflow from creating the Stock Transport Order to placing goods into warehouse storage bins.

---

## 🔄 Process Flow

1. Display Material Inventory
2. Create Stock Transport Order (STO)
3. Review Updated Inventory
4. Check Inventory Value
5. Post Goods Issue (Dallas)
6. Verify Inventory Changes
7. Review Inventory Value
8. Post Goods Receipt (San Diego)
9. Verify Inventory Update
10. Review Updated Inventory Value
11. Run Bin Status Report
12. Create Transfer Order
13. Confirm Transfer Order
14. Verify Final Bin Status

---

## 📦 Warehouse Process

```text
Dallas Plant
      │
      ▼
Create Stock Transport Order
      │
      ▼
Post Goods Issue
      │
      ▼
Goods in Transit
      │
      ▼
Post Goods Receipt
      │
      ▼
Transfer Requirement
      │
      ▼
Create Transfer Order
      │
      ▼
Confirm Transfer Order
      │
      ▼
Goods Stored in Warehouse Bin
```

---

## 👥 SAP Roles Used

| Role | Responsibility |
|------|----------------|
| Warehouse Supervisor | Monitor inventory and warehouse stock |
| Plant Manager | Create Stock Transport Orders |
| Warehouse Employee | Post Goods Issue |
| Goods Receipt Clerk | Receive goods, create and confirm Transfer Orders |

---

## 📌 SAP Applications Used

- Stock – Single Material
- Display Stock Overview
- Display Warehouse Stock
- Create Purchase Order
- Post Goods Movement
- Run Bin Status Report
- Display Transfer Requirement
- Confirm Transfer Order

---

## ✅ Key SAP Transactions Performed

- Stock Transport Order (STO)
- Goods Issue (GI)
- Goods Receipt (GR)
- Inventory Monitoring
- Warehouse Put-away
- Transfer Order Creation
- Transfer Order Confirmation
- Bin Status Reporting

---

## 📈 Expected Outcome

At the end of the process:

- Goods are successfully transferred from Dallas to San Diego.
- Inventory is updated in both plants.
- Goods in Transit becomes zero after receipt.
- Warehouse Transfer Order is completed.
- Goods are assigned to the correct storage bin.
- Warehouse stock reflects the final inventory accurately.

---

## 📚 Skills Demonstrated

- SAP Warehouse Management
- Inventory Management
- Materials Management
- Logistics Execution
- Warehouse Operations
- Stock Transport Process
- Goods Movement
- Warehouse Put-away
- SAP Fiori Navigation
- Business Process Execution

---

## 📄 Project Type

Academic SAP Case Study demonstrating an end-to-end Warehouse Management process using SAP S/4HANA Fiori applications.

---

## 📜 License

This project is for educational and learning purposes only.
