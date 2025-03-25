# 🍽️ Recipe Interaction Predictor

## 📌 Project Overview
This project was developed as part of **CSE 158 Assignment 2**, where we aimed to predict whether a user would interact with a specific recipe based on historical user-recipe interactions. Using the **Food.com dataset**, we applied **exploratory data analysis (EDA), feature engineering, and predictive modeling** to improve our baseline accuracy.

Our best-performing model achieved **79% accuracy**, leveraging **popularity heuristics and similarity functions (Jaccard & Cosine)** to refine predictions.

---

## 📊 Dataset Description
We utilized the **Food.com dataset**, originally collected by Shuyang Li and Bodhisattwa Prasad Majumder on Kaggle. The dataset consists of various CSV files containing **recipe metadata and user interactions**. For our analysis, we primarily focused on:

- **RAW_recipes.csv** – Contains 83,782 recipes with attributes like preparation time, ingredients, steps, and nutrition facts.
- **RAW_interactions.csv** – Includes 731,927 user interactions with recipes (ratings and reviews).
- **interactions_train.csv** – Processed training data for model development.

### 📌 Key Features Extracted:
1. **Recipe Features**: Popularity (number of reviews), average rating.
2. **User Features**: Interaction history, number of ratings given.
3. **Interaction-Based Features**: Jaccard and Cosine similarity between recipes.

---

## 🛠️ Exploratory Data Analysis (EDA)
We conducted an extensive **exploratory data analysis**, identifying trends in:
- Recipe preparation times, ingredient counts, and step distributions.
- Interaction patterns over time (peak activity in 2008).
- Rating biases, where users tend to give extreme ratings (1 or 5 stars).

To clean the data, we **removed outliers** using the **Interquartile Range (IQR) method** and transformed feature distributions to improve model stability.

---

## 🔍 Predictive Task
The objective was to **classify whether a user would interact with a given recipe**. We structured the problem as a **binary classification task**, where:
- **Positive Class**: User interacted with the recipe (rated it).
- **Negative Class**: User did not interact with the recipe.

### 📏 Model Evaluation:
We measured model performance using **accuracy**, splitting the dataset into:
- **Training Set:** 98% of the data.
- **Validation Set:** 2% (balanced positive and negative samples).

---

## 📈 Model Development & Optimization
We explored multiple predictive techniques:

### ✅ **Baseline Model: Popularity Heuristic**
- A simple approach where we **ranked recipes by popularity** (number of interactions).
- If a recipe was in the **top 50% of popular recipes**, we predicted a user would interact with it.
- **Achieved ~70% accuracy.**

### ⚡ **Optimized Model: Similarity-Based Approach**
To improve accuracy, we introduced **Jaccard & Cosine similarity metrics**:
1. **Jaccard Similarity**: Measures shared interactions between users and recipes.
2. **Cosine Similarity**: Captures similarity in user-recipe interaction vectors.

After fine-tuning similarity thresholds and weighting factors, our model accuracy **increased to 79%**.

---

## 🔬 Challenges & Unsuccessful Attempts
1. **Similarity-Based Predictions Led to High False Positives**  
   - Sparse user interactions made similarity-based metrics unreliable.
   - Many recipes had <20 reviews, leading to weak similarity signals.

2. **TF-IDF Ingredient-Based Model Considered, But Not Used**  
   - While promising for **recipe recommendations**, this approach lacked a clear evaluation metric for our **binary classification task**.

---

## 📚 Literature Review & Similar Datasets
We reviewed related works such as:
- **Majumder et al. (2019)**: Explored **personalized recipe generation** using deep learning.
- **Recipe1M+ Dataset**: Used for **image-to-recipe retrieval**, but not ideal for our task.

For more details, refer to the **Works Cited** section in our [full write-up](./Assignment_2_Write_Up.pdf).

---

## 🎥 Project Video Explanation
🔗 **[Watch our project explanation video here!](YOUR_VIDEO_LINK_HERE)**

---

## 📌 Conclusion
Our final model successfully predicted **user-recipe interactions with 79% accuracy**, showing that:
- **Popularity is a strong predictor** of interaction likelihood.
- **Jaccard & Cosine similarity help refine predictions**, but their effectiveness depends on dataset sparsity.

### 🚀 Future Improvements:
- Incorporate **latent user preferences** (e.g., favorite ingredients, cuisine styles).
- Experiment with **deep learning-based collaborative filtering** for better personalization.
- Apply **TF-IDF on recipe descriptions** to test content-based approaches.

---

## 📜 Acknowledgments
This project was completed for **CSE 158 (Fall 2024)**. Special thanks to **Professor McAuley** for guidance and resources.

📢 **Developed by:** Julian & Team  
📅 **Submission Date:** December 3, 2024  
📄 **Full Report:** [Assignment_2_Write_Up.pdf](./Assignment_2_Write_Up.pdf)
