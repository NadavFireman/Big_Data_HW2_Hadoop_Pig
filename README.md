# Big Data HW2: Hadoop/Pig Distributed Processing Solution (Grade 85)

This repository contains the solution for the second assignment in the Big Data course (Shenkar College, IE&M). The project processes a fragmented, multi-file customer dataset using **Pig Latin on the Hadoop framework** (MapReduce abstraction) — computing purchase statistics, ranking customers, and performing text processing — with the raw execution output of every script included.

## Key Skills Demonstrated

* **Pig Latin on Hadoop:** LOAD with typed schemas via PigStorage, FOREACH...GENERATE transformations, and DESCRIBE/DUMP inspection with shell (SH) integration for labeled, self-documenting outputs.
* **Multi-File Ingestion:** Combining several source files in a single LOAD glob — simulating fragmented, distributed HDFS inputs.
* **Aggregation & Ranking:** Per-customer total and average across 10 purchase columns, CASE-based segmentation into High/Mid/Low spending tiers, and global ORDER BY + LIMIT to isolate the top and bottom customers.
* **Text Processing:** SIZE for character counts, LOWER for case normalization, CONCAT for merging five text fields, and REPLACE for stop-word removal ("and"/"the") on unstructured text.

## Repository Structure

### Pig Scripts (Solution Code)

| File | What it does |
| :--- | :--- |
| `00_load_and_describe.pig` | Baseline script: loads the multi-file dataset with a typed 16-field schema (PigStorage), prints the schema with DESCRIBE, and dumps the full combined data for inspection. |
| `01_purchase_summary_tiers.pig` | Task 1, output 1: computes each customer's total and average across the 10 purchase columns, labels them High/Mid/Low average using a CASE expression, and sorts from highest to lowest average. |
| `02_top_customer_by_avg.pig` | Task 1, output 2: isolates the single customer with the **highest** purchase average via ORDER BY ... DESC + LIMIT 1. |
| `03_bottom_customer_by_avg.pig` | Task 1, output 3: isolates the single customer with the **lowest** purchase average via ORDER BY + LIMIT 1. |
| `04_text_processing.pig` | Task 2: per customer, counts total characters across text1–text5 (SIZE), lowercases text2 (LOWER), concatenates all five text fields (CONCAT), and produces "and"-free and "the"-free versions (REPLACE). |

### Execution Outputs (Results)

| File | What it shows |
| :--- | :--- |
| `output_00_load.txt` | The declared schema + the full combined dataset as loaded. |
| `output_01_purchase_summary_tiers.txt` | All customers with sum, average, and High/Mid/Low tier, sorted by average. |
| `output_02_top_customer.txt` | The top customer by purchase average (FGFZV31, avg 6954.3). |
| `output_03_bottom_customer.txt` | The bottom customer by purchase average (ETZB14, avg 3912.9). |
| `output_04_text_processing.txt` | Character counts, lowercased text, and the concatenated text with stop-words removed. |

### Data & Documentation

| File | Role |
| :--- | :--- |
| `data000.txt`, `data002.txt` | Raw input data files (40 customer records each: purchases + free-text fields), combined at load time. |
| `Assignment_Instructions_2.pdf` | Original assignment instructions. |

***
*Course: Big Data (Hadoop/Pig), Shenkar College, IE&M*
