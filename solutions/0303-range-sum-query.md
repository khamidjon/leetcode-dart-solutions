```
class NumArray {
  late final List<int> nums;
  NumArray(List<int> nums) {
      this.nums = nums;
  }
  
  int sumRange(int left, int right) {
      int sum = 0;

      for (int i = left; i<= right; i++) {
          sum += nums[i];
      }
      return sum;
  }
}
```
