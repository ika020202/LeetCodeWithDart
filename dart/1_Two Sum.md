# まとめ
forの組み合わせでもいいけど、
ハッシュマップに既に探索した配列のKeyValueを格納して、ハッシュマップから探索することで、計算量が減る。

重要な事は、配列要素iに対して何を足せばTargetNoになるのかを求める(requiredNumの定義)
IndexMapのキーを配列に格納されている要素にすると、containsKeyメソッドを使用して、requiredNumに一致するKeyを探索できる。

# Code

```dart
class Solution {
  List<int> twoSum(List<int> nums, int target) {
      Map indexMap={};
      for(var i=0;i<nums.length;i++){
          var requiredNum = (target - nums[i]);
          if(indexMap.containsKey(requiredNum)){
              return [indexMap[requiredNum],i];
            }

            indexMap[nums[i]]= i;
        }
        return [];
    }
 }
```
