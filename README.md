# 🍎 ML Fruit Classification Project  
*A comparative study of machine learning models for fruit image recognition, analyzing the impact of color vs. shape features.*  

---

## 📌 Overview  
This project evaluates **8 machine learning models** (CNN, ANN, SVM, etc.) on the [Fruits-360 dataset](https://www.kaggle.com/datasets/moltean/fruits) to determine whether **color** or **shape** features dominate classification accuracy. Key findings:  
- **CNN achieved 100% accuracy**, outperforming all other models.  
- Grayscale images reduced accuracy by **~3-10%**, confirming color’s importance.  
- Tubular fruits (e.g., bananas) were hardest to classify (**86% avg accuracy**).  

---

## 🛠️ Tech Stack  
- **Models**: CNN, ANN, SVM, Random Forest, Logistic Regression, Naive Bayes, Decision Tree, KNN  
- **Tools**: TensorFlow/Keras, Scikit-learn, OpenCV, Matplotlib  
- **Analysis**: Grad-CAM, t-SNE, K-means clustering  
- **Advanced**: WGAN-GP for synthetic fruit generation

---

## 🔍 Key Experiments  
1. **Color vs. Shape Analysis**:  
   - Tested models on **3 color groups** (Red/Yellow/Green), **3 shape groups** (Circular/Not Quite Circular/Tubular), and Randomized Fruits.  
   - Grayscale conversions reduced accuracy, especially for red/yellow fruits.  

2. **Model Comparison**:  
   | Model            | Avg Accuracy |  
   |------------------|-------------|  
   | CNN              | 100%        |  
   | Random Forest    | 98%         |  
   | ANN              | 95%         |  
   | Naive Bayes      | 76%         |  

3. **Explainability**:  
   - Grad-CAM revealed CNNs focus on **fruit contours** (shape) and **texture/color patches**.  

---

## 📊 Results & Discussion

**1. Color vs. Shape Impact:**

  - Similar Color, Different Shapes: 92% accuracy
  - Similar Shape, Different Colors: 91% accuracy

Grayscale (color-ablated) tests: 89% accuracy (3% drop from colored versions)

**2. Model Performance:**
  - **Top Performers:**
    - CNN (100% accuracy)
    - Random Forest (98% accuracy)
    - ANN (95% accuracy)

  - **Weakest Model:** Naive Bayes (76%)

**3. Shape Complexity Gradient:**
  - Circular fruits: 95% → Tubular fruits: 86% accuracy
---

 ## Interpretation
While the small accuracy gap (92% vs. 91%) **suggests no dominant feature** (color vs. shape), secondary evidence reveals:
  - The **3% accuracy drop in grayscale tests** implies color contributes modestly to classification.
  - **Tubular fruits were hardest to classify** (-9% vs. circular), suggesting shape complexity matters more than color uniformity.

 ## Notable Observations
  - **CNN's 100% accuracy** demonstrates the power of hierarchical feature learning.
  - **Naive Bayes' poor performance** (76%) highlights its unsuitability for pixel-dependent tasks.
  - **Grayscale tests:** All models except Naive Bayes lost ~10% accuracy without color data.

---

## 🎯 Conclusion & Recommendations
**Summary**

**1. Feature Impact:**
Neither color nor shape overwhelmingly dominates classification, but:
  - Color provides a consistent ~3% accuracy boost.
  - Shape complexity (tubular vs. circular) causes wider accuracy swings (9% difference).

**2. Model Selection:**

   | Use Case             | Recommended Model |  
   |----------------------|-------------------|  
   | Highest Accuracy     | CNN               |  
   | Interpretability     | Random Forest     |  
   | Resource-constrained | ANN               |  
   
**3. Limitations:**

  - Dataset bias: Some categories overlapped in color/shape (e.g., red circular fruits).
  - Grayscale tests couldn't be replicated for shape isolation.
