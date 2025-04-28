# LEETCODE-Arrays-3392
---
---

## Solution Overview

The `Solution` class contains the method `countSubarrays` which:

- Takes an integer array `nums` as input.
- Iterates over the array from index `1` to `nums.length - 2`.
- For each index `i`, checks if the condition `(nums[i-1] + nums[i+1]) * 2 == nums[i]` holds true.
- Counts the number of times the condition is satisfied.
- Returns the final count.

---

## Code

```java
class Solution {
    public int countSubarrays(int[] nums) {
        int count = 0;
        for (int i = 1; i < nums.length - 1; i++) {
            if ((nums[i-1] + nums[i+1]) * 2 == nums[i]) {
                count++;
            }
        }
        return count;
    }
}
```

---

## Example

**Input:**  
`nums = [1, 5, 3, 7, 9]`

**Working:**  
- i=1: (1 + 3) * 2 = 8 ≠ 5 → no
- i=2: (5 + 7) * 2 = 24 ≠ 3 → no
- i=3: (3 + 9) * 2 = 24 ≠ 7 → no

**Result:**  
`0`

---

## Notes

- The first and last elements are **never** checked because they do not have two neighbors.
- The array must have at least 3 elements for a valid check to happen.
- Time Complexity: **O(n)**, where `n` is the length of the array.
- Space Complexity: **O(1)** (constant extra space).

---
