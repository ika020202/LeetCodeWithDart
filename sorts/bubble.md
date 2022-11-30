# まとめ
隣接する値を比較して、交換していく有名なソート。計算量はO(n2)。 
変数iのfor文は調べる範囲の開始位置を１つずつ後ろへ移動するため（1ループで調べる回数が１減るから）  
変数jのfor文は後ろから前に向かって小さな値を交換していくため

# Code

```dart
void main() {
  // ソート前データ
  var targetData = [3, 4, 8, 1, 9, 5, 6, 7, 2];
  for (var i = 0; i < targetData.length; i++) {
    for (var j = targetData.length - 1; j > i; j--) {
      if (targetData[j] < targetData[j - 1]) {
        var tmp = targetData[j];
        targetData[j] = targetData[j - 1];
        targetData[j - 1] = tmp;
      }
    }
  }
  print(targetData);
}
```
