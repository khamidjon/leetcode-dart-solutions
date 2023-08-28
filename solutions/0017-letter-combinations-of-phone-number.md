```
class Solution {
  List<String> letterCombinations(String digits) {
      if(digits.length == 0) {
          return [];
      }
      
      final givenMap = {
        '2': ['a', 'b', 'c'],
        '3': ['d', 'e', 'f'],
        '4': ['g', 'h', 'i'],
        '5': ['j', 'k', 'l'],
        '6': ['m', 'n', 'o'],
        '7': ['p', 'q', 'r', 's'],
        '8': ['t', 'u', 'v'],
        '9': ['w', 'x', 'y', 'z'],
      };

      if(digits.length == 1){
        return givenMap[digits[0]]!;
      }

      final result =<String> [];
  
       void backTrack(int index, String curString){
          if(curString.length == digits.length){
            result.add(curString);
            return;
          }

          for(final value in givenMap[digits[index]]!){
            backTrack(index + 1, curString + value);
          }
        }
      backTrack(0, '');
      return result;
  }
}
```
