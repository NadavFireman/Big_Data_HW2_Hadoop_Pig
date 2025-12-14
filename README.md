# Big Data HW2: Hadoop Pig Solution (Grade 85)

This repository contains the solution for the second submission assignment in the Big Data course (Shenkar College, IE&M), focusing on distributed data processing using the **Pig Latin** framework on Hadoop.

The project successfully implemented core Big Data engineering skills, including complex aggregation and text processing on fragmented datasets, achieving a grade of **85**.

## Key Skills Demonstrated

* **Pig Latin Mastery:** Utilizing the Pig Latin language for efficient data manipulation and analysis in a distributed environment (MapReduce abstraction).
* **Advanced Text Processing:** Applying Pig functions (SIZE, LOWER, CONCAT, REPLACE) for data cleaning and extraction on unstructured text data.
    * **Note on Case Sensitivity:** The use of functions like `LOWER()` demonstrates the ability to handle data inconsistencies and perform case-insensitive comparisons, a critical task in Big Data pipelines.
* **Distributed Aggregation:** Implementing complex averaging and filtering logic across multiple input files simultaneously.
* **Multi-File Data Handling:** Demonstrating proficiency in loading and combining data from fragmented sources, typical of an HDFS (Hadoop Distributed File System) environment.

## Repository Content

| File Name | Description |
| :--- | :--- |
| **`DATA.txt`, `DATA1.txt`... `DATA4.txt`** | **Pig Scripts:** The working scripts written in Pig Latin. These files contain the logic for averaging, filtering, ordering (DATA1-3), and advanced text manipulation (DATA4). |
| **`df.txt`... `df4.txt`** | **Output Files:** Segmented output files as required by the assignment, showing the results of the Pig scripts (e.g., maximum average, minimum average, and final text processing results). |
| **`data000.txt`, `data002.txt`** | **Input Data:** Sample raw input files used for the distributed processing. |
| **`Assignment_Instructions_2.pdf`** | Original assignment instructions. |

***
*Course: Big Data (Hadoop/Pig), Shenkar College, IE&M*
