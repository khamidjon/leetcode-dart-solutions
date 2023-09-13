```
class Solution {
  bool containsNearbyDuplicate(List<int> nums, int k) {
      final map = Map<int, int>();
      
      for (int i = 0; i < nums.length; i++) {
          int current = nums[i];
          if (map.containsKey(current) && i - map[current]! <= k) {
              return true;
          } else {
              map[current] = i;
          }      
      }
      return false;
  }
}
```
