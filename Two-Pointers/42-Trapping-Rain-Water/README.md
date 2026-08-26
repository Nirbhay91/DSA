# 42. Trapping Rain Water — My Solution

## 📌 Approach

Formula:

`water at i = min(leftMax, rightMax) - height[i]`

### Brute Force
Har index par leftMax aur rightMax calculate karo.

Time `O(n²)`, Space `O(1)`.

### Better — Precompute Arrays
`leftMax[]` and `rightMax[]` build karo, then each index ka water calculate karo.

Time `O(n)`, Space `O(n)`.

### Best — Two Pointer ⭐
`left`, `right`, `leftMax`, `rightMax` maintain karo. Smaller current-height side process karo.

```java
class Solution {
    public int trap(int[] height) {
        int left = 0;
        int right = height.length - 1;
        int leftMax = 0;
        int rightMax = 0;
        int water = 0;

        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= leftMax) {
                    leftMax = height[left];
                } else {
                    water += leftMax - height[left];
                }
                left++;
            } else {
                if (height[right] >= rightMax) {
                    rightMax = height[right];
                } else {
                    water += rightMax - height[right];
                }
                right--;
            }
        }
        return water;
    }
}
```
Time `O(n)`, Space `O(1)`.

### Revision Shortcut
Smaller side move karo → corresponding max maintain karo → `max - height` water add karo.

Source: Notion solution. fileciteturn447file0