# 27. Remove Element — My Solution

> Notion solution copied into the Two Pointers folder.

## 📌 Approach

Remove every occurrence of `val` **in-place** and return the new effective length.

Example:

```text
Input:  [3,2,2,3], val = 3
Output: 2
Array:   [2,2,_,_]
```

### 1️⃣ Brute Force

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        List<Integer> list = new ArrayList<>();

        for (int num : nums) {
            if (num != val) {
                list.add(num);
            }
        }

        for (int i = 0; i < list.size(); i++) {
            nums[i] = list.get(i);
        }

        return list.size();
    }
}
```

- Time: O(n)
- Space: O(n)

### 2️⃣ Shifting Approach

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int n = nums.length;

        for (int i = 0; i < n; i++) {
            if (nums[i] == val) {
                for (int j = i; j < n - 1; j++) {
                    nums[j] = nums[j + 1];
                }
                n--;
                i--;
            }
        }

        return n;
    }
}
```

- Time: O(n²)
- Space: O(1)

### 3️⃣ Best — Two Pointer ⭐

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int i = 0;

        for (int j = 0; j < nums.length; j++) {
            if (nums[j] != val) {
                nums[i] = nums[j];
                i++;
            }
        }

        return i;
    }
}
```

- Time: O(n)
- Space: O(1)

### 🧠 Revision Shortcut

```text
Remove Element
→ skip target
→ i = next valid position
→ j = scanner
→ nums[j] != val
→ nums[i] = nums[j]
→ i++
→ return i
```

### 🎤 Interview Script

“Because the requirement is in-place, I avoid an extra array. A fast pointer scans every element and a slow pointer marks the next position for a valid non-target element. Every non-target value is copied forward. The solution is O(n) time and O(1) extra space.”
