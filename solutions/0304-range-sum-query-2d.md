```
class NumMatrix {
  late final List<List<int>> matrix;
  NumMatrix(List<List<int>> matrix) {
      int cols = matrix[0].length;
      int rows = matrix.length;

      this.matrix = [];
      for (int i = 0; i < rows + 1; i++) {
          final temp = <int>[];
          for(int j = 0; j < cols + 1; j++) {
              temp.add(0);
          }
          this.matrix.add(temp);
      }

      for (int r = 0; r < rows; r++){
          int prefix = 0;
          for (int c = 0; c < cols; c++) {
              prefix += matrix[r][c];
              int above = this.matrix[r][c + 1];
              this.matrix[r + 1][c + 1] = prefix + above;
          }
      }
  }
  
  int sumRegion(int row1, int col1, int row2, int col2) {
      row1 += 1;
      col1 += 1;
      row2 += 1;
      col2 += 1;

      final bottomRight = this.matrix[row2][col2];
      final above = this.matrix[row1 - 1][col2];
      final left = this.matrix[row2][col1 - 1];
      final topLeft = this.matrix[row1 - 1][col1 - 1];

      return bottomRight - above - left + topLeft;
  }
}

/**
 * Your NumMatrix object will be instantiated and called as such:
 * NumMatrix obj = NumMatrix(matrix);
 * int param1 = obj.sumRegion(row1,col1,row2,col2);
 */
```
