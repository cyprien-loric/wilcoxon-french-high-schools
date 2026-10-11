# Wilcoxon Rank Tests — French High Schools

This is my M1 thesis project for the Master in Mathematical Engineering & Data Science at UHA (Mulhouse), supervised by Nicolas Juillet.

The thesis has two parts: first, the theory behind the Wilcoxon test (probability foundations, Lindeberg CLT, exact and asymptotic approaches), and then an application on real data from French high schools.

The two questions I study are:
- Does the size of a high school affect its value-added score?
- Did the Blanquer reform change the value added of French high schools?


## How to run

Python 3.13. Clone the repo and install the dependencies:

```bash
python -m venv .venv
.venv\Scripts\activate       # Windows
source .venv/bin/activate    # Linux / Mac

pip install -r requirements.txt
```

Then open `Wilcoxon.ipynb` in Jupyter or VS Code and run all cells in order.

The notebook is split in 6 parts:
1. Libraries and data loading
2. Descriptive statistics (2025)
3. Justification of the test (chi-square, skewness)
4. Question 1 — Mann-Whitney U test + sensitivity analysis
5. Question 2 — Wilcoxon signed-rank test (paired) + sector analysis
6. Bootstrap power curves

The seed is fixed (`np.random.seed(42)`).


## Data

The dataset comes from [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/indicateurs-de-resultat-des-lycees-denseignement-general-et-technologique/) (result indicators for general and technological high schools, 2012–2025).

32 485 rows, 88 columns. The main variables I use:
- Value added of the pass rate (all tracks)
- Value added of the honors rate (all tracks)
- Number of students (all tracks)
- Sector (public / private under contract)


## Main results

**Q1:** Small high schools have a significantly higher value added than large ones (p < 0.001, Cliff's delta = 0.26). The result holds for cutoff thresholds from the 30th to the 70th percentile.

**Q2:** The reform had no significant effect on the pass rate (p = 0.612), but it lowered the honors rate value added (p = 0.001). This mostly comes from private schools (median diff = −1.58), while public schools show no significant change. Note that the effect size here is small (r = 0.068) despite the significance, which makes sense given the large sample size (n ≈ 2270).


## Contact

Cyprien Loric — [GitHub](https://github.com/Cyprien-Loric)
