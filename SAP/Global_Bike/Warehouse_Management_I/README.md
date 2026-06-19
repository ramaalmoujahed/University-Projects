# SAP S/4HANA Global Bike - Warehouse Management (WM I)

## Project Overview

This directory contains documentation and materials for the **Global Bike Warehouse Management (WM I)** case study using **SAP S/4HANA 2023** with **Fiori 3.0**.

### Project Details
- **Product**: S/4HANA 2023
- **Application**: Global Bike (GB)
- **Module**: Warehouse Management (WM I)
- **UI Technology**: SAP Fiori 3.0
- **Level**: Beginner
- **Version**: 4.3
- **Last Updated**: July 2025
- **Copyright**: © SAP UCC Magdeburg

## About This Project

### Motivation
Warehousing has significant value for logistics and plays a critical role in supply chain management. This project explores:

- **Business Challenges**:
  - Higher cost pressure
  - Shorter innovation cycles
  - Rising customer expectations
  - Market globalization

- **Industry Focus**: Consumer goods industry with high product differentiation

- **Customer Demands**:
  - Reliability of deliveries
  - Promptness and responsiveness
  - Flexibility in fulfillment

### Key Learning Areas

This case study covers warehouse management systems (WMS) that:
- Support global flow of goods between producers and purchasers
- Facilitate near fail-proof logistic operations
- Manage increasingly complex supply chains

## Project Scenario

**Location**: San Diego Distribution Center

Due to increasing sales output in the San Diego distribution center, management has decided to install a Warehouse Management System. This implementation has just been completed and needs to be tested.

**Objective**: To procure trading goods from a vendor and put them into stock in San Diego using the new warehouse management system.

## Employees Involved

- **Jennifer Brown** - Plant Manager
- **Carolin Bruzik** - Warehouse Supervisor
- **Sunil Gupta** - Warehouse Employee
- **Yoshi Agawa** - Goods Receipt Clerk

## Case Study Duration

**Total Time**: 65 minutes for WM I + 40 minutes for WM I Challenge = 105 minutes

## Process Overview

### Warehouse Management I (WM I) - Main Case Study

This case study explains an integrated warehouse management process triggered by a purchase order for a warehouse-managed storage location.

**Process Flow**:
1. Create Purchase Order
2. Display Material Inventory (before receipt)
3. Display Material Inventory Value (before receipt)
4. Receive Goods
5. Display Material Inventory (after receipt)
6. Display Material Inventory Value (after receipt)
7. Run Bin Status Report
8. Create Transfer Order
9. Confirm Transfer Order
10. Run Bin Status Report (final)

**Estimated Time**: 65 minutes

### WM I Challenge

After completing the main case study, test your knowledge with a comprehensive challenge:

**Scenario**: Order two different products (water bottles and road helmets) from supplier "Spy Gear" - 50 pieces each. Store them in different storage bins in San Diego.

**Estimated Time**: 40 minutes

## Prerequisites

Before working through this project, you should have:
- Familiarity with SAP system navigation
- Understanding of basic warehouse management concepts
- Access to an SAP S/4HANA 2023 instance with Global Bike dataset

## Key Concepts Covered

### Warehouse Management Hierarchy

1. **Warehouse Number** (100)
   - Highest level of organizational unit in warehouse management
   - Usually corresponds to a physical building or distribution center
   - Example: San Diego Warehouse

2. **Storage Type** (STBN)
   - Subdivisions within a warehouse
   - Example: Shelf Storage

3. **Storage Bin**
   - Lowest level of organizational structure
   - Physical location where goods are stored
   - Example: STBN-1-563

### Core Processes

#### 1. Purchase Order Creation
- Document Type: NB (Standard PO)
- Materials: KPAD1563, EPAD1563
- Quantity: 50 units each
- Price: 40 USD per unit
- Storage Location: TG00 (Trading Goods)
- Delivery: 8 days

#### 2. Goods Receipt
- Uses app: "Post Goods Receipt for Purchasing Document"
- Creates material document
- Automatically assigns to temporary bins

#### 3. Transfer Order Creation
- Recognizes goods received but not yet put away
- Assigns destination storage bins
- Handoff from Inventory Management to Warehouse Management

#### 4. Transfer Order Confirmation
- Confirms goods are physically in assigned storage bins
- Updates warehouse inventory

#### 5. Bin Status Report
- Displays detailed report of storage bins
- Shows quantity and material information
- Verifies correct placement

