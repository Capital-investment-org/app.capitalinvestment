# app.capitalinvestmentECOS is a numerical software for solving convex second-order cone programs (SOCPs) of type

min  c'*x
s.t. A*x = b
     G*x <=_K h
where the last inequality is generalized, i.e. h - G*x belongs to the cone K. ECOS supports the positive orthant R_+, second-order cones Q_n defined as

Q_n = { (t,x) | t >= || x ||_2 } 
with t a scalar and x in R_{n-1}, and the exponential cone K_e defined as

K_e = closure{(x,y,z) | exp(x/z) <= y/z, z>0}
where (x,y,z) is in R_3. The cone K is therefore a direct product of the positive orthant, second-order, and exponential cones:

K = R_+ x Q_n1 x ... x Q_nN x K_e x ... x K_e
Mixed-Integer SOCPs (ECOS_BB)
Through a recent extension by Han Wang, ECOS now comes with a branch-and-bound procedure (a direct translation of Stephen Boyd's lecture slides) called ECOS_BB for solving mixed-integer or mixed-boolean programs of the form

min  c'*x
s.t. A*x = b
     G*x <=_K h
     some x_i in {0,1}
     some x_j integer
Note: the branch-and-bound module has been designed to solve small problems at acceptable speeds and with minimum added code complexity (ca. 200 lines of code on top of ECOS).

Interfaces
ECOS has numerous interfaces, each hosted in a separate git repository. The core ECOS solver (this repository) is included in the interface repositories as a submodule. You should run git submodule init and git submodule update after cloning the interface repositories.

MATLAB interface
Python interface
Julia interface
R interface. Also on CRAN.
Please refer to the corresponding repositories or the wiki for information on how to install and use ECOS through these interfaces.
