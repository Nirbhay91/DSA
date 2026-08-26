# 283. Move Zeroes — My Solution

## 📌 Approach

Ek array diya hai. Saare `0`s ko end me move karna hai, non-zero elements ka relative order preserve karte hue, aur in-place.

### Brute Force
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int[] temp = new int[nums.length];
        int index = 0;
        for (int num : nums) {
            if (num != 0) temp[index++] = num;
        }
        while (index < nums.length) temp[index++] = 0;
        for (int i = 0; i < nums.length; i++) nums[i] = temp[i];
    }
}
```
Time `O(n)`, Space `O(n)`.

### Better — Shifting
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int n = nums.length;
        for (int i = 0; i < n; i++) {
            if (nums[i] == 0) {
                for (int j = i; j < n - 1; j++) {
                    nums[j] = nums[j + 1];
                }
                nums[n - 1] = 0;
                i--;
            }
        }
    }
}
```
Time `O(n²)`, Space `O(1)`.

### Best — Two Pointer ⭐
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int i = 0;
        for (int j = 0; j < nums.length; j++) {
            if (nums[j] != 0) {
                int temp = nums[i];
                nums[i] = nums[j];
                nums[j] = temp;
                i++;
            }
        }
    }
}
```
Time `O(n)`, Space `O(1)`.

### Revision Shortcut
`Move Zeroes` → non-zero ko front me lao → `i` next valid position → `j` scanner → non-zero mila → swap → `i++`.

Source: Notion solution. fileciteturn445file0