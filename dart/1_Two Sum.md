# 解き方
forの組み合わせでもいいけど、
ハッシュマップに既に探索した配列のKeyValueを格納して、ハッシュマップから探索することで、計算量が減る

# Code Sample

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
