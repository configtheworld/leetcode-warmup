# Group Anagrams

given an array of strings strs, group the anagrams together.

- hold the knowing strings in knowStrs array then iterating the size of the strs. str_split to turning each char into element of array then sorting them will give occurences next to each other eg aaabbbcccccdeee. then used implode for creating string from array elements.

```php
class Solution {

    /**
     * @param String[] $strs
     * @return String[][]
     */
    function groupAnagrams($strs) {
        $knownStrs = [];
        for($i=0;$i<count($strs);$i++){
            $strArr = str_split($strs[$i]);
            sort($strArr);
            $strSorted = implode("",$strArr);
            $knownStrs[$strSorted][]=$strs[$i];
        }
        return array_values($knownStrs);
    }
}
```
