# supply-chain-ml-project
"A machine learning classification model to predict delivery delays in company's sustainable supply chain."

# Phase 3 Project

##  Overview

This project aims to support a logistics company in predicting whether a shipment will arrive **on time** or be **delayed**. On-time delivery is critical for customer satisfaction, operational efficiency, and cost control. By building a classification model using machine learning techniques, this project provides a data-driven solution to anticipate delays before they occur.

---

## Business and Data Understanding

### Stakeholder
The primary stakeholder is a **logistics operations team** within a supply chain company. Their goal is to proactively manage logistics by identifying factors that contribute to delivery delays and to deploy predictive tools that reduce late shipments.

### Dataset
The dataset used (`Train (2).csv`) includes 11 features related to product delivery, such as:
- **Cost_of_the_Product**
- **Weight_in_gms**
- **Discount_offered**
- **Mode_of_Shipment**
- **Warehouse_block**, among others

The target variable is `Reached.on.Time_Y.N`, a binary indicator where:
- `1` means the product was delivered on time
- `0` means it was delayed

Exploratory analysis confirmed the target distribution is relatively balanced, making it suitable for classification without rebalancing.
# Visual Exploration
![Target Variable Distribution](img.1.png)
![Correlation Heatmap](Images\img.2.png)
---

## Modeling

We implemented and compared several classification models:
1. **Logistic Regression** – Used as the baseline model.
2. **Tuned Logistic Regression** – Hyperparameter tuning via GridSearchCV.
3. **Decision Tree Classifier** – Captures non-linear relationships.
4. **Random Forest Classifier** – An ensemble approach combining multiple decision trees.

![ROC Curve Comparison](img.3.png)

**Preprocessing** included:
- Standard scaling for numerical variables.
- One-hot encoding for categorical variables.
- Pipeline integration for cleaner and modular model management.

---

## Evaluation

Each model was evaluated using:
- **Classification Report** (Precision, Recall, F1-score)
- **ROC AUC Score**
- **ROC Curve Visualization**

### Key Results:
- **Decision Tree** performed best with a ROC AUC of **0.74**.
- **Random Forest** followed closely and offered a balanced performance across metrics.
- Logistic models underperformed slightly in comparison but remained interpretable.

The most influential features were:
- `Discount_offered`
- `Weight_in_gms`
- `Cost_of_the_Product`

![Top 10 Feature Importances](Images\img.4.png)

---

## Conclusion

### Key Findings
1. **Decision Tree** achieved the best predictive performance.
2. The target classes were balanced, minimizing the risk of model bias.
3. **Discount Offered** was the most critical feature in predicting delays.
4. Logistic models provided interpretability but lacked predictive strength compared to tree-based models.

### Recommendations
1. **Deploy the Decision Tree model** to flag potential delays in real-time dashboards.
2. **Re-evaluate discount strategies**, as high discounts correlated with more delays.
3. Monitor high-weight shipments proactively using the trained model.
4. Use feature importance insights to guide internal reviews on delay causes, especially focusing on shipping modes and logistics costs.

---

This project bridges the gap between business objectives and data science methods, delivering a predictive tool with practical implications for delivery performance optimization.

