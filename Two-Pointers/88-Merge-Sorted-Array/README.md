# 88. Merge Sorted Array — My Solution

> Notion solution copied into the Two Pointers folder.

## 📌 Approach

Merge two sorted arrays into `nums1` in-place. `nums1` already has `m + n` capacity, with the last `n` positions empty.

Example:

```text
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output = [1,2,2,3,5,6]
```

### 1️⃣ Brute Force

Create a temporary array, copy both arrays, sort, then copy back.

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int[] temp = new int[m + n];
        int index = 0;

        for (int i = 0; i < m; i++) {
            temp[index++] = nums1[i];
        }

        for (int i = 0; i < n; i++) {
            temp[index++] = nums2[i];
        }

        Arrays.sort(temp);

        for (int i = 0; i < temp.length; i++) {
            nums1[i] = temp[i];
        }
    }
}
```

- Time: O((m+n) log(m+n))
- Space: O(m+n)

### 2️⃣ Better Approach

Copy `nums2` to the empty end of `nums1`, then sort the combined array.

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        for (int i = 0; i < n; i++) {
            nums1[m + i] = nums2[i];
        }

        Arrays.sort(nums1);
    }
}
```

- Time: O((m+n) log(m+n))
- Space: O(1) extra

### 3️⃣ Best — Three Pointer ⭐

Because both arrays are sorted and `nums1` has free space at the end, merge **from the back**.

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;

        while (i >= 0 && j >= 0) {
            if (nums1[i] > nums2[j]) {
                nums1[k] = nums1[i];
                i--;
            } else {
                nums1[k] = nums2[j];
                j--;
            }
            k--;
        }

        while (j >= 0) {
            nums1[k] = nums2[j];
            j--;
            k--;
        }
    }
}
```

- Time: O(m+n)
- Space: O(1)

### 🧠 Revision Shortcut

```text
Sorted Arrays
→ largest element is at the end
→ merge from back
→ i = m - 1
→ j = n - 1
→ k = m + n - 1
→ place larger value at nums1[k]
→ k--
```

### 🎤 Interview Script

“Since both arrays are already sorted and `nums1` has empty space at the end, I merge from the back. I keep one pointer at the last valid element of `nums1`, one at the last element of `nums2`, and one write pointer at the end of `nums1`. I place the larger value first, which avoids overwriting unprocessed values. The solution is O(m+n) time and O(1) extra space.”
