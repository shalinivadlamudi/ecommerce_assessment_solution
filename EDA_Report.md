# Comprehensive Data Cleaning & Exploratory Data Analysis Report
**Dataset:** messy_ecommerce_15000_student_practice.csv  
**Cleaned Dataset:** cleaned_ecommerce_dataset.csv  

---

## 1. Dataset Description
The dataset contains 15,075 e-commerce transactions with 16 attributes including customer demographics (`Age`, `Gender`, `City`), transaction metadata (`Order_ID`, `Customer_ID`, `Order_Date`), product details (`Product_Category`, `Product`, `Unit_Price`, `Quantity`), logistics (`Delivery_Days`, `Returned`), and financial outputs (`Discount`, `Total_Amount`).

---

## 2. Data-Quality Problems Identified
1. **Duplicate Records:** 75 exact duplicate rows were detected in the raw dataset.
2. **Inconsistent Categorical Text:** Mixed capitalization in `Gender` (`male`/`Male`), `Payment_Method` (`upi`/`UPI`), and `Returned` (`yes`/`Yes`).
3. **Missing Values:** Null entries present in `Age`, `Gender`, `City`, `Discount`, `Payment_Method`, `Rating`, and `Delivery_Days`.
4. **Data Inconsistency:** Calculation discrepancies existed between raw `Total_Amount` and expected calculated totals (`Unit_Price * Quantity * (1 - Discount/100)`).

---

## 3. Cleaning Techniques Applied
- **De-duplication:** Dropped 75 exact duplicate rows.
- **Categorical Normalization:** Standardized string values using `.str.capitalize()` and `.str.title()`.
- **Imputation:**
  - `Age`, `Rating`, `Delivery_Days` imputed using Median.
  - `Gender`, `City`, `Payment_Method` imputed using Mode.
  - `Discount` imputed with `0.0`.
- **Consistency Correction:** Recalculated `Total_Amount` using exact mathematical formula.

---

## 4. Key Visualizations & Observations
- **Univariate:** `Total_Amount` demonstrates a right-skewed distribution. Age and gender distributions are balanced.
- **Bivariate & Multivariate:** Unit price and quantity show the strongest positive correlation with total order amount.

---

## 5. Top 10 Business Insights
1. **Revenue Drivers:** `Unit_Price` and `Quantity` dictate transaction size.
2. **Category Balance:** Even product demand across categories.
3. **Payment Flexibility:** Balanced adoption across UPI, Credit Card, and Net Banking.
4. **Demographics:** Equal engagement across gender and age tiers.
5. **Returns:** Baseline return rate requires monitored quality assurance.
6. **Discounts:** Standard discounts up to 30% retain order volume.
7. **Fulfillment Speed:** Delivery times (1-7 days) operate efficiently.
8. **Customer Satisfaction:** Ratings average ~3.5 stars across categories.
9. **Regional Demand:** Tier-1 and Tier-2 cities exhibit equal purchasing power.
10. **Dataset Health:** Final cleaned dataset is 100% free of missing values and ready for predictive modeling.

---

## 6. Final Conclusion
The dataset has been thoroughly sanitized, validated for mathematical consistency, and successfully exported to `cleaned_ecommerce_dataset.csv`.
