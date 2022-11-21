# まとめ
定数で、ローマ数字＋値のMapを作成しておくのが、可読性も高くいい感じかな？

ローマ数字の計算方法の特徴は、次(前)の数字と比較して、大きいか少ないかで数値が変わること。
VI＝６だから、V + Iでいい。だけれども、IV＝４だから、V - Iをしなければならない。
以下のプログラムでは、後ろから前に向かって進んでいく計算方法だが、これを組み込む。

IVを例に考えると、
前(V)が、現在(無し)よりも大きいか見るが、初回なので、必ず合計値に追加。前=Vとする。<br>
前(V)が、現在(I)よりも大きい場合、合計値から現在(I)を引く。これで再現する。


# Code
void main() {
  // ローマ数字
  var s = "MCMXCIV";
  var int = romanToInt(s);
  print(int);
}

int romanToInt(String s) {
  Map<String, int> romanMap = {
    "I": 1,
    "V": 5,
    "X": 10,
    "L": 50,
    "C": 100,
    "D": 500,
    "M": 1000,
  };

  int sum = 0;
  int current = 0;
  int pre = 0;

  for (var i = s.length - 1; i >= 0; i--) {
    current = romanMap[s[i]]!;
    if (pre > current) {
      sum = sum - current;
    } else {
      sum = sum + current;
      pre = current;
    }
  }
  return sum;
}
