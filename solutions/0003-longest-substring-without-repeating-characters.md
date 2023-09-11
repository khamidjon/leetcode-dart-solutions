```
class Solution {
  int lengthOfLongestSubstring(String s) {
      if (s.isEmpty) {
          return 0;
      }
      final chars = <String>{};
      int result = 1;
      
      for (int i = 0; i < s.length; i++) {
          for(int j = i; j < s.length; j++ ) {
              if (chars.contains(s[j])) {
                result = max(result, chars.length);
                chars.clear();
                break;
              } else {
                chars.add(s[j]);
              }
          }     
      }
      return max(result, chars.length);
  }
}
```