## SAP Fiori Applications Used

### Plant Manager Role
- **Stock - Single Material** - View inventory for a single material
- **Display Stock Overview** - View stock overview for materials
- **Display Warehouse Stock** - View warehouse stock values

### Goods Receipt Clerk Role
- **Post Goods Receipt for Purchasing Document** - Create goods receipt

### Warehouse Employee Role
- **Display Transfer Requirement – List for Material** - View transfer requirements
- **Create Transfer Order** - Create transfer orders for putaway
- **Confirm Transfer Order** - Confirm transfer order completion

### Warehouse Supervisor Role
- **Run Bin Status Report** - Generate bin status reports

## Sample Materials & Data

### Material 1: KPAD1563
- Description: Keyboard Pad
- Plant: SD00 (San Diego)
- Storage Location: TG00 (Trading Goods)
- Order Quantity: 50 units
- Price: 40 USD per unit

### Material 2: EPAD1563
- Description: Electronic Pad
- Plant: SD00 (San Diego)
- Storage Location: TG00 (Trading Goods)
- Order Quantity: 50 units
- Price: 40 USD per unit

### Supplier Information
- **Supplier ID**: 103563
- **Purchasing Group**: N00

## Key Learning Objectives

Upon completion of this case study, you will:

1. ✅ Create purchase orders in SAP Fiori
2. ✅ Monitor material inventory and values
3. ✅ Process goods receipts
4. ✅ Create and confirm transfer orders
5. ✅ Verify correct storage bin placement
6. ✅ Understand warehouse management system workflows
7. ✅ Apply warehouse management best practices

## Important Notes

### About the Global Bike Dataset
- Exclusively created for SAP UA (University Alliance) global curricula
- Used for educational and training purposes
- Proprietary to SAP

### Implementation Notes
- This case study focuses on Warehouse Management
- Invoice receipt and vendor payment procedures are covered in the Materials Management (MM) case study
- Temporary bins hold goods until transfer orders are confirmed
- Physical inventory verification is completed through bin status reports

## Challenge Exercise: WM I Challenge

### Objective
Test your warehouse management skills by independently completing a procurement and storage exercise.

### Challenge Scenario
**Supplier**: Spy Gear

**Products to Order**:
1. **Water Bottles** - 50 pieces @ 11 USD each
2. **Road Helmets** - 50 pieces @ 27 USD each

**Storage Instructions**:
- Delivery Location: SD00, San Diego
- Storage Duration: 8 days
- Water Bottles Destination Bin: STBN-2-563
- Road Helmets Destination Bin: STBN-3-563

### Instructions
- Use the WM I case study as a guideline
- Complete the challenge independently to validate your skills
- Follow the same process flow as the main case study

**Estimated Time**: 40 minutes

## Resources

- [SAP Learning Hub](https://learning.sap.com/)
- [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/)
- [SAP S/4HANA Documentation](https://help.sap.com/viewer/product/SAP_S4HANA)
- [SAP University Alliances](https://www.sap.com/training.html)

## Authors & Credits

**Original Case Study Authors:**
- Simha Magal
- Stefan Weidner
- Chris Bernhardt

**Copyright**: © SAP UCC Magdeburg

**Repository Owner**: @ramaalmoujahed

## Project Completion

- **Study Duration**: 105 minutes (65 min WM I + 40 min Challenge)
- **Difficulty Level**: Beginner to Intermediate
- **Recommended Prerequisites**: Basic SAP system navigation

## References

### Key Warehouse Management Concepts

- **Warehouse Number**: Organizational unit corresponding to physical warehouse/distribution center
- **Storage Type**: Subdivisions within a warehouse (e.g., Shelf Storage)
- **Storage Bin**: Physical location where goods are stored (lowest organizational level)
- **Transfer Requirement**: System-generated document when goods are received but not yet put away
- **Transfer Order**: Document instructing warehouse employees where to place received goods
- **Quant**: Quantity of a specific material in a specific storage bin

## License

This project is based on SAP's Global Bike case study materials created for SAP University Alliances. Use in accordance with SAP's educational licensing agreements.

## Contact & Support

For questions about this project:
- Review the detailed documentation files in this repository
- Consult SAP Learning resources
- Contact your SAP instructor or administrator

---

**Last Updated**: June 2026
**Status**: Active
**Level**: Beginner to Intermediate
**Product**: SAP S/4HANA 2023
**Case Study Version**: 4.3