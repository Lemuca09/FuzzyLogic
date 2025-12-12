# 🔮 Fuzzy Customer Satisfaction System

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![scikit-fuzzy](https://img.shields.io/badge/scikit--fuzzy-4B8BBE?style=flat)](https://pythonhosted.org/scikit-fuzzy/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat&logo=plotly&logoColor=white)](https://plotly.com/)

---

## 🔍 Overview

This project implements a **Fuzzy Inference System (FIS)** to estimate **customer satisfaction** based on three business-critical variables: **delivery time**, **price**, and **quality**.  
The system models subjective human reasoning using fuzzy sets and linguistic rules, producing a numerical satisfaction score and an interpretable qualitative label.

---

## ⚙️ Features

* Fuzzy modeling of subjective customer satisfaction
* Trapezoidal and triangular membership functions
* Rule-based inference using linguistic variables
* Centroid-based defuzzification
* Synthetic dataset generation (200 samples)
* Interactive user input for real-time evaluation
* 2D and 3D visualizations for interpretability
* Explainable decision logic (no black-box modeling)

---

## 📦 Requirements

* Python 3.8+
* numpy
* pandas
* scikit-fuzzy
* matplotlib
* plotly

---

## ⚙️ Installation

1. Clone the repository:

```bash
git clone <GIT-REPO-HTTPS>
cd repo-name
```

3. Install dependencies:

```bash
pip install numpy pandas scikit-fuzzy matplotlib plotly
```

4. Run the script or notebook:

```bash
python fuzzyprecos.py
# or
jupyter notebook FuzzyPrecos.ipynb
```

---

## 🚀 Usage

1. **Define input values**
   The system will prompt for:

   * Delivery time (0–72 hours)
   * Price (1–100)
   * Quality (0–10)

2. **Run inference**
   The fuzzy system will:

   * Fuzzify inputs
   * Apply fuzzy rules
   * Aggregate rule outputs
   * Defuzzify using the centroid method

3. **View results**

   * Numerical satisfaction score (0–10)
   * Qualitative label:

     * Excellent
     * Good
     * Poor
     * Very Poor
   * Visual plots for interpretability

---

## 📁 Project Structure

```
FuzzyPrecos.ipynb      # Main notebook with full explanation and execution
fuzzyprecos.py        # Script version of the fuzzy system
```

---

## ⚙️ System Design

### **Input Variables**

| Variable      | Range  | Linguistic Terms         |
| ------------- | ------ | ------------------------ |
| Delivery Time | 1–72 h | Fast, Moderate, Slow     |
| Price         | 1–100  | Low, Medium, High        |
| Quality       | 0–10   | Poor, Average, Excellent |

### **Output Variable**

| Variable     | Range | Linguistic Terms  |
| ------------ | ----- | ----------------- |
| Satisfaction | 0–10  | Low, Medium, High |

---

## 📜 Rule Base

1. IF quality is **excellent** AND price is **low** → satisfaction is **high**
2. IF quality is **poor** OR price is **high** → satisfaction is **low**
3. IF delivery time is **slow** AND quality is **average** → satisfaction is **medium**
4. IF delivery time is **fast** AND quality is **excellent** → satisfaction is **high**
5. IF delivery time is **slow** AND price is **high** → satisfaction is **low**
6. IF delivery time is **moderate** AND price is **medium** AND quality is **average** → satisfaction is **medium**

---

## 🔬 Dataset Simulation

A synthetic dataset of **200 samples** is generated using uniform distributions:

* Delivery Time → ( U(1, 72) )
* Price → ( U(1, 100) )
* Quality → ( U(0, 10) )

Each sample represents a realistic customer scenario evaluated by the fuzzy system.

---

## 📊 Visualization

* 2D scatter: **Quality × Satisfaction** (colored by Price)
* 2D scatter: **Delivery Time × Satisfaction** (colored by Price)
* 3D scatter: **Quality × Delivery Time × Satisfaction**

These plots help reveal relationships such as:

* Higher prices tend to reduce satisfaction
* Slow delivery negatively impacts satisfaction depending on quality

---

## 🧠 Defuzzification Method

The system uses the **Centroid (Center of Area)** method:

[
S = \frac{\int x \cdot \mu(x),dx}{\int \mu(x),dx}
]

This ensures a stable and interpretable crisp output from the aggregated fuzzy set.

---

## 🚀 Applications

* Customer experience modeling
* Pricing and logistics optimization
* Decision support systems
* Explainable AI (XAI)
* Academic studies on fuzzy logic

---

## 📚 References

* [scikit-fuzzy Documentation](https://pythonhosted.org/scikit-fuzzy/)
* [Fuzzy Logic – Zadeh (1965)](https://ieeexplore.ieee.org/document/4036239)
* [Centroid Defuzzification](https://en.wikipedia.org/wiki/Fuzzy_logic)

---
