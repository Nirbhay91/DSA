# 977. Squares of a Sorted Array — My Solution

## 📌 Approach

Sorted array diya hai; har element ka square nikal kar sorted order return karna hai.

### Brute Force
Square karo, then sort.

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] result = new int[nums.length];
        for (int i = 0; i < nums.length; i++) {
            result[i] = nums[i] * nums[i];
        }
        Arrays.sort(result);
        return result;
    }
}
```
Time `O(n log n)`, Space `O(n)`.

### Better — Merge Logic
Negative and positive parts ke squares ko merge karo.

### Best — Two Pointer ⭐
Largest square hamesha left ya right end par hoga. Result ko back se fill karo.

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        int n = nums.length;
        int[] result = new int[n];
        int left = 0;
        int right = n - 1;
        int index = n - 1;

        while (left <= right) {
            int leftSquare = nums[left] * nums[left];
            int rightSquare = nums[right] * nums[right];

            if (leftSquare > rightSquare) {
                result[index] = leftSquare;
                left++;
            } else {
                result[index] = rightSquare;
                right--;
            }
            index--;
        }
        return result;
    }
}
```
Time `O(n)`, Space `O(n)` for returned result array.

### Revision Shortcut
Sorted + square → largest absolute value at one of the ends → compare left/right squares → fill result from back.

Source: Notion solution. fileciteturn446file0