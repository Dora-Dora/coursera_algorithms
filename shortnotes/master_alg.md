**The Master Algorithm**
1. Base Case: T(n) <= const (for suff. small n)
2. For all larger n:
  T(n) <= a T(n/b) + O(n^d)
  where a = # of recursive calls (>=1)
        b = input size shrinkage factor (>1)
        d = exponent in running time of "combine step" (>=0)
        (a,b,c are independt of n)
