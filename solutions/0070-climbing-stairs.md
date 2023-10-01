```
class Solution {
    int climbStairs (int n) {
        int one = 1;
        int two = 1;
        
        for (int i = 1; i <= n-1; i++) {
            int temp = one;
            one = one + two;
            two = temp;
        }
        return one;        
    }

    // time limit
    int fib(int m) {
        if(m == 0 || m == 1) {
            return 1;
        }
        return fib(m-1) + fib(m-2);
    }
}
```
