# Contains Duplicate

- First approach I tried storing items in another array to check is there a duplicate, however, its sucks if the input is so long and duplicates are just position at really late iterations

```ts
function containsDuplicate(nums: number[]): boolean {
  let uniques = [];
  let duplicateFlag = false;
  for (let i = 0; i < nums.length; i++) {
    if (duplicateFlag) {
      break;
    }
    if (uniques.includes(nums[i])) {
      duplicateFlag = true;
    } else {
      uniques.push(nums[i]);
    }
  }
  return duplicateFlag;
}
```

- second approach, first successful approaach was sorting an array first then comparing index i and i+1 to find the duplicates

```ts
function containsDuplicate(nums: number[]): boolean {
  const sortedArr = nums.sort();
  const duplicateFlag = false;
  for (let i = 0; i < sortedArr.length; i++) {
    if (sortedArr[i] === sortedArr[i + 1]) {
      return true;
    }
  }
  return duplicateFlag;
}
```

- third approach is using Set() and with one operations checking does hashSet has the value

```ts
function containsDuplicate(nums: number[]): boolean {
  const hashSet = new Set();
  for (let i = 0; i < nums.length; i++) {
    if (hashSet.has(nums[i])) {
      return true;
    }
    hashSet.add(nums[i]);
  }

  return false;
}
```

- In PHP its with one function which tells the occurencies array_count_values

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Boolean
     */
    function containsDuplicate($nums) {
        $countValues = array_count_values($nums);
        foreach ($countValues as $quantity){
            if($quantity>=2)return true;
        }
        return false;
    }
}
```
