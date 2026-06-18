# Warehouse Management Concepts & Terminology

## Organizational Structure

### Warehouse Number
- **Definition**: Highest organizational unit in warehouse management
- **Purpose**: Represents a physical building or distribution center
- **Example**: 100 = San Diego Warehouse
- **Characteristics**:
  - One warehouse per physical location
  - Contains multiple storage types
  - Managed by Warehouse Supervisor

### Storage Type (STBN)
- **Definition**: Subdivision within a warehouse
- **Purpose**: Organizes warehouse areas by function or storage method
- **Example**: STBN = Shelf Storage
- **Characteristics**:
  - Multiple storage types per warehouse
  - Contains storage sections (optional)
  - Each has specific configuration

### Storage Section
- **Definition**: Optional subdivision within storage type
- **Purpose**: Further organize storage areas
- **Characteristics**:
  - Not always used
  - Useful for large warehouses
  - Maps spatial relationships

### Storage Bin
- **Definition**: Lowest organizational level; physical storage location
- **Format**: STBN-1-563, STBN-2-563, STBN-3-563
- **Purpose**: Identifies exact location of goods
- **Characteristics**:
  - Assigned to specific storage type
  - Can contain multiple quants
  - Represents actual physical location

---

## Inventory Management Concepts

### Stock Types

#### 1. Unrestricted-Use Stock
- **Status**: Available for use
- **Symbol**: U
- **Use**: Normal operations
- **Example**: Received goods ready for sale

#### 2. Quality Inspection Stock
- **Status**: Awaiting quality check
- **Symbol**: Q
- **Use**: Goods in inspection process
- **Timing**: Temporary status

#### 3. Blocked Stock
- **Status**: Not available for use
- **Symbol**: X
- **Use**: Goods with issues or holds
- **Duration**: Indefinite until cleared

#### 4. On-Order Stock
- **Status**: Ordered but not received
- **Symbol**: O
- **Use**: Pending purchase orders
- **Timing**: Until goods receipt

### Stock Levels

**Total Stock = Unrestricted-Use + Quality Inspection + Blocked + On-Order**

---

## Material Management Hierarchy

### Material Master
- **Definition**: Master data for a material
- **Contains**:
  - Material number (KPAD1563, EPAD1563)
  - Description
  - Unit of measure (pieces, kg, etc.)
  - Valuation class
  - Standard cost

### Plant
- **Definition**: Production or distribution facility
- **Example**: SD00 = San Diego
- **Role**: Groups materials and storage locations

### Storage Location
- **Definition**: Organizational unit for inventory
- **Example**: TG00 = Trading Goods
- **Purpose**: Separate materials by location or type

---

## Warehouse Management Documents

### Purchase Order (PO)
- **Purpose**: Request to buy materials
- **Type**: NB = Standard Purchase Order
- **Contains**:
  - Supplier information (103563)
  - Material and quantity
  - Price and delivery date
  - Storage location (TG00)
- **Status**: Triggers procurement process

### Material Document
- **Purpose**: Records goods receipt
- **Created by**: Goods receipt posting
- **Contains**:
  - Material quantity (50 units each)
  - Document date
  - Reference to PO
  - Stock type (Unrestricted-Use)

### Transfer Requirement (TR)
- **Purpose**: System-generated need to move goods
- **Triggered by**: Goods receipt in managed storage location
- **Contains**:
  - Material and quantity
  - Source bin (temporary)
  - Plant (SD00) and warehouse (100) info
- **Status**: Awaiting transfer order creation

### Transfer Order (TO)
- **Purpose**: Instruction to warehouse employee
- **Created from**: Transfer requirement
- **Contains**:
  - Material and quantity (source)
  - Destination storage bin (STBN-1-563, STBN-2-563, STBN-3-563)
  - Storage type (001 - Shelf Storage) and section
  - Employee assignment
- **Status**: Awaits confirmation

### Quant
- **Definition**: Quantity of material in specific bin
- **Unique Key**: Material + Storage Bin + Stock Type + Batch
- **Purpose**: Tracks exact location of materials
- **Example**: 50 pieces of KPAD1563 in STBN-1-563

---

## Process Flow Concepts

### Goods Receipt Process
1. **Trigger**: Purchase order delivery date reached
2. **Action**: Goods Receipt Clerk creates GR for purchase order
3. **System**: Allocates to temporary bin
4. **Update**: Inventory increases (On-Order → Unrestricted-Use)
5. **Next Step**: Transfer requirement automatically generated

### Putaway Process
1. **Trigger**: Transfer requirement exists for received goods
2. **Action**: Warehouse Employee creates transfer order
3. **Specify**: Destination bin (STBN-1-563) and storage type (Shelf)
4. **System**: Updates warehouse structure
5. **Next Step**: Employee physically moves goods and confirms

### Confirmation Process
1. **Trigger**: Transfer order created and ready for pickup
2. **Action**: Warehouse Employee physically moves goods to destination
3. **Confirmation**: Confirms goods in destination bin (STBN-1-563)
4. **System**: Moves quant from temporary to destination bin
5. **Result**: Goods now in permanent storage location

