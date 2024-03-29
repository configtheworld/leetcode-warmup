# Two Sum

- In PHP we set up a empty array then iterating the values of given array and trying to find a remaning sum for target value. if array has the remaining value we return indexes otherwise we add the value to the array

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function twoSum($nums, $target) {
        $arr = [];
        for($i=0;$i<count($nums);$i++){
                $remaining = $target-$nums[$i];
                if(isset($arr[$remaining])){
                    return array($i,$arr[$remaining]);
                }else{
                    $arr[$nums[$i]]=$i;
                }
        }
        return [];
    }
}
```

- In TS iterating the array and checking array includes remaining and remaining index is not same with the one we have

```ts
function twoSum(nums: number[], target: number): number[] {
  for (let i = 0; i < nums.length; i++) {
    if (
      nums.includes(target - nums[i]) &&
      i != nums.indexOf(target - nums[i])
    ) {
      return [i, nums.indexOf(target - nums[i])];
    }
  }
}
```
