# Python Bootcamp for Social Scientists

A free, four-session introduction to Python for social scientists, built as a companion to my [R bootcamp](https://github.com/dr-antonetti-marta/r-bootcamp): same data, same questions, in Python. Written by [Marta Antonetti](https://github.com/dr-antonetti-marta) (2026).

Four notebooks, one running question: **did the 1983 seatbelt law reduce road deaths in Great Britain?**
The data are monthly road-casualty counts for 1969–1984 (`data/Seatbelts.csv`).

## Sessions

1. Python basics: Jupyter, importing data, subsetting, renaming, missing values
2. Descriptive statistics, hypothesis tests, linear regression
3. Visualisation, regression tables, coefficient plots (with simulated trust-experiment data)
4. Count, logistic and ordered models; your own mini-analysis; trees and random forests

Coming from R? [`R_to_Python_cheatsheet.md`](R_to_Python_cheatsheet.md) maps common R commands to their Python equivalents. Python counts from 0, ranges exclude the end point, and most things need `import` first.

## Set-up (once)

1. **Download** this repository: click the green **Code** button above → **Download ZIP**, then unzip it and keep its contents together. (If you use Git: `git clone https://github.com/dr-antonetti-marta/python-bootcamp.git`.)
2. You need Python 3.9 or newer. If you use Anaconda you already have most of what's needed. From inside the folder, install the packages:

```bash
pip install -r requirements.txt
```

3. Start JupyterLab and open `Session1.ipynb`:

```bash
jupyter lab
```

## How to work through a session

- Run cells top to bottom (**Shift + Enter**). Later cells depend on earlier ones.
- Cells starting `# your code here` are tasks. Try them before looking anything up.
- Sections tagged *(syntax demo)* teach a tool on a toy example. The rest is built around the seatbelts question.
- Keep the folder structure: the notebooks look for the data in `data/`. If the file can't be found they say so, and fall back to downloading the same data through `statsmodels`.

## About the data

`Seatbelts` is a real, historical dataset that ships with R. One dataset in Session 3 (the "trust experiment") is fully simulated for teaching, not real survey data. Original sources:

- Harvey, A.C. and Durbin, J. (1986). The effects of seat belt legislation on British road casualties: A case study in structural time series modelling. *Journal of the Royal Statistical Society, Series A*, 149, 187–227.
- Harvey, A.C. (1989). *Forecasting, Structural Time Series Models and the Kalman Filter*. Cambridge University Press.

## Solutions

This repository contains the **student versions** only: tasks come with instructions but no worked answers, so that solutions don't circulate among future cohorts. If you're an instructor or self-learner and would like the solutions, email me at [m.antonetti@lse.ac.uk](mailto:m.antonetti@lse.ac.uk).

## Licence

© 2026 Marta Antonetti. This material is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/): you're free to use, share and adapt it, including for your own teaching, as long as you credit the author.
