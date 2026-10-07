# R → Python cheat sheet (as used in this bootcamp)

| Task | R | Python |
|---|---|---|
| Load packages | `library(ggplot2)` | `import seaborn as sns` |
| Read CSV | `read.csv("x.csv")` | `pd.read_csv("x.csv")` |
| Structure of data | `str(df)` | `df.info()` |
| Summary | `summary(df)` | `df.describe()` |
| Pick a column | `df$kms` | `df["kms"]` |
| Filter rows | `subset(df, law == 1)` | `df[df["law"] == 1]` or `df.query("law == 1")` |
| Rename a column | `names(df)[2] <- "x"` | `df.rename(columns={"old": "x"})` |
| New column | `df$z <- df$x / df$y` | `df["z"] = df["x"] / df["y"]` |
| Group means | `aggregate(y ~ g, df, mean)` | `df.groupby("g")["y"].mean()` |
| Frequency table | `table(df$g)` | `df["g"].value_counts()` |
| Cross-tab | `table(df$a, df$b)` | `pd.crosstab(df["a"], df["b"])` |
| Mean ignoring NA | `mean(x, na.rm = TRUE)` | `x.mean()` (pandas skips NA by default; `np.mean` does not) |
| Variance | `var(x)` (n − 1) | `x.var()` (n − 1) but `np.var(x)` is n, use `ddof=1` |
| Welch t-test | `t.test(y ~ g, data = df)` | `scipy.stats.ttest_ind(a, b, equal_var=False)` |
| Linear model | `lm(y ~ x + factor(m), df)` | `smf.ols("y ~ x + C(m)", df).fit()` |
| Model summary | `summary(m)` | `m.summary()` |
| Poisson / logit | `glm(..., family = poisson)` | `smf.glm(..., family=sm.families.Poisson())`, `smf.logit(...)` |
| Ordered logit | `MASS::polr` / `ordinal::clm` | `OrderedModel.from_formula(...)` |
| Regression table | `stargazer(m1, m2)` | `summary_col([m1, m2], stars=True)` |
| Random numbers | `set.seed(1); rnorm(5)` | `rng = np.random.default_rng(1); rng.normal(size=5)` |
| Decision tree | `rpart(y ~ x, df)` | `DecisionTreeClassifier(max_depth=3).fit(X, y)` |
| Random forest | `randomForest(...)` | `RandomForestClassifier(...)` |

## Differences that trip people up

- **Indexing starts at 0** and ranges exclude the end: `x[0:3]` is the first three items.
- **Copies.** After subsetting, use `.copy()` before adding columns, or you may get a `SettingWithCopyWarning`.
- **Random numbers differ.** The same seed gives different numbers in R and Python, so simulated results (Session 3) match in *pattern*, not digit for digit.
- **Trees need limits.** `rpart` stops growing by itself; scikit-learn grows until leaves are pure, so set `max_depth` / `min_samples_leaf`.
- **No `attach()`.** Always refer to the data frame explicitly.
