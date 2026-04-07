#  Statistical Engine & Monte Carlo Simulation

##  Objective

This project implements a **Statistical Analysis Engine** and a **Monte Carlo Simulation system** to:

- Compute **descriptive statistics** (mean, median, mode)
- Measure **data dispersion** (variance, standard deviation)
- Detect **outliers**
- Simulate **probabilistic events** (e.g., system crashes)

The focus is not just computation, but:
- Ensuring **data integrity**
- Applying **correct mathematical principles**
- Demonstrating **real-world statistical modeling**

---

##  Project Structure
statistical_engine/
│
├── data/
│   └── sample_salaries.json       
├── src/
│   ├── __init__.py
│   ├── stat_engine.py            
│   └── monte_carlo.py           
├── tests/
│   ├── __init__.py
│   └── test_stat_engine.py        
├── README.md
└── main.py         

---

## ⚙️ How It Works

### 1. Statistical Engine (`StatEngine`)
- Accepts raw input data (list or tuple)
- Cleans and validates data
- Computes statistical metrics

### 2. Monte Carlo Simulation (`simulate_crashes`)
- Simulates random events over time
- Estimates probability using repeated trials

### 3. Testing (`unittest`)
- Ensures correctness of statistical methods
- Validates edge cases and error handling

---

##  Data Cleaning

Before computation, input data is validated:

### Rules:
- `int`, `float` → accepted
- `str` → converted to float (if possible)
- `None` → rejected
- Other types → rejected

### Why this matters:
Invalid data leads to incorrect statistical results.

---

##  Mathematical Formulas

### 🔹 Mean (Average)

\[
\mu = \frac{\sum_{i=1}^{n} x_i}{n}
\]

---

###  Median

- Sort data
- If odd:
  - Middle value
- If even:
  - Average of two middle values

---

###  Mode

- Most frequently occurring value(s)
- If all values are unique → no mode

---

###  Variance

**Population Variance:**
\[
\sigma^2 = \frac{\sum (x_i - \mu)^2}{n}
\]

**Sample Variance (used in this project):**
\[
s^2 = \frac{\sum (x_i - \mu)^2}{n - 1}
\]

---

###  Standard Deviation

\[
\sigma = \sqrt{\sigma^2}
\]

---

###  Outlier Detection

\[
|x - \mu| > k \cdot \sigma
\]

- Default: \( k = 2 \)
- Values beyond this range are considered outliers

 Note: Assumes approximately normal distribution.

---

##  Monte Carlo Simulation

### Concept

Estimate probability using repeated random sampling.

### Formula

\[
P \approx \frac{\text{Number of Crashes}}{\text{Total Days}}
\]

### Process

- For each simulated day:
  - Generate a random number between 0 and 1
  - If less than crash probability → count as crash

### Insight

- Larger number of simulations → more accurate results

---

##  Usage

### Run Main Script

```bash
 main.ipynp
