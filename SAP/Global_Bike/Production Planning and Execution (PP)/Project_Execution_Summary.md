# Project Execution Summary

**Production Planning and Execution (PP) — Deluxe Touring Bike (Red)**

| | |
|---|---|
| **System** | SAP S/4HANA 2023 (Fiori 3.0) |
| **Case Study** | Global Bike — Production Planning and Execution |
| **Plant** | DL00 (Dallas) |
| **Execution Date** | 22 June 2026 |

> ✅ **All 15 process steps completed — production order settled**

---

## 1. Executive Summary

This document records the end-to-end execution of the Production Planning and Execution (PP) case study for the Global Bike Deluxe Touring Bike (red), material `DXTR3563`, in plant `DL00` (Dallas). The run covers the complete cycle: material master and routing preparation, product group demand planning, MRP, conversion of a planned order into a production order, full goods receipt and issue, production confirmation, finished-goods receipt, cost review, and final settlement.

All master data and transactional postings below reflect actual system results captured during execution on 22 June 2026.

---

## 2. Master Data Configuration

### 2.1 Strategy Group Assignment

Strategy Group `40` (Planning with Final Assembly) was applied to the Dallas plant view of all three Deluxe Touring Bike variants, enabling participation in demand-driven MRP.

| Material | Variant | Strategy Group |
|---|---|---|
| `DXTR1563` | Black | 40 |
| `DXTR2563` | Silver | 40 |
| `DXTR3563` | Red | 40 |

### 2.2 Bill of Material — DXTR3563

Routing group `11776` components were allocated across the standard operation sequence (seat/frame at Op. 0020, handlebar at 0030, wheel/derailleur at 0040, chain at 0050, brakes at 0060, pedals at 0070, warranty document and packaging at 0100), producing BOM `00016267`.

| Item | Component |
|---|---|
| BOM | `00016267` |
| Header Material | `DXTR3563` — Deluxe Touring Bike (red) |
| Plant | `DL00` |
| Allocation 1 | `TRFR3563` — Touring Frame-Red |
| Allocation 2 | `TRSK1563` — Touring Seat Kit |
| Allocation 3 | `TRHB1563` — Touring Handle Bar |
| Allocation 4 | `TRWA1563` — Touring Aluminum Wheel Assembly |
| Allocation 5 | `DGAM1563` — Derailleur Gear Assembly |
| Allocation 6 | `CHAN1563` — Chain |
| Allocation 7 | `BRKT1563` — Brake Kit |
| Allocation 8 | `PEDL1563` — Pedal Assembly |
| Allocation 9 | `WDOC1563` — Warranty Document |
| Allocation 10 | `PCKG1563` — Packaging |

### 2.3 Product Group

Product group `PG-DXTR563` aggregates the three color variants for family-level demand planning (proportions: 40% black, 30% silver, 30% red), with Dallas responsibility confirmed.

| Field | Value |
|---|---|
| Product Group | `PG-DXTR563` |
| Product 1 | `DXTR1563` — black |
| Product 2 | `DXTR2563` — silver |
| Product 3 | `DXTR3563` — red |
| Responsibility | Plant Dallas (`DL00`) confirmed |

---

## 3. Demand Planning — Planned Independent Requirements

A 12-month flat forecast of 100 EA per period was entered via mass maintenance for all three materials in plant `DL00`, beginning 01 June 2026 and running through 01 May 2027.

| Period | Date | DXTR1563 | DXTR2563 | DXTR3563 |
|---|---|---|---|---|
| 1 | 01.06.26 | 100 | 100 | 100 |
| 2 | 01.07.26 | 100 | 100 | 100 |
| 3 | 01.08.26 | 100 | 100 | 100 |
| 4 | 01.09.26 | 100 | 100 | 100 |
| 5 | 01.10.26 | 100 | 100 | 100 |
| 6 | 01.11.26 | 100 | 100 | 100 |
| 7 | 01.12.26 | 100 | 100 | 100 |
| 8 | 01.01.27 | 100 | 100 | 100 |
| 9 | 01.02.27 | 100 | 100 | 100 |
| 10 | 01.03.27 | 100 | 100 | 100 |
| 11 | 01.04.27 | 100 | 100 | 100 |
| 12 | 01.05.27 | 100 | 100 | 100 |

---

## 4. Material Requirements Planning (MRP)

A single MRP run against product group `PG-DXTR563` exploded the period forecast through the bill of material, generating planned orders for the finished bikes and all dependent components.

| Parameter | Value |
|---|---|
| Job Name | Material Requirements Planning (MRP) |
| Plant | `DL00` |
| Product Group | `PG-DXTR563` |
| All Order BOM Components | ✅ Selected |
| Regenerative Planning | ✅ Selected |
| Scheduling | 1 — Determination of Basic Dates for Planned Orders |
| Planning Mode | 1 — Adjust Planning Data |
| Output Material List (Job Log) | ✅ Selected |

---

## 5. Production Order

The third planned order for `DXTR3563` was converted into a production order, released automatically with planned costs calculated on save.

