# Data Description

## 1. Background

This dataset is a core feature subset constructed for **logistics waybill claim and customer complaint analysis**. It integrates multiple aspects of information, including:

- Waybill attributes
- Transportation conditions
- Customer complaint information
- Hub (node) statistical features
- Product-related information
- Claim outcomes

The dataset contains **4,948 samples** in total and is mainly used for:

- Claim prediction
- Customer complaint risk identification
- In-depth analysis of abnormal waybills

------

## 2. Number of Samples

A total of **4,948 waybill records** are included in this dataset.

------

## 3. Data Content

The dataset consists of the following categories of features (English field names are provided in parentheses):

### 3.1 Waybill Attributes

- Insured amount (`waybill_price_protect_money`)

------

### 3.2 Transportation Information

- Delivery delay duration (`plan_delv_to_real_delv_diff`)
- Abnormal reason (`abnormal_reason`)
- Transport type (`transport_type`)
  - 1: Road
  - 2: High-speed rail
  - 3: Air

------

### 3.3 Customer Complaint Features

- Source channel (`source`)
- Time from delivery to complaint initiation (`real_delv_to_case_create_diff`)
- Claimed compensation amount (`payment_contract_money`)

------

### 3.4 Product and Behavioral Features

- Product category (`goods_category`)
- Item type (`goods_type`)
- Condition level (`goods_level`)
- Sender type B/C (`bc_source`)
- Customer role (`customer_role`)

------

### 3.5 Hub Statistical Features

- Number of waybills at origin hub (`start_node_waybill_num`)
- Claim rate per 10,000 orders at origin hub (`start_node_accident_rate`)
- Compensation ratio at origin hub (`start_node_real_claim_num_ratio`)
- Number of waybills at destination hub (`end_node_waybill_num`)
- Claim rate per 10,000 orders at destination hub (`end_node_accident_rate`)
- Compensation ratio at destination hub (`end_node_real_claim_num_ratio`)

------

### 3.6 Claim Outcome

- Actual compensation amount (`payment_real_money`)

------

## 4. Notes

### 4.1 Sample Representativeness

This dataset may be a **selected subset of waybills related to claims or complaints**, and its distribution may differ from the full dataset.
Therefore, attention should be paid to potential bias when conducting analysis.

------

### 4.2 Time-related Features

- `plan_delv_to_real_delv_diff` and `real_delv_to_case_create_diff` may contain **negative values or missing values**.
- Proper data cleaning is required before use.

------

### 4.3 Compensation Amount

- The actual compensation amount is generally influenced by the insured amount and the claimed amount.
- However, **not all waybills result in compensation**, so the target variable should be clearly defined when modeling.

------

### 4.4 Hub Features

- Hub-related statistical features are aggregated over the **past six months**.
- If the dataset spans a long time period, the **temporal validity** of these features should be considered.