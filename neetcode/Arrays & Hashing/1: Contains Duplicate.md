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
        const numsSeen = new Set();
        for (let i = 0; i < nums.length; i++) {
            if (numsSeen.has(nums[i])) {
                return true;
            }
            numsSeen.add(nums[i]);
        }
        return false;
    }
}
```

## ポイント

- **存在チェック (`has`) → Set / Map を疑う**。`includes()` は `O(n)` なのでループ内で使うと `O(n²)` に化ける
- **早期 return**: Yes/No 型の問題は見つけた瞬間に返す

## 他の問題にも活かせる考え方

- **「2 重ループを書きたくなったら、見た情報を Hash に持たせて 1 ループにできないか？」**（Two Sum, Longest Substring など共通）
- **Time ↔ Space のトレードオフ**: O(n²) Brute Force ↔ O(n) Hash（メモリで時間を買う）
- **ソート解法の落とし穴**: `Array.prototype.sort()` は元配列を破壊。数値比較には `(a,b)=>a-b` を渡す（デフォルトは文字列比較）
