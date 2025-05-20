# Markov Chains and Couples

A discrete‐time Markov chain model projecting the evolution of France’s relationship status and family size over a 10-year horizon. States are defined by

```
(AgeBin, Status, NumberOfChildren)
```

plus an absorbing `Dead` state. The model uses INSEE data for the initial distribution, parametric rates for aging, union transitions, fertility (from INED), and mortality (from French life tables), then computes

```
π₀, P ⇒ π₁…π₁₀
```

and produces charts and CSV tables of marginals over time. 

We had a hard time focusing on US data also, we are currently rebuilding it because we add a problem at the end of the computation. Data on friendship would have been much only assumptions because we didn't foudn data that could helps find real link between status, except for very small unreliable studies

---

## Prerequisites

* Python 3.8+
* git
* Internet access (to download INSEE/INED data)

---

## Installation

```bash
# 1. Clone the repository
git clone  https://github.com/FallenElias/Markov-Chains-and-Couples.git
cd markov-couples

# 2. Install dependencies
pip install -r requirements.txt
```

---

## Data Preparation

1. **Download INSEE household data (2021)**
   [https://www.insee.fr/fr/statistiques/fichier/8205182/base-cc-coupl-fam-men-2021\_csv.zip](https://www.insee.fr/fr/statistiques/fichier/8205182/base-cc-coupl-fam-men-2021_csv.zip)

2. **Unzip in place**

Unzip the Insee data in the folder and rename base-cc-coupl-fam-men-2021.CSV to insee_household_2021.csv

   The resulting CSV(s) will be used by the preprocessing script.

---

## Repository Layout

```
.
├── pop_age_sex_matrimonial_2020.xlsx  # CSV age and pop number
├── Insee_household_2021.csv           # Household data
├── Markov chain.ipynb                 # Notebook
├── requirements.txt                   # pandas, numpy, matplotlib, xlrd,...
└── README.md                          # This file
```

---

## Customization


* **Age progression** (`age_prog`) dict
* **Union transitions** (`status_rates`) dict
* **Fertility rates** (`fertility` dict, sourced from INED)
* **Mortality rates** (`mortality` dict, from life tables)

---

## Data Sources

* **INSEE**
  Household composition by age, status, children (2021)
  [https://www.insee.fr/fr/statistiques/fichier/8205182/base-cc-coupl-fam-men-2021\_csv.zip](https://www.insee.fr/fr/statistiques/fichier/8205182/base-cc-coupl-fam-men-2021_csv.zip)

* **INED**
  Fertility by age group (2021)
  [https://www.ined.fr/en/everything\_about\_population/data/france/births-fertility/changes-fertility/#r167](https://www.ined.fr/en/everything_about_population/data/france/births-fertility/changes-fertility/#r167)

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
