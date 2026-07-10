# Big Data HW2: Hadoop/Pig Solution (Grade 85)

This repository contains the solution for the second assignment in the Big Data course (Shenkar College, IE&M) — Pig Latin scripts running on Hadoop that process a fragmented, multi-file customer dataset: purchase statistics, customer ranking, and text processing, with the raw execution output of every script included.

## Key Skills Demonstrated

* **Pig Latin on Hadoop (MapReduce abstraction):** LOAD with typed schemas via PigStorage, FOREACH...GENERATE transformations, and DESCRIBE/DUMP inspection with shell (SH) integration for labeled outputs.
* **Multi-File Ingestion:** Combining several source files in a single LOAD glob — '{data000.txt, data000.txt, data002.txt}' — simulating fragmented HDFS inputs.
* **Aggregation & Ranking:** Per-customer total and average across 10 purchase columns, CASE-based segmentation into High/Mid/Low tiers, and global ORDER BY + LIMIT to extract the top and bottom customers.
* **Text Processing:** SIZE for character counts, LOWER for normalization, CONCAT for merging five text fields, and REPLACE for stop-word removal ("and"/"the").

## Repository Structure

| File | Role |
| :--- | :--- |
| `00_load_and_describe.pig` | Loads the multi-file dataset with a typed schema and dumps it for inspection |
| `01_purchase_summary_tiers.pig` | Sum + average per customer, High/Mid/Low tiering (CASE), sorted by average |
| `02_top_customer_by_avg.pig` | The single customer with the highest purchase average (ORDER + LIMIT) |
| `03_bottom_customer_by_avg.pig` | The single customer with the lowest purchase average |
| `04_text_processing.pig` | Character counts, lowercasing, concatenation, and "and"/"the" removal |
| `output_0X_*.txt` | Raw execution output of each script, including DESCRIBE schemas |
| `data000.txt`, `data002.txt` | Raw input data files |
| `Assignment_Instructions_2.pdf` | Original assignment instructions |

***
*Course: Big Data (Hadoop/Pig), Shenkar College, IE&M*
