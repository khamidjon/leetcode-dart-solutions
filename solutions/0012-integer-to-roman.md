```
class Solution {
  String intToRoman(int number) {
      final numerals = [['I', 1], ['IV', 4], ['V', 5], ['IX', 9], ['X', 10],
        ['XL', 40], ['L', 50], ['XC', 90], ['C', 100], ['CD', 400], ['D', 500],
        ['CM', 900], ['M', 1000],
      ];

      var res = '';

      for(final numeral in numerals.reversed) {
        final n = numeral[1] as int;
        final s = numeral[0] as String;
          if(number ~/ n != 0) {
              int count = number ~/ n;
              res += (s * count);
              number = number % n;
          }
      }
      return res;
  }
}
```
