# Big Data HW2: Hadoop/Pig Distributed Processing Solution

This repository contains the solution for the second assignment in the Big Data course (Shenkar College, IE&M). The project processes a fragmented, multi-file customer dataset using **Pig Latin on the Hadoop framework** (MapReduce abstraction) — computing purchase statistics, ranking customers, and performing text processing — with the raw execution output of every script included.

## Key Skills Demonstrated

* **Pig Latin on Hadoop:** LOAD with typed schemas via PigStorage, FOREACH...GENERATE transformations, and DESCRIBE/DUMP inspection with shell (SH) integration for labeled, self-documenting outputs.
* **Multi-File Ingestion:** Combining several source files in a single LOAD glob — simulating fragmented, distributed HDFS inputs.
* **Aggregation & Ranking:** Per-customer total and average across 10 purchase columns, CASE-based segmentation into High/Mid/Low spending tiers, and global ORDER BY + LIMIT to isolate the top and bottom customers.
* **Text Processing:** SIZE for character counts, LOWER for case normalization, CONCAT for merging five text fields, and REPLACE for stop-word removal ("and"/"the") on unstructured text.

## Repository Content

* **`00_load_and_describe.pig`**: Baseline script — loads the multi-file dataset with a typed 16-field schema (PigStorage), prints the schema with DESCRIBE, and dumps the full combined data for inspection.
* **`01_purchase_summary_tiers.pig`**: Computes each customer's total and average across the 10 purchase columns, labels them High/Mid/Low average using a CASE expression, and sorts from highest to lowest average.
* **`02_top_customer_by_avg.pig`**: Isolates the single customer with the highest purchase average using ORDER BY ... DESC + LIMIT 1.
* **`03_bottom_customer_by_avg.pig`**: Isolates the single customer with the lowest purchase average using ORDER BY + LIMIT 1.
* **`04_text_processing.pig`**: Per customer — counts total characters across text1–text5 (SIZE), lowercases text2 (LOWER), concatenates all five text fields (CONCAT), and produces "and"-free and "the"-free versions (REPLACE).
* **`output_00_load.txt`**: Execution output — the declared schema and the full combined dataset as loaded.
* **`output_01_purchase_summary_tiers.txt`**: Execution output — all customers with sum, average, and High/Mid/Low tier, sorted by average.
* **`output_02_top_customer.txt`**: Execution output — the top customer by purchase average (FGFZV31, avg 6954.3).
* **`output_03_bottom_customer.txt`**: Execution output — the bottom customer by purchase average (ETZB14, avg 3912.9).
* **`output_04_text_processing.txt`**: Execution output — character counts, lowercased text, and the concatenated text with stop-words removed.
* **`data000.txt`**, **`data002.txt`**: Raw input data files (40 customer records each: purchase amounts + free-text fields), combined at load time.
* **`Assignment_Instructions_2.pdf`**: Original assignment instructions.
