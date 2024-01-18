```
class Solution {
  int threeSumClosest(List<int> nums, int target) {
    int result = nums[0] + nums[1] + nums[nums.length - 1];
    nums.sort();
    for (int i = 0; i < nums.length - 2; i++) {
            int leftPtr = i+1;
            int rightPtr = nums.length - 1; 

            while (leftPtr < rightPtr) {
                int curSum = nums[i] + nums[leftPtr] + nums[rightPtr];
                if (curSum > target) {
                    rightPtr -=1;
                } else {
                    leftPtr += 1;
                }

                if((curSum - target).abs() < (result - target).abs()){
                    result = curSum;
                }
            }
    }
    return result;
  }
}
```
