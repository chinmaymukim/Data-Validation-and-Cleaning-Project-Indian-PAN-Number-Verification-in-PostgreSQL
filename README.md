# Data-Validation-and-Cleaning-Project-Indian-PAN-Number-Verification-in-PostgreSQL
Built a SQL-based data cleaning and validation pipeline to ensure the quality and integrity of PAN (Permanent Account Number) records using PostgreSQL.
The project demonstrates data preprocessing, pattern matching, and validation logic with custom functions, regular expressions, and analytical reporting.

Key Steps & Highlights:
Data Quality Checks
Identified and handled missing values (NULL and blank PAN numbers).
Detected and removed duplicate entries.
Cleaned data by trimming spaces and standardizing to uppercase.
Custom Validation Functions (PL/pgSQL)
fn_check → detected adjacent identical characters in PAN numbers.
fn_check_seq → detected sequential characters to prevent predictable PAN patterns.
Regex-Based Pattern Validation
Ensured PAN format matched ^[A-Z]{5}[0-9]{4}[A-Z]$ (5 letters, 4 digits, 1 letter).

Data Categorization
Classified records into VALID and INVALID PAN categories using CTEs.
Created a reusable view vw_valid_invalid_pans for future analysis.

Summary Reporting
Generated aggregated counts for valid, invalid, and missing PAN numbers.
Produced insights into total processed records and data quality percentages.

Techniques & Tools Used:
SQL (PostgreSQL) – CTEs, window functions, regex, custom functions, data aggregation.
PL/pgSQL – procedural logic for validation rules.
Data Cleaning & Standardization – trimming, uppercasing, deduplication.
Data Quality Metrics – custom views for reporting.

Impact:
Built a repeatable, efficient validation process for identity data.
Improved data integrity by detecting incorrect or suspicious PAN entries before downstream use.
Enabled quick summarization of data quality health.
