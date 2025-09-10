Software version: Matlab R2020 b or R2021 a.
Encoding: UTF-8.

(1) The main basic function: est_LSIR.m.
This function is used to obtain the proposed estimators. 

results_LSIR=est_LSIR(Z,X,y,Mn,Beta_initial,Eta_initial,Tau_initial,Alpha_initial,Lambda,t,deltan,cn,pen,maxiter,tol,B,ifplot)

Input：
Z: The covariates in the linear part.
X: The covariates in the index part.
y: The outcomes. 
Mn: The number of knots.
Beta_initial: The initial values for beta.
Eta_initial: The initial values for eta.
Tau_initial: The initial values for tau.
Alpha_initial: The initial values for alpha.
Lambda: Tuning parameter in the penalty.
t: A parameter that controls the concavity of the penalty function.
deltan: The tuning parameter for smoothness.
cn:  A predetermined parameter in BIC.
pen:  penalty function, i.e. 'SCAD' and 'MCP' .
MI: The maximum number of iterations.
tol:  The tolerance parameter.
B: The times of bootstrap sampling.
ifplot: Whether plotting the figures: 'true' or 'flase'.

Output: results_LSIR is a struct type, which inclues
resultTable: A table including the estimated values, standard errors (SE), confidence interval (CI) and p-value.
hatalpha: The estimated values of alpha.
hatbeta: The estimated values of beta.
hattau: The estimated values of tau
hateta: The estimated values of eta
pvalue: The p-values.
SE: The standard errors (SE).
CI: The confidence interval (CI).
R2: The coefficient of determination.
hatMn: The estimated value of Mn*.
pvalue_knot: The p-value of testing for knot effects.
BIC_lambda: The BIC values corresponding to all lambdas.
hatlambda: The lambda value that minimizes the BIC.

Another basic functions:

chooseBIC.m: This function is used to select the estimated values of LSIR model according to the BIC minimum principle.

est_ADMM.m: This function is used to calculate the estimated values of LSIR model according to ADMM algorithm.

Global_ADMM.m: This function is used to calculate the global estimated values of LSIR model according to the bootstrap adjustment method.

est_oracle.m: This function is used to calculate the oracle estimated values of LSIR model.

est_PR_global.m and est_PR.m: These functions are used to calculate the initial values using polynomial regression (PR) model.

est_SIR_wang.m and hatf_fun_wang.m:  These functions are used to calculate the estimated values of PLSIR model (see Wang et al., 2010).

est_SE.m:  This function is used to calculate the estimated values of variance of hatTheta.

EvalutionFunc.m: This is a set of functions including SCAD and MCP.

f0.m: This is a function for f(x,tau)=(x-tau)I(x>tau).

qn.m: This is an approximation function of  f(x,tau)=(x-tau)I(x>tau).

funTBZ.m: This function is used to construct the objective function for the estimation of Eta and Beta in est_ADMM.m and est_oracle.m.

ST.m: This function is the solution function corresponding to the Lasso method.

S_SCAD.m: This function is the solution function corresponding to the SCAD method.

S_MCP.m: This function is the solution function corresponding to the MCP method.

test_knots.m: This function is used to calculate the p-value of testing for knot effects.

Note:
For convenience, we used the Matlab function: array2table to output table-type results. 


