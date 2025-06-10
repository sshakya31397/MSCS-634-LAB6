# MSCS 634 – Lab 6: Frequent Itemset Mining with Apriori and FP-Growth


Sauhard Shakya
MSCS 634 – Advanced Big Data Analytics
Lab 6 – Frequent Itemset Mining and Association Rule Learning

---

## Objective

This lab explores frequent itemset mining and association rule generation using two popular algorithms: **Apriori** and **FP-Growth**. The `Online Retail` dataset was used to uncover frequent purchase patterns and generate actionable insights using support, confidence, and lift metrics.

---

## Dataset Summary

- **Rows**: 541,909  
- **Columns**: 8  
- **After Cleaning**: 530,669 valid transactions  
- **Transactions (Invoices)**: 20,136  
- **Unique Items**: 4,077  
- **Top Items by Quantity**:  
  - WHITE HANGING HEART T-LIGHT HOLDER  
  - JUMBO BAG RED RETROSPOT  
  - REGENCY CAKESTAND 3 TIER  
  - PARTY BUNTING  

---

## Key Steps

- Cleaned data (removed cancelled, missing, or zero-quantity transactions).
- Visualized top-selling items using Seaborn bar plots.
- Created a transaction–item basket matrix (1 if bought, 0 if not).
- Applied Apriori and FP-Growth algorithms with a support threshold of 2%.
- Generated association rules with confidence and lift.
- Visualized confidence vs. lift using scatter plots.

---

## Comparative Analysis: Apriori vs FP-Growth

### 1. Frequent Itemset Mining

| Aspect                    | Apriori                                | FP-Growth                              |
|---------------------------|-----------------------------------------|----------------------------------------|
| **Number of Itemsets**    | 375                                     | 375                                    |
| **Top Items (by Support)**| Matches sales frequency: e.g., “WHITE HANGING HEART T-LIGHT HOLDER” | Similar top items with same support |
| **Speed**                 | Slower with large data                  | Faster due to tree-based compression   |
| **Efficiency**            | Multiple scans, memory intensive        | Single scan, better memory usage       |

---

### 2. Pattern & Rule Quality

| Metric              | Observation                              |
|---------------------|-------------------------------------------|
| **Support**         | Both methods met threshold consistently. |
| **Confidence**      | Ranged from 0.4 to 0.9 → strong rules.   |
| **Lift**            | High lift (>5, even 10+) in many rules.  |

Scatter plots showed well-separated rules with strong confidence and lift clustering.

---

## Conclusions

- **FP-Growth outperforms Apriori** in speed and scalability while producing the same results.
- **Apriori is easier to grasp**, but becomes computationally expensive.
- **Both algorithms found high-quality rules**, confirming robust purchase trends.
- **Strong associations** (like clock or cake items) can inform promotions or bundling strategies.

---

## Challenges Faced

- Memory inefficiencies when using raw quantity instead of binary data.
- Handling string conversion for itemset visualization.
- Tuning `min_support` to avoid excessive or zero frequent itemsets.

---

## Next Steps

- Filter rules by lift/confidence thresholds.
- Export itemsets and rules to CSV.
- Integrate findings into a recommendation engine.
