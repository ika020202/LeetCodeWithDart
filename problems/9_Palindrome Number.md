# まとめ
数値のまま計算する事で、反転数値を作成し、それに一致するかどうかというアルゴリズムが最速だけど...暗記必須の方法なのでやめる。
直感で出来る＋int型以外も使用できる方法でしたい。
⇒String型に変換し、反転するという方法で比較する。

・マイナス数値と、0以外の語末が0になる数値(10,100など)は必ずfalseなので先に省いておくと処理時間が若干短縮される。

# Code
```dart
class Solution {
  bool isPalindrome(int x) {
    if(x < 0 || (x != 0 && x % 10 == 0)){
        return false;
    }
    String stringValue = x.toString();
    int reversedNumber = int.parse(stringValue.split('').reversed.join(''));

    return x == reversedNumber ? true : false;

  }
}
```
