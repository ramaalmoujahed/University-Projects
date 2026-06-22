Production Planning and Execution (PP) — Global Bike, S/4HANA 2023

What this covers

A full manufacturing cycle for the Deluxe Touring Bike product family (black, silver, red) in plant DL00 (Dallas), run end-to-end in Fiori: master data prep → demand planning → MRP → production order → goods movements → confirmation → costing → settlement.

Student number used throughout: 563. Materials, bins, and groups below follow the ### → 563 substitution pattern.


The story, in order

1. Material master prep. The three Deluxe Touring Bikes (DXTR1563 black, DXTR2563 silver, DXTR3563 red) get a Strategy Group of 40 ("planning with final assembly") added in their Dallas plant view. This is what makes them plannable through Sales & Operations Planning.

2. Routing. The red bike's routing (group 11776, plant DL00) gets its components allocated to operations — frame and seat to operation 0020, handlebar to 0030, wheel assembly and derailleur to 0040, chain to 0050, brakes to 0060, pedals to 0070, warranty doc and packaging to 0100. This turns a generic operation sequence into a real bill-of-operations.

3. Product group. PG-DXTR563 ties the three color variants together with proportions — 40% black, 30% silver, 30% red — so forecasting can happen at the family level instead of per-SKU.

4. Planned Independent Requirements. Using Mass Maintenance, all three materials get a flat 100 units/month forecast across the next 12 periods in plant DL00. This is demand that exists before any real customer order does.

5. MRP run. A single MRP run against PG-DXTR563 (with all order BOM components, regenerative planning, basic-date scheduling) explodes the PIRs down through the BOM, generating planned orders for the finished bikes and their components alike.

6. Stock/Requirements List. Reviewing DXTR3563 shows the planned orders sitting against the forecast, with everything pegged back to the original independent requirement — a clean line from "we expect to sell 100 of these" to "here's the planned order that covers it."

7. Conversion to production order. The third planned order for DXTR3563 gets converted into a real production order (order type PP01), released automatically, with planned costs calculated on save.

8. Goods receipt (bypassing procurement). Since this case study skips the purchasing cycle, 500 units of each component — wheel assembly, frame, derailleur, seat kit, handlebar, pedals, chain, brake kit, warranty doc, packaging — are posted straight into inventory via goods receipt without reference, split between semi-finished (SF00) and raw materials (RM00) storage.

9. Goods issue. Components get issued to the production order (movement type 261), drawn from the correct storage locations, which triggers consumption updates and the first real actual costs hitting the order.

10. Status check #1. The order shows Released → Precosted → Settlement Rule Created, and the component list confirms nothing is still open.

11. Confirmation. A final confirmation records the 50-unit yield, clears open reservations, and backdates the start time — this is what calculates labor cost and sets up the parameters for the finished-goods receipt.

12. Status check #2. Status flips to Confirmed, processing moves to "move to storage," and the order confirmation log shows the full quantity with zero scrap.

13. Finished goods receipt. The 50 completed bikes move into FG00 (finished goods storage), closing the loop on the physical process.

14. Cost review. Production Cost Analysis on the closed order shows target vs. actual by cost element (raw material consumption, labor, overhead) and introduces the Manufacturing Output Settlement Variance — the gap between what flowed in as cost and what flowed out as a valued finished good.

15. Settlement. A test run, then a real settlement run, clears the production order's balance to zero by moving the variance to the appropriate account — visible in the before/after Actual/Plan/Variance report (order balance goes from -75.70 to 0.00 once settled).


Key concepts worth holding onto


Strategy Group 40 is the switch that makes a material participate in make-to-stock planning with final assembly.
Product groups exist purely to make high-level demand planning tractable — you forecast the family, the system disaggregates to the members.
PIRs are demand without a sales order — they represent the planning department's best guess, consumed later by real orders.
MRP nets requirements against stock and existing receipts, then proposes planned orders to close the gap.
A planned order becomes a production order the moment shop floor execution needs to begin — this is the PP/MM handoff point.
Goods issue and confirmation are two separate events: issuing materials charges actual cost; confirming yield records labor and unlocks the finished-goods receipt.
Settlement is what actually clears the production order's balance — until settlement runs, the order carries a variance that hasn't been assigned anywhere.



Master data quick reference (student 563)

ItemIDDeluxe Touring Bike (black)DXTR1563Deluxe Touring Bike (silver)DXTR2563Deluxe Touring Bike (red)DXTR3563Product groupPG-DXTR563Touring Frame-RedTRFR3563Touring Seat KitTRSK1563Touring Handle BarTRHB1563Touring Aluminum Wheel AssemblyTRWA1563Derailleur Gear AssemblyDGAM1563ChainCHAN1563Brake KitBRKT1563Pedal AssemblyPEDL1563Warranty DocumentWDOC1563PackagingPCKG1563Plant (Dallas)DL00


The PP Challenge (self-test, ~60 min)

Same flow, applied to the Offroad Bicycles product group, focused on ORMN1563:


Apply Strategy Group 40 to the offroad family.
Manual PIRs by period: +1 month → 110, +2 → 150, +3 → 175, +4 → 200, +5 → 85, remaining months → 100.
Convert the first planned order for ORMN1563 into a production order.
Run the full goods receipt/issue/confirmation cycle — note the BOM differs from the touring bike.
Settle costs once production and all goods movements are complete.


No routing changes needed for the challenge.
