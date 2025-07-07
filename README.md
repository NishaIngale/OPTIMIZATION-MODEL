# OPTIMIZATION-MODEL
# 🏭 Warehouse-to-Store Allocation Optimization

This repository contains a complete solution for optimizing the shipment of multiple products from multiple warehouses to multiple stores using **linear programming** with **PuLP**. It aims to **minimize shipping costs** while satisfying store demand and respecting warehouse stock limitations.

---

## 📋 Problem Description

A company needs to ship two products (P1, P2) from two warehouses (W1, W2) to three stores (S1, S2, S3). The goal is to minimize the total shipping cost under these conditions:

1. **Warehouse stock limits** must not be exceeded.
2. **Store demands** must be fully satisfied.
3. Shipping is in **whole units** (integer decision variables).
4. **Cost per unit** varies by product and route.

---

## 📦 Data Overview

All parameters are hard-coded in the script:

- **Warehouses & Stock**:
  - W1: P1 = 100 units, P2 = 80 units  
  - W2: P1 = 90 units, P2 = 120 units  

- **Store Demand**:
  - S1: P1 = 70, P2 = 60  
  - S2: P1 = 80, P2 = 70  
  - S3: P1 = 40, P2 = 50  

- **Shipping Costs (₹ per unit)**:

  | Route    | P1 | P2 |
  |----------|----|----|
  | W1 → S1  | 4  | 6  |
  | W1 → S2  | 5  | 5  |
  | W1 → S3  | 6  | 4  |
  | W2 → S1  | 5  | 4  |
  | W2 → S2  | 4  | 6  |
  | W2 → S3  | 3  | 5  |

---

## 🔧 Getting Started

### Prerequisites

- Python 3.7+  
- [PuLP](https://python-pulp.readthedocs.io/en/latest/)

Install PuLP via:

```bash
pip install pulp
```
---

## 🧰 Understanding the Model
# **Decision Variables**: ship[warehouse][store][product] – integer units shipped.

# **Objective Function**: Minimize total shipping cost across all routes.

# **Constraints**:

1. ∑ shipments from warehouse ≤ warehouse stock (for each product)

2. ∑ shipments to store ≥ store demand (for each product)

---

### 📈 Results & Output
1. Displays the optimal shipping plan, e.g.:
Ship 70 units of P1 from W1 to S1
Ship 80 units of P1 from W2 to S2
...
Ship 50 units of P2 from W2 to S3

2. Shows total minimized shipping cost:
Total shipping cost ₹ 1580.0

---

🧠 References
1. PuLP Documentation
2. Basics of linear programming and supply-chain optimization

---

Crafted by Nisha during her data science internship at CODTECH 💡
For questions or feedback: [nishaingale70@gmail.com] 
