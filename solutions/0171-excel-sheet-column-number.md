```
class Solution {
    int titleToNumber(String columnTitle) {
        num result = 0;
        for (int i= 0; i < columnTitle.length; i++) {
            result = result + charToInt(columnTitle[columnTitle.length - 1 - i]) * pow(26, i);
        }
        return result.toInt();
    }
    
    int charToInt(String s) {
        return s.codeUnits[0] - 64;
    }
}
```
