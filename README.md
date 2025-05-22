# ☕ Analysis of Starbucks Promotional Campaign and Customer Segmentation

## 🎯 Objective

To understand customer response to different offers in order to come up with better approaches to sending customers specific promotional deals.

## 🖼 Business Questions

1. What are better approaches to sending customer offers?
2. What are recommended strategies regarding specific customer groups?
   
<img width="995" alt="Screenshot 2025-05-22 at 01 03 25" src="https://github.com/user-attachments/assets/5148dd85-ec68-488a-84a4-748b893f8b91" />

## 🗂️ Dataset Overview

Data is provided by Starbucks, simulating their customer demographics and transactional activities during a promotional campaign. [Link](https://www.kaggle.com/datasets/ihormuliar/starbucks-customer-data) 

The campaign lasted for one month, during which customers received a variety of offers.

Three data files are provided:

- **portfolio.csv** - data about offers sent to customers (10 offers x 6 columns)

- **profile.csv** - demographic data of customers (17,000 customers x 5 columns)

- **transcript.csv** - customer response to offers and transactions made (306,648 events x 4 columns)

### Offers and Customers

- Offers of different types, duration, reward and difficulty.

- Promotional channels (social media, email, mobile app and websites).

- Age, gender, income and date of becoming a member.

- Not all customers received the same number of offers. Most customers received between 3 to 5 during the month, and some even received none.

### Events

- Customer response to these offers and transactions made during the month. 

- Three offer-related types of events: offer received, offer viewed and offer completed.

- Transaction or purchases made by a customer. 

- Time (hour) is when each event occurred since the start of the campaign (the first offer was sent when time = 0 hour).

## 🧩 Proposed Solution

**1. Data Preprocessing**

- Drop any irrelevant columns and drop/fill missing values.

- Convert columns to their proper format.
  
- Add a column 'offer_alias' to examine by the offer type.
  
- Use feature engineering by creating and merging new columns to the datasets.

**2. Exploratory Data Analysis**

- Understand the customer profile, customer event behaviors and customer spending behaviors.

- Analyze the offer porfolio and offer effectiveness.

**3. Modeling**

- **Classification (Logistic Regression, Random Forest):** Explore the factors affecting the offer completion.

- **Clustering (KMeans, PCA):** Segment customers into different groups to target personalized strategies.

## 🧠 Key Findings

### Customer Profile

- Majority of customers are male, followed by female, with a smaller "Other" group.

- Most customers are between 40 and 70 years old, with a peak around 50–60 years, representing a mature, working-age population.

- Customer incomes mainly range from 50,000 to 80,000, indicating a middle- to upper-middle-class customer base.

### Offer Portfolio

- Starbucks promoted BOGO (Buy-One-Get-One) and Discount offers equally (~4 each), while Informational offers (no reward, just marketing) were less common.

- Most offers lasted around 5 to 7 days, while longer 10-day offers were less common. Shorter 3–4 day offers were even rarer.

- Higher rewards come with higher difficulty, and difficult offers are typically available for a longer period, giving customers more time to complete them.

- BOGO and Discount offers offer tangible rewards but differ in difficulty and duration. Discount offers are more variable in difficulty and tend to last longer. Informational offers, as expected, provide no rewards and are easier and shorter in duration.

### Customer Event Behavior

- Transactions are the most frequent events, followed by offer received, offer completed, and offer viewed. This suggests that while transactions are common, not all customers fully engage with the offer cycle.

- Customer activity shows clear spikes at regular intervals throughout the campaign, possibly linked to marketing pushes or offer release schedules. Activity peaks roughly every few days, indicating bursts of customer engagement.

- Customer engagement spikes periodically throughout the campaign, indicating the impact of scheduled offer releases.

### Offer Effectiveness

- Offers B, D, E, F had the highest view rates (close to 1), meaning almost every customer who received them also viewed them.

- Offers G, H, I had much lower view rates, suggesting that these offers were less attractive or less noticed after being received.

- Offers G and H (although not viewed much) had very high completion rates — if they were viewed, customers were highly motivated to complete them.

- Offers I and J had zero completion rates, meaning either they were never completed or were not effective even if viewed.

### Customer Spending Behavior

- Most individual transactions are small, under $20. Very few transactions are large, leading to a highly skewed distribution.

- The majority of customers spent relatively low amounts overall (below 200). A small number of customers are high spenders, with totals reaching over $1,000.

### Modeling

- **Age** and **income** are by far the most influential predictors, followed by reward and difficulty of the offer. Marketing channels and gender information are less influential for predicting offer completion.

- The optimal customer groups are 5:
   
   -  **Low-Engagement Customers:** Lowest transactions, lowest spending, lower offer completion.
   
   -  **High-Value Loyalists:** High transactions (10.4), highest spending (265), and high offer completion (8.25 offers). Likely the most engaged and high-value customers.
   
   - **Low-Spend Infrequent Users:** Low spending, low engagement — possible lower-priority group.

   - **Affluent Moderates:** Older, wealthier, but medium engagement — mid-range in transactions and offer completions.

   - **Frequent Low-Spenders:** Most frequent buyers (15.1 transactions) but lower spending (122) per transaction. Younger, moderately active customers.  

## 🚀 Recommendations

-  **Low-Engagement Customers:** Hard to convert with normal campaigns — deprioritize or target only with high-impact efforts:

   - Avoid routine promotions.

   - Focus on surprise campaigns or major brand events.

   - Use “win-back” discounts only occasionally.

   - Or reallocate budget away from this group to higher ROI segments. 
   
-  **High-Value Loyalists:** Ensure high satisfaction and retention. They’re already loyal, so focus on making them feel special:

   - Send birthday cards with coupons.
   
   - Offer surprise gifts on holidays like Valentine’s Day, Mother’s Day, or Halloween.

   - Maintain service quality and test exclusive perks to reinforce their value.
  
- **Low-Spend Infrequent Users:** Nurture early relationship and re-engage:
   
   - Send welcome campaigns with introductory offers.

   - Highlight popular drinks or bundles to spark interest.

   - Provide free drink coupons or “buy 1 get 1” promos.

   - Use email/SMS to share upcoming events or product highlights.

- **Affluent Moderates:** Increase engagement and build habit:
   
   - Send more frequent, personalized offers.

   - Offer a free drink to show appreciation and initiate habit formation.

   - Start a monthly newsletter (with consent) to share new products and promotions.
   
   - Create VIP preview access for seasonal launches.

- **Frequent Low-Spenders:** Encourage upselling and cross-selling:
   
   - Offer discounts on pastries or bread when they buy their usual drink.

   - Suggest seasonal or premium drinks with small discounts.

   - Offer free toppings or syrups to increase perceived value and build habit for higher-spend orders.
