# Valid Anagram

- First approach I tried checking length of the strings and with for loop I checked does t includes s[i], and remove the character s[i] from t

```ts
function isAnagram(s: string, t: string): boolean {
  // equal length and exact chars
  if (s.length !== t.length) return false;
  for (let i = 0; i < s.length; i++) {
    if (!t.includes(s[i])) {
      return false;
    }
    let iChar = t.indexOf(s[i]);
    t = t.slice(0, iChar) + t.slice(iChar + 1);
  }
  return true;
}
```

- in PHP there is a function count_chars

```php

class Solution {

    /**
     * @param String $s
     * @param String $t
     * @return Boolean
     */
    function isAnagram($s, $t) {
        return count_chars($s) == count_chars($t);
    }
}

```
