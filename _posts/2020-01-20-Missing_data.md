Outline of this article
-----------------------

-   Missing Data Mechanisms
-   Simple missing data fixes: LVCF, mean imputation, dummy variable
    methods
-   More complicated missing data fixes: Weighting, hotdecking,
    regression imputation
-   Building blocks and overview of multiple imputation, including
    regresion imputation with noise
-   More advanced imputation and other missing data methods

Examining Patterns of Missing Data
----------------------------------

### Cases:

-   Univariate Nonresponse: ![Univariate
    Nonresponse](/Users/YaoJunyan/Documents/pic/a.jpeg)
-   Multivariate Two Patterns: ![Multovariate Two
    Patterns](/Users/YaoJunyan/Documents/pic/b.png)
-   Monotone: ![Monotone](/Users/YaoJunyan/Documents/pic/c.png)
-   General: ![General](/Users/YaoJunyan/Documents/pic/d.png)

\*\* Notation and explanation Let R be the matrix of variables
*R*<sub>1</sub>, *R*<sub>2</sub>,...,*R*<sub>*p*</sub>, corresponding to
variables in dataset, *Y*<sub>1</sub>, *Y*<sub>2</sub>,
...,*Y*<sub>*p*</sub>, that indicate whether a given value of the
corresponding Y variable is observed(=1) or missing(=0)

Missing Data Mechanisms:
------------------------

-   Missing Completely at Random (MCAR)
    -   *P*(*R*<sub>1</sub>, *R*<sub>2</sub>, ..., *R*<sub>*p*</sub>|*Y*<sub>1</sub>, *Y*<sub>2</sub>, ..., *Y*<sub>*p*</sub>)=*P*(*R*<sub>1</sub>, *R*<sub>2</sub>, ..., *R*<sub>*p*</sub>)
-   Missing at Random (MAR)
    -   *P*(*R*<sub>1</sub>, ..., *R*<sub>*p*</sub>|*Y*<sub>1</sub>, ..., *Y*<sub>*p*</sub>)=*P*(*R*<sub>1</sub>, ..., *R*<sub>*p*</sub>|*Y*<sub>1</sub><sup>*o**b**s*</sup>, ..., *Y*<sub>*p*</sub><sup>*o**b**s*</sup>)
        Missingness depends on observed values of the variables
-   Not Missing at Random(NMAR), also called Missing Not at Random
    -   $$P(R\_{1},...,R\_{p}| Y\_{1},...,Y\_{p}) \\neq P(R\_{1},...,R\_{p}| Y^{obs}\_{1},...,Y^{obs}\_{p})$
        Missingness depends on the values of the items that are missing!

MCAR and MAR are both ignorable missing data mechanisms. The term
ignorable reflects that fact that for these missing data mechanisms we
can make inferences using our data without having to include a model for
the missing data mechanism within our analysis model. NMAR is a
non-ignorable missing data mechanism,
