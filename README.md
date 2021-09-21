# Linear-Programming
from scipy.optimize import linprog

obj = [-112000, -76000, -85000, -105000, -146000]

lhs_ineq = [[ 1,  1,  1,  1,  1],
            [-1, -1, -1, -1, -1],
            [ 1,  1, 0.7, 0,  1.25],
            [ 0.25, 0.25, 0.15, 0.1, 0.15],
            [ 7,  5,  4,  0,  0],
            [ 0,  0,  0,  0,  1],
            [ 1,  1,  1,  1,  1],
            [ 4,  3.5,  3,  3,  3.25],
            [ 1,  0,  0,  0,  0],
            [-1,  0,  0,  0,  0],
            [ 0,  1,  0,  0,  0],
            [ 0, -1,  0,  0,  0],
            [ 0,  0,  1,  0,  0],
            [ 0,  0, -1,  0,  0],
            [ 0,  0,  0,  1,  0],
            [ 0,  0,  0, -1,  0],
            [ 0,  0,  0,  0,  1],
            [ 0,  0,  0,  0, -1]]



rhs_ineq = [ 300,
            -165,
             270,
             60,
             918,
             64,
             302,
             1200,
             50,
            -35,
             57,
            -25,
             66,
            -30,
             66,
            -40,
             61,
            -30]

bnd = [(0, float("inf")),
       (0, float("inf")),
       (0, float("inf")),
       (0, float("inf")),
       (0, float("inf"))]

opt = linprog(c=obj, A_ub=lhs_ineq, b_ub=rhs_ineq, bounds=bnd, 
              method="revised simplex")
opt
