```
class Solution {
  int maxArea(List<int> height) {
      int result = 0;
      
      int left = 0;
      int right = height.length - 1;
      
      while (left < right) {
          int amount = (right - left) * min(height[left], height[right]);
          result = max(result, amount);
          
          if (height[right] > height[left]) {
              left++;
          } else {
              right--;
          }
      }
      return result;
  }
}
```
