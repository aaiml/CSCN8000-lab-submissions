# Lab 2 – Spam Classification with Naive Bayes & Airbnb NYC Price Outliers

**Name:** Juan Antonio Sainz Gálvez
**Student ID:** 9072844
**Course:** CSCN8000 – AI Algorithms Math (AAIML), Conestoga College

## Files

| File | What it is |
|---|---|
| `lab2.ipynb` | Notebook with Part A and Part B, already executed |
| `lab2.html` | HTML export of the notebook (published with GitHub Pages) |
| `requirements_lab2.txt` | Python packages needed to run the notebook |
| `AB_NYC_2019_clean_lab2.csv` | Clean Airbnb dataset produced in Part B |

The notebook reads the datasets from the course repository folder `practical_labs/` (`Lab2_dataset.csv` and `AB_NYC_2019.csv`) using the relative path `../../practical_labs/`.

## Part A – Spam vs not spam (Naive Bayes)

- 5,171 emails (71% ham, 29% spam); 178 duplicated emails removed before splitting.
- 80/20 stratified train/test split; emails converted to word counts with `CountVectorizer` (English stop words removed, full vocabulary).
- Two models trained and compared: **GaussianNB** and **MultinomialNB**.

| Model (full vocabulary) | Test accuracy | Spam precision | Spam recall | Spam F1 |
|---|---|---|---|---|
| GaussianNB | 0.953 | 0.949 | 0.887 | 0.917 |
| MultinomialNB | **0.971** | 0.946 | **0.956** | **0.951** |

**MultinomialNB performs better.** It catches far more spam (13 spam emails missed vs 33 for GaussianNB) with almost the same precision, and 5-fold cross-validation confirms it (average accuracy 0.980 vs 0.965 for GaussianNB's best set-up). Word counts are discrete, non-negative and mostly zero, which matches the multinomial distribution, not the bell curve GaussianNB assumes. The notebook also shows that with a small vocabulary GaussianNB can come close, and uses the trained MultinomialNB model to predict test emails and new example emails.

## Part B – Airbnb NYC price outliers

- 48,895 listings; price per night is extremely right-skewed (mean $153, median $106, max $10,000, 11 listings at $0).
- Techniques compared: Z-score (mean ± 3 SD), IQR (1.5 × IQR), percentiles (1st–99th), median ± 3 MAD, and IQR per room type.
- Mean-based rules fail on skewed data because the outliers inflate the mean and standard deviation; median/quartile-based rules are robust.

**Final clean dataset:** $0 prices removed, then IQR fences calculated **separately for each room type** (entire home, private room, shared room), because each type has its own normal price range. Result: 45,640 listings kept (6.66% removed); the gap between mean and median drops from about $47 to about $22.

## How to run

1. Create the virtual environment in this folder and install the packages:
   `python -m venv .venv` then `.venv\Scripts\pip install -r requirements_lab2.txt`
2. Open `lab2.ipynb` in VS Code, select the `.venv` kernel and run all cells.
3. Export the HTML: `.venv\Scripts\jupyter nbconvert --to html lab2.ipynb`
