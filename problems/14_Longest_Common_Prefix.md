# まとめ
垂直にチェックしていく形のPrefixチェッカー。<br>
最初のfor文は、配列[0]の文字を順に見ていくためのもの。そのため、繰り返し回数は配列の長さではなく、要素[0]の文字数<br>
内側のfor文は、配列[2,3...n]の1文字目を順番に見ていくもの。<br>
つまり、[0]を除く、全ての配列要素の先頭文字を見ていく垂直処理を行う<br>

# Code
```dart
void main() {
  var strs = ["flower", "flow", "flight"];
  var result = preFix(strs);
  print(result);
}

String preFix(List<String> strs) {
  if (strs.length == 0 || strs.isEmpty || strs.length == '') {
    return "";
  }

  String checkStr = "";
  // 前提として、垂直にチェックしていく。
  // そのため、最初のFor文は、List[0]の1文字目を格納して、他の要素をチェックしていく。
  for (int i = 0; i < strs[0].length; i++) {
    print(strs[0][i]);
    checkStr = strs[0][i];

    for (int j = 1; j < strs.length; j++) {
      if (i == strs[j].length || strs[j][i] != checkStr)
        return strs[0].substring(0, i);
    }
  }
  return strs[0];
}

```
