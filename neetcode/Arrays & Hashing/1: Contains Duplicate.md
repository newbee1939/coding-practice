## 問題

https://neetcode.io/problems/duplicate-integer/question

重複チェック:

## 回答

```ts
class Solution {
    /**
     * @param {number[]} nums
     * @return {boolean}
     */
    hasDuplicate(nums: number[]): boolean {
        const numsMap = new Set();
        for (let i = 0; i < nums.length; i++) {
            if (numsMap.has(nums[i])) {
                return true;
            }
            numsMap.add(nums[i]);
        }
        return false;
    }
}
```
