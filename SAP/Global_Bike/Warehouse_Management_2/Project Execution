# Warehouse Management II – Project Execution
**Global Bike Inc. | SAP S/4HANA 2023 | LEARN-563 | SAP UCC Magdeburg**

---

## Project Overview

This document records the execution of the SAP Warehouse Management II (WM II) case study, completed in the Global Bike S/4HANA training environment. The process covers a full internal stock transfer cycle, where finished goods were requested from the Dallas manufacturing plant and received into the San Diego distribution center warehouse using SAP's Warehouse Management System.

| Field | Value |
|---|---|
| System | SAP S/4HANA 2023 – Global Bike |
| Case Study | Warehouse Management II (WM II) |
| Process | Internal Stock Transfer – Dallas to San Diego |
| User | LEARN-563 |
| Supplying Plant | DL00 – Dallas |
| Receiving Plant | SD00 – San Diego |
| Warehouse | 100 – San Diego |
| Material | DXTR1563 |
| Quantity | 10 units |
| Final Bin | STBN-7-563 |

---

## Step 1 — Create Stock Transport Order

A Stock Transport Order (STO) was created to request 10 units of material DXTR1563 from the Dallas plant (DL00) to the San Diego distribution center (SD00). Unlike a standard purchase order from an external vendor, this order represents an internal plant-to-plant transfer within the same company code. The order was placed using document type UB with a scheduled delivery date of 15.06.2026.

| Field | Value |
|---|---|
| Stock Transport Order Number | 4500000154 |
| Purchase Order Type | UB |
| Supplying Plant | DL00 – Dallas |
| Purchasing Organization | US00 |
| Purchasing Group | N00 |
| Company Code | US00 |
| Material | DXTR1563 |
| Order Quantity | 10 |
| Delivery Date | 15.06.2026 |
| Receiving Plant | SD00 – San Diego |
| Storage Location | FG00 – Finished Goods |

---

## Step 2 — Goods Issue (Dallas)

The goods issue was posted from the Dallas plant to physically release the 10 units of DXTR1563 from Dallas inventory and initiate the transfer to San Diego. This step reduced the stock in Dallas and placed the goods in transit. Movement type WA was used to record the outgoing stock movement against the Stock Transport Order.

| Field | Value |
|---|---|
| Material Document | 4900038262 |
| Stock Transport Order No. | 4500000154 |
| Transaction/Event Type | WA |
| Document Type | WA |
| Storage Location | FG00 – Finished Goods |
| Quantity Issued | 10 |

---

## Step 3 — Goods Receipt (San Diego)

Upon arrival of the goods in San Diego, a goods receipt was posted to confirm the physical delivery of the 10 units into the San Diego distribution center. This step updated the inventory in San Diego, cleared the on-order stock, and moved the goods into the finished goods storage location (FG00), ready to be placed into a warehouse bin.

| Field | Value |
|---|---|
| Material Document | 5000000188 |
| Stock Transport Order No. | 4500000154 |
| Transaction/Event Type | WE |
| Document Type | WE |
| Movement Type | 101 |
| Plant | SD00 – San Diego |
| Storage Location | FG00 – Finished Goods |
| Quantity Received | 10 |

---

## Step 4 — Create Transfer Order

A Transfer Order was created to move the received goods from their temporary storage position into a designated permanent warehouse bin. This step is the handoff from inventory management to warehouse management — the system identified the open transfer requirement and a transfer order was raised to direct the goods to bin STBN-7-563 in pallet storage section.

| Field | Value |
|---|---|
| Transfer Order Number | 0000005008 |
| Warehouse Number | 100 |
| Material | DXTR1563 |
| Plant | SD00 – San Diego |
| Source Target Quantity | 10 |
| Destination Storage Type | 2 – Pallet Storage |
| Destination Storage Section | 1 |
| Destination Bin | STBN-7-563 |

---

## Step 5 — Confirm Transfer Order

The Transfer Order was confirmed to record that the 10 units of DXTR1563 were physically moved and placed into the destination bin STBN-7-563 in the San Diego warehouse. This confirmation completed the full warehousing cycle and updated the bin status report to reflect the goods in their final storage location.

| Field | Value |
|---|---|
| Transfer Order Number | 5008 |
| Warehouse Number | 100 |
| Confirmation | X |
| Confirmation Date | 07.06.2026 |
| Material | DXTR1563 |
| Quantity | 10 |
| Destination Bin | STBN-7-563 |

---

## Final Result

All steps of the Warehouse Management II process were completed successfully. The 10 units of material DXTR1563 were transferred from the Dallas plant, received in San Diego, and stored in the designated warehouse bin STBN-7-563 using SAP's Warehouse Management System.

| Step | Document | Status |
|---|---|---|
| Stock Transport Order | 4500000154 | ✅ |
| Goods Issue – Dallas | Mat. Doc. 4900038262 | ✅ |
| Goods Receipt – San Diego | Mat. Doc. 5000000188 | ✅ |
| Transfer Order Created | TO 0000005008 | ✅ |
| Transfer Order Confirmed | 07.06.2026 – STBN-7-563 | ✅ |

**10 units of DXTR1563 successfully stored in bin STBN-7-563.**
