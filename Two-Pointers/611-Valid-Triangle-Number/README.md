# 611. Valid Triangle Number — My Solution

## 📌 Approach

Triangle condition: after sorting `a <= b <= c`, only `a + b > c` needs to be checked.

### Brute Force
3 nested loops.

Time `O(n³)`, Space `O(1)`.

### Better — Sorting + Binary Search
Fix two sides and binary-search the last valid third side.

Time `O(n² log n)`, Space `O(1)` excluding sorting implementation details.

### Best — Sorting + Two Pointer ⭐
Fix largest side `k`, then use `i` and `j` from both ends.

```java
class Solution {
    public int triangleNumber(int[] nums) {
        Arrays.sort(nums);
        int count = 0;

        for (int k = nums.length - 1; k >= 2; k--) {
            int i = 0;
            int j = k - 1;

            while (i < j) {
                if (nums[i] + nums[j] > nums[k]) {
                    count += j - i;
                    j--;
                } else {
                    i++;
                }
            }
        }
        return count;
    }
}
```
Time `O(n²)`, Space `O(1)` extra apart from sorting.

### Why `count += j - i`?
Array sorted hai. Agar `nums[i] + nums[j] > nums[k]`, then `i..j-1` ke saare possible first sides bhi valid honge.

### Revision Shortcut
Sort → largest side `k` fix → `i=0`, `j=k-1` → if sum > largest, `count += j-i` and `j--`; else `i++`.

Source: Notion solution. fileciteturn448file0