### Verification Process
1. **Trigger**: After confirmation completed
2. **Action**: Warehouse Supervisor runs bin report
3. **Verification**: Confirms correct placement in STBN-1-563
4. **Report**: Shows bin contents (50 × KPAD1563 + 50 × EPAD1563)
5. **Outcome**: Process complete and verified

---

## Key Transactions & Apps Used in Case Study

### Plant Manager View (Jennifer Brown)
- **Stock - Single Material**: See inventory for KPAD1563, EPAD1563
- **Display Stock Overview**: See summary by plant SD00
- **Display Warehouse Stock**: See inventory values (2,000 USD each)
- **Focus**: Planning and monitoring

### Goods Receipt Clerk View (Yoshi Agawa)
- **Post Goods Receipt for PD**: Record incoming goods
- **Focus**: Data entry and verification
- **Activities**: Check materials, create GR, verify TG00 location

### Warehouse Employee View (Sunil Gupta)
- **Display Transfer Requirement**: Find work tasks
- **Create Transfer Order**: Plan putaway to STBN-1-563
- **Confirm Transfer Order**: Complete putaway
- **Focus**: Physical warehouse operations

### Warehouse Supervisor View (Carolin Bruzik)
- **Run Bin Status Report**: Monitor warehouse and bin 563
- **Display Transfer Order**: Track work progress
- **Focus**: Oversight and coordination

---

## Data Flow Example for User 563

```
PURCHASE ORDER (50 × KPAD1563 @ 40 USD)
  ↓ (PO created with supplier 103563)
  ↓
MAT. INVENTORY (On-Order: 50 units)
  ↓ (Delivery arrives)
  ↓
GOODS RECEIPT
  ↓ (GR posted)
  ↓
MATERIAL DOCUMENT (Created)
  ↓ (Goods in temporary bin)
  ↓
MAT. INVENTORY (Unrestricted-Use: 50 units)
  ↓ (Value: 2,000 USD)
  ↓
TRANSFER REQUIREMENT (Auto-generated)
  ↓ (Warehouse employee acts)
  ↓
TRANSFER ORDER (TO created for STBN-1-563)
  ↓ (Specifies destination bin)
  ↓
CONFIRMATION (Employee confirms)
  ↓ (Physically moves goods)
  ↓
QUANT (Updated in STBN-1-563)
  ↓ (Goods now in permanent storage)
  ↓
BIN STATUS REPORT (Supervisor verifies)
  ↓ (STBN-1-563 shows 50 × KPAD1563 + 50 × EPAD1563)
```

---

## Best Practices Applied in WM I

### Warehouse Organization
1. **Clear Bin Naming**: Use consistent naming (STBN-1-563, STBN-2-563, STBN-3-563)
2. **Storage Type Assignment**: Group similar materials in same bin
3. **Bin Capacity**: Respect maximum quantities per bin
4. **Aisle Management**: Ensure accessibility for warehouse employees

### Inventory Accuracy
1. **Stock Verification**: Check inventory before and after receipt
2. **Bin Verification**: Run bin status reports
3. **Transfer Confirmation**: Confirm all transfers before closing
4. **System Integrity**: Regular audits of stock vs physical count

### Operational Efficiency
1. **Minimize Travel**: Group materials in same location when possible
2. **Process Flow**: Follow standard procedures consistently
3. **Transfer Consolidation**: Combine transfers where feasible
4. **Documentation**: Record all transaction details

### Data Management
1. **Accurate Descriptions**: Clear material names (Keyboard Pad, Electronic Pad)
2. **Regular Updates**: Keep master data current
3. **Audit Trail**: Track all movements through material document
4. **Documentation**: Record transfer orders and confirmations

---

## Calculation Examples for User 563

### Inventory Value - Material KPAD1563
**Formula**: Quantity × Unit Cost
**Calculation**: 50 units × 40 USD = **2,000 USD**

### Inventory Value - Material EPAD1563
**Formula**: Quantity × Unit Cost
**Calculation**: 50 units × 40 USD = **2,000 USD**

### Total Procurement Value
**Formula**: (KPAD1563 × 50 × 40) + (EPAD1563 × 50 × 40)
**Calculation**: 2,000 + 2,000 = **4,000 USD total**

### Challenge Exercise - Water Bottles
**Formula**: 50 × 11 USD
**Calculation**: 50 × 11 = **550 USD**

### Challenge Exercise - Road Helmets
**Formula**: 50 × 27 USD
**Calculation**: 50 × 27 = **1,350 USD**

### Challenge Total Value
**Formula**: 550 + 1,350
**Calculation**: **1,900 USD total**

---

## Common Scenarios in WM I

### Scenario 1: Material in Temporary Bin
**Situation**: Goods received but transfer order not yet confirmed
**Solution**: Create and confirm transfer order immediately
**Impact**: Goods moved to permanent storage bin

### Scenario 2: Bin Capacity Exceeded
**Situation**: Cannot fit all 50 units in single bin
**Solution**: Use multiple destination bins (STBN-1-563, STBN-2-563)
**Impact**: Distribute materials across bins

### Scenario 3: Stock Discrepancy
**Situation**: Bin report shows different quantity than expected
**Solution**: Physical count and investigate
**Impact**: Adjust system if needed

---

**Last Updated**: June 2026
**Case Study Version**: 4.3
**User ID**: 563