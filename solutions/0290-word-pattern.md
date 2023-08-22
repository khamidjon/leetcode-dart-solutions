```
class Solution {
  bool wordPattern(String pattern, String s) {
      List<String> input = s.split(' ');
      Map<String, String> dict = {};

      int patternLength = pattern.length;
      int inputLength = input.length;
      if (patternLength != inputLength) {
          return false;
      }
      for(int i = 0; i < patternLength; i++) {
          if(dict.keys.contains(pattern[i])){
              if(dict[pattern[i]] != input[i]) {
                  return false;
              }
          } else {
              if(dict.values.contains(input[i]))
                    return false;
              dict[pattern[i]] = input[i];
          }
      }
      return true;
  }
}
```
