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
* T(n) = O(n^d) &emsp;&emsp; (case 2) if a < b^d
* T(n) = O(n^{log_b a}) (case 3) if a > b^d
