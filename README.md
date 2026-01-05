# Data-Validation-and-Cleaning-Project-Indian-PAN-Number-Verification-in-PostgreSQL
Designed and implemented a robust SQL-driven data validation and cleaning pipeline to ensure the accuracy, consistency, and integrity of Indian PAN (Permanent Account Number) records using PostgreSQL. This project showcases strong expertise in data preprocessing, rule-based validation, pattern recognition, and analytical reporting, all built with scalable and reusable database logic.

Project Overview

The objective of this project was to identify, clean, and validate PAN records by applying business rules, structural checks, and anomaly detection techniques directly at the database level. The solution emphasizes automation, reusability, and data quality monitoring, making it suitable for real-world financial or compliance-driven systems.

Key Steps & Highlights
1. Data Quality Assessment & Cleaning

Identified and handled missing PAN values, including both NULL and blank entries.

Detected and eliminated duplicate PAN records to prevent data redundancy.

Standardized PAN values by:

Trimming leading and trailing whitespace

Converting all characters to uppercase for consistency

2. Advanced Validation using Custom PL/pgSQL Functions

Developed custom validation functions to detect suspicious or invalid PAN patterns:

fn_check → Identified PANs containing adjacent identical characters, which may indicate data entry errors or fabricated values.

fn_check_seq → Flagged PANs with sequential characters (alphabetic or numeric), helping prevent predictable or weak identifiers.

Embedded procedural logic to extend validation beyond basic format checks.

3. Regex-Based Structural Validation

Enforced official PAN format compliance using regular expressions:

^[A-Z]{5}[0-9]{4}[A-Z]$


Ensures correct structure: 5 uppercase letters, 4 digits, and 1 uppercase letter

Combined regex validation with custom logic for higher accuracy.

4. Data Classification & Reusability

Categorized PAN records into VALID and INVALID groups using CTEs (Common Table Expressions).

Created a reusable database view vw_valid_invalid_pans to:

Simplify downstream analysis

Enable consistent validation logic across applications

5. Summary Reporting & Data Quality Metrics

Generated aggregated reports showing:

Total PANs processed

Counts of valid, invalid, and missing PAN records

Calculated data quality percentages to measure overall dataset health.

Enabled quick insights for compliance checks and auditing purposes.

Techniques & Tools Used

PostgreSQL / SQL

CTEs, window functions, regex pattern matching

Custom views and aggregation queries

PL/pgSQL

Procedural functions for complex validation rules

Data Cleaning & Standardization

Trimming, uppercasing, deduplication

Data Quality Reporting

Reusable views and summary metrics

Impact & Business Value

Built a repeatable and scalable validation framework for sensitive identity data.

Significantly improved data integrity and reliability by identifying invalid, missing, or suspicious PAN entries early in the pipeline.

Reduced risk in downstream processes such as financial reporting, compliance checks, and analytics.

Provided stakeholders with clear visibility into data quality health through summary metrics and reporting views.
