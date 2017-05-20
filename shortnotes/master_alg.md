**The Master Algorithm (from lecture IV)**

1. Base Case: T(n) <= const (for suff. small n)
2. For all larger n:
  T(n) <= a T(n/b) + O(n^d)
  where
* a = # of recursive calls (>=1)
* b = input size shrinkage factor (>1)
* d = exponent in running time of "combine step" (>=0)
* (a,b,c are independt of n)

The running time can be shown to be:
* T(n) = O(n^d logn) &emsp; (case 1) if a = b^d
* T(n) = O(n^d) &emsp;&emsp;&emsp;&nbsp;(case 2) if a < b^d
* T(n) = O(n^{log_b a}) (case 3) if a > b^d

Note that the coefficients
* a = rate of subproblem proliferation (RSP) -> more problem as we go down the recursion tree
* b^d = rate of work shrinkage (RWS) per subproblem -> do less work as we go down the recursion tree
And at each level of the recursion tree, the upper bound of runtime is
<p align="center"> cn^d (a/(b^d))^j </p>

So the intuition of the running time for the 3 cases
* RSP = RWS -> same amount of work each level (e.g. Merge sort) -> O(n^d logn)
* RSP < RWS -> less work as we go down the recursion tree -> O(n^d)
* RSP > RWS -> more work as we go down the revursion tree -> O(# of leaves = a^{log_b n} = n^{log_b a})
