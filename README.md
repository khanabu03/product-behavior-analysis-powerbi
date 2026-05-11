# Product Behaviour Analysis: Identifying High-Value User Patterns

## Project Overview

This project analyzes product event data to identify behavioural patterns that separate high-value users from low-value users.

The goal of this analysis is to understand which user actions are associated with stronger engagement and higher product value. Instead of focusing only on surface-level activity such as views, this project investigates whether deeper behaviours like wishlist, cart, and purchase actions provide stronger signals of valuable users.

## Business Objective

The main business question:

**What behaviours separate high-value users from low-value users?**

This analysis helps product and growth teams understand:
- Which users are most engaged
- Which behaviours indicate higher user value
- Which actions should be prioritized in product optimization
- Whether views alone are a reliable success metric

## Dataset Overview

The dataset contains product event data with approximately:

- **9,995 users**
- **80,000 events**
- **4 event types**
- Time range: **January 2024 to November 2025**

### Key Columns Used

| Column | Description |
|---|---|
| `user_id` | Unique identifier for each user |
| `event_id` | Unique identifier for each event |
| `event_type` | Type of product action performed |
| `event_timestamp` | Time when the event occurred |

### Event Types Analyzed

The analysis focuses on four major event types:

- `view`
- `wishlist`
- `cart`
- `purchase`

## Tools Used

- **Power BI** — dashboard creation and visual analysis
- **DAX** — calculated tables, measures, and segmentation logic
- **Data Modeling** — user-level summary table and event-level analysis

## Methodology

### 1. User-Level Summary Table

A user-level table was created to summarize each user’s behaviour across the dataset.

Key user-level metrics included:

- Total events per user
- Number of distinct event types used
- First event timestamp
- Last event timestamp

This transformed the raw event level data into a user level structure suitable for segmentation.

### 2. User Segmentation

Users were classified into two groups:

| Segment | Definition |
|---|---|
| **High-Value Users** | Users with at least 12 total events and at least 3 distinct event types |
| **Low-Value Users** | All remaining users |

This segmentation was designed to identify users with both high engagement depth and broader behavioural variety.

### 3. Behaviour Adoption Analysis

A user-event table was created to identify whether each user performed each event type at least once.

This allowed the analysis to calculate:

- Percentage of high-value users performing each action
- Percentage of low-value users performing each action
- Behaviour gap between the two segments

## Dashboard Pages

### Page 1: Product Behaviour Summary

This page provides a high-level overview of user segmentation and engagement differences.

It includes:
- Total users
- High-value users
- Low-value users
- High-value user share
- User distribution by segment
- Average total events by segment
- Average distinct event types by segment

![Product Behaviour Summary](visuals/01_product_behaviour_summary.png)
<img width="980" height="553" alt="image" src="https://github.com/user-attachments/assets/8321d90f-45d1-41cc-b986-9c5d2860abe5" />


### Page 2: Behavioural Drivers of High-Value Users

This page identifies which behaviours separate high-value users from low-value users.

It includes:
- Behaviour adoption by segment
- Behaviour gap between high-value and low-value users
- Key recommendation based on behavioural differences

![Behavioural Drivers of High-Value Users](visuals/02_behavioural_drivers.png)
<img width="973" height="548" alt="image" src="https://github.com/user-attachments/assets/bec0afc2-af16-4a53-b64f-3892cdad13dc" />


## Key Findings

### 1. High-value users are a small but important segment

High-value users represent only **9.3%** of the total user base.

Despite being a minority, they show stronger engagement depth and broader behavioural variety compared to low-value users.

### 2. High-value users engage more deeply

High-value users average:

- **13.18 total events**
- **3.39 distinct event types**

Low-value users average:

- **7.47 total events**
- **2.49 distinct event types**

This suggests that high-value users are not only more active, but also interact with more parts of the product experience.

### 3. Views are not a strong value signal

View behaviour is nearly universal across both high-value and low-value users.

This makes views a weak differentiator of user quality.

### 4. Wishlist, cart, and purchase behaviours separate high-value users

The largest behavioural gaps were found in:

| Event Type | High-Value Users | Low-Value Users | Gap |
|---|---:|---:|---:|
| Wishlist | 86.73% | 51.83% | 34.90% |
| Purchase | 59.12% | 30.14% | 28.98% |
| Cart | 92.66% | 67.66% | 25.01% |
| View | 100.00% | 99.63% | 0.37% |

Wishlist, purchase, and cart actions are much stronger indicators of high-value engagement than views.

## Business Recommendation

Product teams should avoid treating views as the main success metric.

Instead, they should focus on moving users from passive browsing into stronger intent based actions such as:

- Adding products to wishlist
- Adding products to cart
- Completing purchases

Wishlist behaviour shows the largest gap between high-value and low-value users, making it a strong signal for targeting, personalization, and future engagement campaigns.

## Final Insight

High-value users are not defined by viewing behaviour alone. They are defined by deeper lifecycle engagement and stronger adoption of intent based product actions.

The key product opportunity is to optimize the user journey from:

**View → Wishlist → Cart → Purchase**

By encouraging wishlist and cart behaviour, the product team may be able to increase the likelihood of users becoming high-value.

## Limitations

- The dataset does not include demographic data, marketing channel data, or acquisition source.
- Revenue or transaction value was not included, so “high-value” was defined behaviourally rather than financially.
- The analysis focuses on behavioural engagement, not profitability.
- Causation cannot be assumed; the analysis identifies associations between behaviour and user value.

## Files Included

```text
product-behavior-analysis-powerbi/
│
├── README.md
├── powerbi/
│   └── product_behavior_analysis_final.pbix
├── visuals/
│   ├── 01_product_behaviour_summary.png
│   └── 02_behavioural_drivers.png
└── data/
    └── README.md
