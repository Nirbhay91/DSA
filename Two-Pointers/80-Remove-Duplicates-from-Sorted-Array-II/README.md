# 80. Remove Duplicates from Sorted Array II — My Solution

> Notion solution copied into the Two Pointers folder.

## 📌 Approach

Given a **sorted array**, every value may appear at most **twice**. Remove extra occurrences in-place.

Example:

```text
Input:  [1,1,1,2,2,3]
Output: 5
Array:   [1,1,2,2,3]
```

### 1️⃣ Brute Force

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        List<Integer> result = new ArrayList<>();

        for (int num : nums) {
            int count = 0;
            for (int existing : result) {
                if (existing == num) {
                    count++;
                }
            }

            if (count < 2) {
                result.add(num);
            }
        }

        for (int i = 0; i < result.size(); i++) {
            nums[i] = result.get(i);
        }

        return result.size();
    }
}
```

- Time: O(n²)
- Space: O(n)

### 2️⃣ HashMap

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        Map<Integer, Integer> frequency = new HashMap<>();
        List<Integer> result = new ArrayList<>();

        for (int num : nums) {
            int count = frequency.getOrDefault(num, 0);

            if (count < 2) {
                result.add(num);
                frequency.put(num, count + 1);
            }
        }

        for (int i = 0; i < result.size(); i++) {
            nums[i] = result.get(i);
        }

        return result.size();
    }
}
```

- Time: O(n) average
- Space: O(n)

### 3️⃣ Best — Two Pointer ⭐

The first two elements are always valid. For every next element, compare it with the element **two valid positions behind**.

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length <= 2) {
            return nums.length;
        }

        int i = 2;

        for (int j = 2; j < nums.length; j++) {
            if (nums[j] != nums[i - 2]) {
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

### ⭐ Why `i - 2`?

```text
Allowed copies = 1 → compare with nums[i - 1]
Allowed copies = 2 → compare with nums[i - 2]
Allowed copies = k → compare with nums[i - k]
```

### 🧠 Revision Shortcut

```text
Sorted Array
→ duplicates adjacent
→ At Most Twice
→ i = 2
→ j = 2
→ nums[j] != nums[i - 2]
→ nums[i] = nums[j]
→ i++
→ return i
```

### 🎤 Interview Script

“Because the array is sorted, duplicates are adjacent. The first two elements are always allowed. Then I keep a slow pointer at the next valid position and compare each scanned value with the value two valid positions behind. If they are different, the current value can be safely kept. That gives O(n) time and O(1) extra space.”
