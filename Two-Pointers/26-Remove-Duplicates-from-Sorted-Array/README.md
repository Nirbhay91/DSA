# 26. Remove Duplicates from Sorted Array — My Solution

> Notion solution copied into the Two Pointers folder.

## 📌 Approach

Given a **sorted array**, remove duplicates **in-place** and return the number of unique elements.

Example:

```text
Input:  [1,1,2]
Output: 2
Array:   [1,2,_]
```

### 1️⃣ Brute Force

Create a new list of unique values and copy them back.

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        List<Integer> unique = new ArrayList<>();

        for (int num : nums) {
            if (!unique.contains(num)) {
                unique.add(num);
            }
        }

        for (int i = 0; i < unique.size(); i++) {
            nums[i] = unique.get(i);
        }

        return unique.size();
    }
}
```

- Time: O(n²)
- Space: O(n)

### 2️⃣ HashSet

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        Set<Integer> set = new LinkedHashSet<>();

        for (int num : nums) {
            set.add(num);
        }

        int index = 0;
        for (int num : set) {
            nums[index++] = num;
        }

        return set.size();
    }
}
```

- Time: O(n) average
- Space: O(n)

### 3️⃣ Best — Two Pointer ⭐

Because the array is sorted, duplicates are adjacent.

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length == 0) {
            return 0;
        }

        int i = 0;

        for (int j = 1; j < nums.length; j++) {
            if (nums[j] != nums[i]) {
                i++;
                nums[i] = nums[j];
            }
        }

        return i + 1;
    }
}
```

- Time: O(n)
- Space: O(1)

### 🧠 Revision Shortcut

```text
Sorted Array
→ duplicates are adjacent
→ i = last unique position
→ j = scanner
→ nums[j] != nums[i]
→ i++; nums[i] = nums[j]
→ return i + 1
```

### 🎤 Interview Script

“Because the array is sorted, duplicate values are adjacent. I keep a slow pointer at the last unique position and use a fast pointer to scan the array. Whenever I find a new value, I place it immediately after the last unique value. This gives O(n) time and O(1) extra space.”
