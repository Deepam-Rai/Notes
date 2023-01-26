Definition: LP is mathematical technique to optimize a linear objective function subject to constraints represented by linear equations or inequalities.
#TODO mathematical expression

# Methods

## Corner-point method (Graphical)
Plot the feasible reason of LP in the graph and identify the corner points, which are taken as candidate for the optimal solution.

1. Plot the feasible regaion in graph.
2. Identify the corner points.
3. Evaluate the objective function at the corner points.
4. Choose optimal(max/min) solution based upon the evaluation.

#### Why cornerpoints? Extreme Value Theorem
For a continuous function on a closed and bounded set, an optimal solution(max or min) must occur at an extreme point(aka endpoint, boundary point) of the set.

- In LP intuitively if you are not taking the corner point, then consequently there is/are  direction/dimension moving along which the value of some variable will increase/decrease, which consequently would mean objective function would increase/decrease if we move along that line.

## Simplex method
Its an iterative algorithm for solving LP that starts at an initial feasible solution and then moves to adjacent solution that improves the objective function until the optimal solution is reached.

Simplex tableau, pivot element