| Field | Value |
|---|---|
| Production Order | `1000082` |
| Plant | `DL00` |
| Material | `DXTR3563` — Deluxe Touring Bike (red) |
| Total Order Quantity | 50 EA |
| Status | REL (Released) · SETC (Settlement Rule Created) · MACM (Material Committed) |

---

## 6. Goods Receipt — Component Stock-In

Component inventory (500 EA per item) was posted directly into Dallas storage via goods receipt without reference, ahead of production, split between semi-finished (`SF00`) and raw materials (`RM00`) storage.

**Material Document:** `4900038319` | **Plant:** `DL00` | **Date:** 22.06.2026

| Material | Quantity | Storage Location |
|---|---|---|
| `TRWA1563` — Wheel Assembly | 500 EA | `SF00` |
| `TRFR3563` — Touring Frame-Red | 500 EA | `RM00` |
| `DGAM1563` — Derailleur Gear Assembly | 500 EA | `RM00` |
| `TRSK1563` — Touring Seat Kit | 500 EA | `RM00` |
| `TRHB1563` — Touring Handle Bar | 500 EA | `RM00` |
| `PEDL1563` — Pedal Assembly | 500 EA | `RM00` |
| `CHAN1563` — Chain | 500 EA | `RM00` |
| `BRKT1563` — Brake Kit | 500 EA | `RM00` |
| `WDOC1563` — Warranty Document | 500 EA | `RM00` |
| `PCKG1563` — Packaging | 500 EA | `RM00` |

---

## 7. Goods Issue to Production Order

Components were issued against the production order using movement type `261`, drawn from the correct storage locations per the BOM allocation.

**Material Document:** `4900038320` | **Movement Type:** 261 (GI for Order) | **Production Order:** `1000082` | **Date:** 22.06.2026

| Material | Quantity | From |
|---|---|---|
| `TRWA1563` — Wheel Assembly | 100 EA | `SF00` |
| `TRFR3563` — Touring Frame-Red | 50 EA | `RM00` |
| `DGAM1563` — Derailleur Gear Assembly | 50 EA | `RM00` |
| `TRSK1563` — Touring Seat Kit | 50 EA | `RM00` |
| `TRHB1563` — Touring Handle Bar | 50 EA | `RM00` |
| `PEDL1563` — Pedal Assembly | 50 EA | `RM00` |
| `CHAN1563` — Chain | 50 EA | `RM00` |
| `BRKT1563` — Brake Kit | 50 EA | `RM00` |
| `WDOC1563` — Warranty Document | 50 EA | `RM00` |
| `PCKG1563` — Packaging | 50 EA | `RM00` |

---

## 8. Production Confirmation

Final confirmation was posted for the full order quantity with open reservations cleared, recording actual execution times and triggering labor cost calculation.

| Field | Value |
|---|---|
| Confirmation Number | `0000000951` |
| Production Order | `1000082` |
| Confirmation Type | Final Confirmation · Clear Open Reservations |
| Yield Confirmed | 50 EA |
| Execution Start | 22.06.2026, 14:55:52 |
| Execution Finish | 22.06.2026, 15:55:52 |
| Posting Date | 22.06.2026 |

---

## 9. Finished Goods Receipt

The completed quantity was received into finished goods storage, closing the physical production loop and updating the order's delivered value.

| Field | Value |
|---|---|
| Material Document | `5000000216` |
| Material | `DXTR3563` — Deluxe Touring Bike (red) |
| Production Order | `1000082` |
| Plant | `DL00` |
| Storage Location | `FG00` — Finished Goods |
| Document / Posting Date | 22.06.2026 |

---

## 10. Cost Settlement

Following cost review on the closed order (target vs. actual by cost element — raw material consumption, labor, overhead), the production order was settled, clearing the order balance to zero via the *Settle. Manuf. Output* account.

| Field | Value |
|---|---|
| Production Order | `1000082` |
| Controlling Area | `NA00` — Global Bike North America |
| Settlement Period | Current period |
| Posting Period | Current period |
| Fiscal Year | Current year |
| Result | Order balance settled to zero — variance transferred to *Settle. Manuf. Output* |

---

## 11. Process Completion Checklist

- [x] Strategy Group 40 applied to all three Deluxe Touring Bike variants
- [x] Routing components allocated across operations 0020–0100
- [x] Product group `PG-DXTR563` confirmed with Dallas responsibility
- [x] 12-month Planned Independent Requirements entered (100 EA/period)
- [x] MRP run executed — planned orders generated through full BOM explosion
- [x] Planned order converted to production order `1000082` (50 EA)
- [x] Component goods receipt posted — 500 EA per item (Doc. `4900038319`)
- [x] Goods issued to production order `1000082` (Doc. `4900038320`)
- [x] Production confirmed complete — 50 EA yield, zero scrap (Conf. `0000000951`)
- [x] Finished goods received into `FG00` (Doc. `5000000216`)
- [x] Production costs reviewed — target vs. actual by cost element
- [x] Production order settled — balance cleared to zero

---

*End of execution summary — Global Bike S/4HANA 2023, Production Planning and Execution*
