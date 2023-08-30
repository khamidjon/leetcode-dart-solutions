```
class Solution {
  bool isAnagram(String s, String t) {
      final map = <String, int>{};
      
      for (int i = 0; i < s.length; i++) {
          if (map[s[i]] != null) {
              int count = map[s[i]]!;
              map[s[i]] = count + 1;
          } else {
              map[s[i]] = 1;
          }
      }
      
      for (int i = 0; i < t.length; i++) {
          if (map[t[i]] != null) {
              int count = map[t[i]]!;
              map[t[i]] = count - 1;
              if (map[t[i]] == 0) {
                  map.remove(t[i]);
              }
          } else {
              return false;
          }
      }
      return map.isEmpty;
  }
}
```
