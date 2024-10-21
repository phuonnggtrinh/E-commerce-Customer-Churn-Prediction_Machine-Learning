# E-commerce-Customer-Churn-Prediction_Machine-Learning
## I.Introduction
An e-commerce company seeks to predict churned users to offer targeted promotions to retain them. This project analyses churn behaviour, builds a Machine Learning model to predict churn, and segments churned users to offer specialized promotions. The company can implement strategies to reduce churn and enhance customer retention by identifying churn patterns and understanding different user segments.

**Link Project:**
https://colab.research.google.com/drive/1PZL4IDjiSj_miHfJt5yhZIqIpiEamY8L?usp=sharing

- **Explore Data:** First, we will load and examine the dataset provided (churn_predict.csv). Key features include:
  - User demographics (age, gender, marital status)
  - Account tenure
  - Customer service interactions (complaints, support tickets)
  - Transaction history (last purchase date, cashback received)
  - Churn label (whether the user churned or not)
Through initial data exploration, we'll check for missing values, data distributions, and any potential correlations between the features and the churn label.
## II. Analysis: 
To understand the patterns of churn, we will analyze:
- Customer tenure: Do users with shorter tenure churn more frequently?
- Complaints: Do users with complaints have a higher churn rate?
- Spending habits: Are low-spending customers more likely to churn?
- Marital status: Are single users more prone to churn than married ones?
### 1. Supervised Learning: Predicting Churn
Goal: You need to predict whether a customer will churn or not. This is a classic supervised learning problem because you have a labeled dataset, where customers are labelled as either "churned" or "not churned."
- **Data Preparation:** First, preprocess the dataset (e.g., churn_predict.csv) to handle missing values, feature scaling, and feature encoding (for categorical variables).
- **Feature Selection:** Use features such as tenure, complaint status, marital status, order category, etc. as input variables.
- **Model Selection:** Train a machine learning model using algorithms such as:
  - Logistic Regression
  - Random Forest
- **Evaluation:** Fine-tune the model using techniques like cross-validation and **hyperparameter tuning** to optimize accuracy, precision, recall, or other metrics that suit your business objectives.
### 2. Unsupervised Learning: Customer Segmentation
Goal: Once the churned customers are identified, the company wants to segment them into different groups to offer tailored promotions. This is where unsupervised learning comes into play.
- **Data Preparation:** Use the churned customers' data (filtered from your churn prediction model).
- **Clustering:** Apply clustering algorithms to group churned customers based on their characteristics (e.g., tenure, cashback amount, order category). K-Means clustering is a commonly used unsupervised learning algorithm for segmentation.
- **Insights:** The clustering will help you identify different customer personas. For example, you might find that one group has a short tenure and low cashback amount (likely first-time customers), while another group might have a long tenure but hasn't made a purchase recently (potential long-term customers who lost interest).

### **Feature Important**
  <img width="873" alt="Screenshot 2024-10-21 at 15 29 00" src="https://github.com/user-attachments/assets/4a6df5f1-e40d-47d1-b89e-d093c9bffbc8">

Based on the model's feature importance, the top three features influencing a customer's churn probability are:
- **Customer Tenure:** Customers with shorter tenures are more likely to churn, as they may not have developed loyalty or satisfaction with the service yet.
- **Customer Complaints:** As expected, customers who have filed complaints show a higher churn rate compared to those without any complaints, indicating dissatisfaction with the service.
- **Marital Status:** Single customers have a higher churn rate compared to other groups, potentially indicating different usage patterns or service expectations.

  <img width="457" alt="Screenshot 2024-10-21 at 15 30 39" src="https://github.com/user-attachments/assets/d53b5b02-9e60-4cb1-aa20-ba6259fd5a26">

### **Cluster's Profile Based On Tenure And Cashback Amount**
- **Cluster 0** (dark brown): Customers with higher tenure (above 10 years) and higher cashback amounts. This group seems highly loyal and may expect premium rewards or higher cashback offers.
- **Cluster 1** (light blue): These customers have relatively low tenure and moderate cashback amounts. They may be newer customers, potentially attracted by entry-level promotions.
- **Cluster 2** (light brown): This group falls somewhere between Cluster 0 and 1, with varied tenures but generally moderate cashback amounts. They may be regular buyers looking for occasional deals.

<img width="457" alt="Screenshot 2024-10-21 at 15 31 03" src="https://github.com/user-attachments/assets/0365939e-7bee-45be-9300-337bf791f744">

### **Distribution Of The Clusters by Marital Status**
- **Single customers** (Cluster 0) seem to stand out as outliers in terms of churn risk and may benefit from personalized offers that drive engagement or create a stronger connection with the brand.
- **Married and Divorced customers** (Clusters 1 and 2) are more evenly distributed, suggesting they may already be receiving appropriate offers. However, targeted promotions related to family or household purchases could boost loyalty.

<img width="484" alt="Screenshot 2024-10-21 at 15 32 10" src="https://github.com/user-attachments/assets/33b5d33f-317a-4736-8141-f432eb35ab90">

### **Cluster's Profile Based On Prefered Order Category**
- **Mobile** devices dominate the order category across all clusters, especially in Cluster 1 . This indicates that promotions around mobile devices and accessories could be highly effective in driving sales for this group.
- **Fashion and Grocery** categories also stand out for Clusters 1 and 2. Cross-category promotions (such as discounts on fashion items with mobile device purchases) might increase conversion rates.

<img width="455" alt="Screenshot 2024-10-21 at 15 34 02" src="https://github.com/user-attachments/assets/400e4bf4-e4db-4d40-bac5-91e5b827b7ae">

### **Cluster's Profile Based On Day Since Last Order**
- **Customers in Cluster 1** show the highest frequency of recent orders, suggesting they are the most engaged and responsive to new promotions.
- **Cluster 2** shows more variation, indicating the need for re-engagement campaigns (like limited-time discounts or loyalty bonuses) to prevent churn.

<img width="455" alt="Screenshot 2024-10-21 at 15 34 39" src="https://github.com/user-attachments/assets/383823e4-cf54-4987-844d-a90627f08a60">

## **Recommendations:**

### **1. Segment-Specific Promotions:**

- **Cluster 0 (High Loyalty, High Cashback):** Offer exclusive or premium rewards, such as higher cashback, early access to new products, or premium membership benefits.

- **Cluster 1 (New Customers):** Provide entry-level promotions, such as “Buy One, Get One Free” offers or introductory discounts to encourage repeat purchases.

- **Cluster 2 (Regular Buyers):** Focus on personalized offers based on purchase history and interest in specific categories (e.g., technology, fashion).

### **2. Promotional Timing:**

- Use the insights from the **Days Since Last Order** data to offer time-sensitive deals, particularly targeting Cluster 2 for re-engagement.
- Align promotions around high-demand times for each cluster, ensuring that Cluster 1 receives frequent updates on new products.

### **3. Personalized Messaging:**

- Utilize **marital status insights** to craft messaging tailored to specific segments. For example, single customers may respond better to individual-focused campaigns, while married customers could appreciate family-oriented promotions.

### **4. Leverage Preferred Categories:**

- Create **category-specific campaigns** targeting high-demand items such as mobiles for Cluster 1 and offer bundle deals to increase average order value.
- Cross-sell between high-potential categories like Fashion and Groceries to promote variety.
