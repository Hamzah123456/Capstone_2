# Capstone\_2

\# Capstone 2: Emporium Sales Territory Analysis



\*\*Analyst:\*\* Hamzah Alssoudi

\*\*Course:\*\* Year Up United — Data Analyst



\## Project Description

EmporiUm is a growing student bookstore chain that also sells tech gear, art supplies, and other

products. This project reads, cleans, and analyzes EmporiUm's sales data to compare two assigned

sales territories and recommend where the retail marketing team should focus next quarter.



\## Territories Analyzed

| Territory | State | Territory Manager | Region |

|-----------|-------|-------------------|--------|

| Territory 1 | \*\*Maryland\*\* | Shruti Reddy | Northeast |

| Territory 2 | \*\*Massachusetts\*\* | Bo Heap | Northeast |



Both territories are in the \*\*Northeast\*\* region (a same-region comparison). The data spans

\*\*January 1, 2022 – December 31, 2025\*\*.



\## Files in This Repository

| File | Description |

|------|-------------|

| `alssoudi\_sales\_analysis.ipynb` | \*\*Core Marketing Analysis\*\* — answers the marketing manager's six questions (Steps 6–8), with 2 Matplotlib charts. |

| `alssoudi\_bonus\_analysis.ipynb` | \*\*Bonus Analysis\*\* — all 15 appendix questions, with 3 additional Matplotlib charts. |

| `alssoudi\_5min\_presentation.pptx` | \*\*5-minute live presentation slides\*\* for in-class delivery. |

| `StoreSales.csv` | Transaction-level sales (the fact table). |

| `StoreDetail.csv` | Store dimension: location, state, manager, region. |

| `Products.csv` | Product dimension: product number, category/subcategory IDs. |

| `ProductCategories.csv` | Lookup of readable category/subcategory names. |

| `customer\_list.csv` | Rewards member list (pipe-delimited). |

| `README.md` | This file. |



\## How the Data Connects

\- `StoreSales` → `StoreDetail` on \*\*Store ID\*\*

\- `StoreSales` → `Products` on \*\*Prod Num\*\*

\- `Products` → `ProductCategories` on \*\*CategoryID + SubcategoryID\*\*

\- `StoreSales` → `customer\_list` on \*\*RewardsID = cust\_id\*\* (rewards transactions only; \~10% of sales)



\## Data Cleaning Notes

Two data-quality issues were found during exploration and handled deliberately:



1\. \*\*Orphan adhesive products\*\* — five products carry `CategoryID` 115 (Art Supplies) but an

&#x20;  invalid `SubcategoryID` (`110-adh`). They were retained and labeled Art Supplies / Adhesives

&#x20;  so their \~1,200 transactions still count toward category totals.



2\. \*\*Duplicate category key\*\* — subcategory `115-pai` appears twice in the lookup (once as

&#x20;  "Paint Brushes" and once as "Paints"), which would duplicate every paint transaction on

&#x20;  merge. It was collapsed to a single "Paints \& Brushes" row, keeping the transaction count

&#x20;  at the true 335,129 rows from the source file.



\## Key Findings

\- \*\*Maryland leads on total revenue\*\* (\~$11.5M vs. \~$5.7M) despite having \*\*half the stores\*\*

&#x20; (9 vs. 18).

\- \*\*But Maryland's lead depends almost entirely on one store\*\* — North Harford generates \~$8.8M

&#x20; on its own, which is \*\*more than all 18 Massachusetts stores combined\*\*.

\- \*\*Without North Harford, Maryland is actually the smaller territory.\*\* The other 8 Maryland

&#x20; stores aren't doing anything exceptional.

\- \*\*Massachusetts revenue is evenly distributed\*\* across its 18 stores — broad, even, with real

&#x20; growth headroom on a per-store basis (\~$319K/store vs. Maryland's \~$1.27M/store).

\- \*\*Technology \& Accessories dominates revenue\*\* in both territories, followed by Textbooks.

&#x20; Smaller categories (Books, Art Supplies, Stationery) are growth opportunities, especially in

&#x20; Massachusetts where they under-index versus Maryland.

\- \*\*Both territories trend upward\*\* every year from 2022 to 2025. A linear regression on

&#x20; combined monthly revenue confirms a positive overall slope.

\- \*\*Rewards coverage is low\*\* — only \~10% of transactions are tied to a known customer; the

&#x20; other 90% are anonymous.



\## Recommendation

Focus next quarter's marketing on \*\*Massachusetts\*\* to lift its weak per-store performance

(18 stores with large untapped headroom and momentum from 2025), while \*\*diversifying Maryland's

revenue\*\* beyond its dependence on the North Harford store and \*\*growing the rewards base\*\* in

both territories to improve future targeting.



> \*"Massachusetts has the runway. Maryland has a single point of failure. And we need to know

> who our customers are."\*



\## Running the Notebooks

Requires Python with `pandas`, `numpy`, and `matplotlib`. Open each notebook in Jupyter and

choose \*\*Kernel → Restart \& Run All\*\*; both execute cleanly from top to bottom.



\## Video Demo

\*(Add your recording link here once uploaded.)\*



\## Live Presentation

A 5-minute slide deck (`alssoudi\_5min\_presentation.pptx`) is included for the in-class

presentation.

