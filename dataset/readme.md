## **Dataset**

This directory contains the datasets used throughout the project after applying preprocessing, cleaning steps, or transformations.

These files represent the processed versions derived from the original census microdata, prepared for analysis and modeling.

---
**Original Data Source**

The original Uruguay Census 2023 microdata can be downloaded from the National Institute of Statistics (INE):

https://www5.ine.gub.uy/documents/CENSO%202023/Microdatos/personas_ext_26_02.rar

---
**personas_clean_csv.zip**

The file personas_clean_csv.zip contains a processed and standardized
version of the original Uruguay Census 2023 microdata.

This dataset was generated after applying structured preprocessing steps
in PySpark to ensure data quality, consistency, and modeling readiness.

**Transformations Applied**

1. Schema Standardization

-   Renamed raw census variables to normalized, analysis-ready column
    names.
-   Reduced the dataset to a curated feature set:

    ID, age, sex, works, education, municipality, departament

---
2. Data Validation & Filtering

-   Removed invalid age codes (e.g., placeholder values such as 5555).
-   Filtered age values outside a plausible range (0–110).
-   Preserved only valid categorical values for sex.

---
3. Categorical Recoding

-   Re-encoded works as a binary variable:
    -   1 → employed
    -   0 → not employed
    -   Special or non-response codes → NULL
-   Transformed education into an ordinal scale reflecting increasing
    educational attainment.
    -   Non-valid or undefined codes → NULL

---
4. Null Handling

-   Explicit conversion of special census codes (e.g., 7777, 8888, 9898)
    into NULL.
-   Maintained NULL values intentionally for downstream modeling
    decisions (no imputation applied at this stage).

---
