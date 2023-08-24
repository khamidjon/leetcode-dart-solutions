```
class Solution {
  String convert (String s, int numRows) {
      if (numRows == 1) {
          return s;
      }
      final buffer = StringBuffer();
      
      for (int r = 0; r < numRows; r++) {
          int increment = 2 * (numRows - 1);
          
          for (int i = r; i < s.length; i += increment) {
              buffer.write(s[i]);
              
              if (r > 0 && r < numRows - 1 && i + increment - 2 * r < s.length) {
                  buffer.write(s[i + increment - 2 * r]);
              }
          }
      } 
      return buffer.toString();
  }
}
```
