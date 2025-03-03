# Global-Suicide-Rates-Analsyis

Welcome to the **Global Suicide Rates Analysis** project. This project leverages **data mining and machine learning techniques** to analyze and predict global suicide trends across different **countries, years, age groups, and economic conditions**.

---

## **1. Introduction**
### **Purpose**
This project aims to analyze **global suicide rates from 1985 to 2016** using **exploratory data analysis (EDA)** and **machine learning models**. By understanding the correlation between **demographic, economic, and social factors**, this study can support **mental health policies and intervention strategies**.

### **Tech Stack**
- **Programming & Libraries:** Python, NumPy, Pandas, Scikit-learn, Matplotlib, Seaborn
- **Machine Learning Models:** K-Nearest Neighbors (KNN), Decision Tree, Random Forest, Logistic Regression, Naïve Bayes
- **Data Source:** [Kaggle - Suicide Rates Overview 1985-2016](https://www.kaggle.com/russellyates88/suicide-rates-overview-1985-2016)

---

## **2. Dataset Overview**
The dataset consists of **27,820 rows and 12 columns**, providing suicide statistics for **101 countries** from **1985 to 2016**.

### **📊 Dataset Columns**
| Column | Description |
|---------|------------|
| **country** | Name of the country |
| **year** | Year of record (1985 - 2016) |
| **sex** | Gender of the individual (Male/Female) |
| **age** | Age group (e.g., 15-24, 35-54, 75+) |
| **suicides_no** | Number of reported suicides |
| **population** | Population size for that country-year-age group |
| **suicides/100k pop** | Suicide rate per 100,000 people |
| **country-year** | Unique identifier for each country-year entry |
| **HDI for year** | Human Development Index (HDI) for that year (some missing values) |
| **gdp_for_year ($)** | Total GDP for the country (in USD) |
| **gdp_per_capita ($)** | GDP per person (economic indicator) |
| **generation** | Generation classification (Silent, Boomer, Gen X, Millennials, etc.) |

---

## **3. Data Preprocessing**
Before applying machine learning models, extensive **preprocessing** was performed:
- **Handling Missing Values:** `HDI for year` contained missing values, which were filled using **backward fill (bfill)**.
- **Outlier Detection & Removal:** Used **Interquartile Range (IQR)** to remove extreme outliers.
- **Data Cleaning:** Converted `gdp_for_year ($)` to an **integer** format by removing commas.
- **Categorical Feature Encoding:** Converted string features (`country`, `sex`, `age`, `generation`) into numerical values.
- **Feature Scaling:** Used **Min-Max Normalization** to scale numeric features.

---

## **4. Exploratory Data Analysis (EDA)**
We conducted **in-depth analysis** of the dataset to uncover **suicide patterns**:

1️⃣ **Gender-based Trends:**  
   - **Male suicide rates** are consistently **higher** than female rates.  
   - Suicide rates vary across **different generations**.  

2️⃣ **Age-based Trends:**  
   - **Elderly individuals** (75+ years) have **higher suicide rates**.  
   - **Young adults (15-24 years)** show concerning trends in certain regions.  

3️⃣ **Economic & Social Factors:**  
   - Countries with **higher GDP per capita** generally have **lower suicide rates**.  
   - **HDI (Human Development Index)** correlates with suicide trends.  
   - Developed countries show **higher suicide rates**, possibly due to **mental health pressures, work stress, and psychiatric illness prevalence**.  

4️⃣ **Time-based Trends:**  
   - Suicide rates **fluctuate** over the years.  
   - Economic **recessions (e.g., 2008 financial crisis)** impact suicide trends.  
   - Countries like **Japan, Russia, and South Korea** have **higher suicide rates** than others.

EDA Visualisations:

![dwdm 1](https://github.com/user-attachments/assets/0c1f02ed-855a-4cfe-a78c-0b92ce7ca47a)

![dwdm 2](https://github.com/user-attachments/assets/ad058fcf-65fd-409a-ac21-2b3d153a9d89)

![dwdm 3](https://github.com/user-attachments/assets/7df7b1c1-63e8-4011-b19a-65741b22764c)

---

## **5. Machine Learning Models**
We implemented multiple **supervised learning models** to predict **suicide rates** based on demographic and economic indicators. The models used include:

- **K-Nearest Neighbors (KNN)** ✅ *(Best performing model)*
- **Decision Tree**
- **Random Forest**
- **Logistic Regression**
- **Naïve Bayes**
- **Linear Regression** *(Not ideal for this dataset)*
- **Multiple Linear Regression** *(High error rates due to data complexity)*

### 🔍 **Key Findings**
- **KNN performed the best**, effectively predicting suicide rates with the lowest error.
- **Economic and demographic factors** (GDP per capita, HDI, age group) significantly impact suicide trends.
- **Linear Regression models did not perform well** due to the **non-linear relationships** in the dataset.

---

## **6. Key Results & Model Performance**
### ✅ **Major Findings**
✔ **Economic indicators (GDP per capita, HDI) significantly impact suicide rates**  
✔ **Males are at a higher risk of suicide than females globally**  
✔ **Older age groups (55+ years) show the highest suicide rates across multiple regions**  
✔ **Economic downturns (e.g., the 2008 financial crisis) correlate with increased suicide rates**  

### 📊 **Model Performance & Evaluation**
We tested multiple **machine learning models** for **suicide rate prediction**, and the **best-performing model was K-Nearest Neighbors (KNN)** due to its adaptability to non-linear relationships in the dataset.

#### **📌 Models Used**
- **K-Nearest Neighbors (KNN)** ✅ *(Best performing model)*
- **Decision Tree**
- **Random Forest**
- **Logistic Regression**
- **Naïve Bayes**
- **Linear Regression** *(Not ideal for this dataset)*
- **Multiple Linear Regression** *(High error rates due to data complexity)*

#### **📌 Model Comparison**
| **Model** | **Best Use Case** | **Limitations** |
|-----------|----------------|----------------|
| **K-Nearest Neighbors (KNN)** ✅ | Best accuracy, works well with non-linear relationships | Sensitive to feature scaling |
| **Decision Tree** | Easy to interpret, good for feature importance | Can overfit without pruning |
| **Random Forest** | Handles large datasets well, reduces overfitting | Computationally expensive |
| **Logistic Regression** | Works for binary classification | Struggles with complex relationships |
| **Naïve Bayes** | Fast and efficient for simple patterns | Assumes feature independence |
| **Linear Regression** | Good for linear relationships | Fails due to non-linearity in data |
| **Multiple Linear Regression** | Accounts for multiple predictors | High error due to dataset complexity |

### 📌 **Feature Importance (Derived from Decision Tree & Random Forest)**
The top predictors of suicide trends were:
1. **GDP per capita ($)** → Strong negative correlation with suicide rates.
2. **Human Development Index (HDI)** → Lower HDI countries had higher suicide rates.
3. **Age Group** → Older individuals had significantly higher suicide rates.
4. **Sex (Male/Female)** → Male suicides were disproportionately higher than female.
5. **Economic downturns** → Financial crises led to an increase in suicides across regions.

---

## **7. Future Enhancements**
1. **Feature Expansion**  
   - Integrate **mental health-related data** such as depression prevalence, access to therapy, and government intervention programs.
   - Incorporate **unemployment rates** and **education levels** for deeper economic analysis.

2. **Model Improvement**  
   - Experimenting with other **advanced machine learning** techniques and **hyperparameter tuning**.
     
3. **Deployment**  
   - Developing a **web application** for real-time prediction.

---

## **8. Conclusion**
This project applies **machine learning and data science** to analyze and predict **global suicide trends**. The **KNN model achieved the highest accuracy**, making it the most effective for suicide rate prediction. 

- The study found **strong correlations** between **economic factors, age groups, and suicide rates**.
- Future enhancements include **mental health data integration, deep learning models, and real-time dashboards** for better analysis.

These insights can **aid policymakers, healthcare organizations, and mental health professionals** in developing targeted **suicide prevention strategies** based on **data-driven decision-making**.
