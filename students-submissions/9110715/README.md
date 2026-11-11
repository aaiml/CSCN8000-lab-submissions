# CSCN8000 — Artificial Intelligence Algorithms and Mathematics

**Student:** Ubaid Ullah  
**Student ID:** 9110715  
**Course:** CSCN8000 — Artificial Intelligence Algorithms and Mathematics

---

## Overview

This repository folder contains my practical lab submissions for CSCN8000. Each lab explores fundamental concepts in artificial intelligence, machine learning, probability, statistics, and data analysis through Python-based implementations.

The submissions include Jupyter Notebooks with explanations, executable code, visualizations, experimental results, and conclusions. HTML versions are also provided for convenient viewing.

## Lab Submissions

### Lab 1 — Basic NumPy Operations

**Objective:** Practice fundamental numerical computing operations using NumPy.

**Topics Covered:**
- NumPy arrays and basic numerical operations
- Array manipulation and indexing
- Mathematical calculations using Python
- Practical applications of NumPy

**Submission Files:**

- [Jupyter Notebook — Lab 1](Lab1.ipynb)
- [HTML Report — Lab 1](Lab1.html)

---

### Lab 2 — Spam Classification and Airbnb Price Outlier Detection

**Objective:** Apply probability-based machine learning techniques to email classification and use statistical measures of central tendency and dispersion to identify and remove unusual Airbnb nightly prices.

#### Part A — Spam Classification Using Naive Bayes

This section compares two probabilistic classification algorithms:

- Gaussian Naive Bayes
- Multinomial Naive Bayes

**Methodology:**

1. Loaded and explored the email dataset containing 5,171 messages.
2. Identified and removed 178 duplicate email messages.
3. Split the cleaned dataset into 80% training and 20% testing data.
4. Converted email text into numerical features using CountVectorizer.
5. Trained Gaussian and Multinomial Naive Bayes classifiers.
6. Evaluated the models using accuracy, precision, recall, F1-score, and confusion matrices.
7. Performed predictions on unseen test emails.

**Model Performance:**

| Evaluation Metric | Gaussian Naive Bayes | Multinomial Naive Bayes |
|---|---:|---:|
| Accuracy | 94.79% | 94.69% |
| Precision (Spam) | 87.31% | 87.04% |
| Recall (Spam) | 96.25% | 96.25% |
| F1-Score (Spam) | 91.56% | 91.41% |

**Key Finding:**

Gaussian Naive Bayes achieved slightly better performance on the test dataset. However, both models demonstrated strong classification performance, and the difference was too small to establish the general superiority of either classifier.

#### Part B — New York City Airbnb Price Outlier Detection

This section examines nightly accommodation prices in the New York City Airbnb dataset using statistical techniques.

**Dataset:** 48,895 Airbnb listings with 16 attributes.

**Statistical Techniques:**

- Mean and standard deviation
- Interquartile Range (IQR)
- Z-score
- Median Absolute Deviation (MAD)
- Percentile-based filtering
- Room-type-specific IQR analysis

**Outlier Detection Comparison:**

| Method | Statistical Outliers Detected | Percentage of Valid Listings |
|---|---:|---:|
| Global IQR | 2,972 | 6.08% |
| Z-score | 388 | 0.79% |
| MAD | 2,916 | 5.97% |
| Percentile Filtering | 867 | 1.77% |
| Room-Type-Based IQR | 3,244 | 6.64% |

**Final Cleaning Approach:**

Room-type-based IQR was selected because entire homes, private rooms, and shared rooms have different typical price distributions.

After removing 11 zero-price listings and 3,244 statistical outliers, the final dataset contained **45,640 listings**.

**Before-and-After Comparison:**

| Measurement | Original Dataset | Cleaned Dataset |
|---|---:|---:|
| Total Listings | 48,895 | 45,640 |
| Mean Nightly Price | $152.72 | $121.81 |
| Median Nightly Price | $106.00 | $100.00 |
| Standard Deviation | $240.15 | $73.23 |
| Minimum Price | $0 | $10 |
| Maximum Price | $10,000 | $392 |

**Key Finding:**

The room-type-based IQR method provides a more context-aware approach to identifying unusual prices than applying one global price threshold across all accommodation types.

The final dataset satisfies the original room-type-specific IQR boundaries. However, statistical outliers are not necessarily data errors, and different detection methods may identify different observations.

#### Lab 2 Submission Files

- [Jupyter Notebook — Lab 2](lab2.ipynb)
- [HTML Report — Lab 2](lab2.html)
- [Cleaned Airbnb Dataset — CSV](airbnb_cleaned.csv)

---

## Technologies and Libraries

The labs use Python and Jupyter Notebook, along with relevant scientific computing and machine learning libraries.

| Technology | Purpose |
|---|---|
| Python | Programming and data analysis |
| Jupyter Notebook | Interactive analysis and documentation |
| NumPy | Numerical computing |
| Pandas | Data manipulation and statistical analysis |
| Matplotlib | Data visualization |
| Scikit-learn | Machine learning and model evaluation |
| Git and GitHub | Version control and submission management |

## Data Sources

The datasets and lab instructions are provided through the course's official GitHub repository:

[CSCN8000 Lab Submissions — Course Repository](https://github.com/aaiml/CSCN8000-lab-submissions)

## Conclusion

These practical labs demonstrate the application of Python, machine learning, and statistical analysis to real-world datasets.

Lab 1 focuses on foundational numerical computing, while Lab 2 applies probabilistic classification to email messages and statistical techniques to Airbnb pricing data.

The work emphasizes reproducible analysis, data preparation, model evaluation, visualizations, and interpretation of results.

---

**Prepared by:** Ubaid Ullah  
**Student ID:** 9110715  
**Course:** CSCN8000 — Artificial Intelligence Algorithms and Mathematics
