# 75. Sort Colors — My Solution

> Notion solution copied into the Two Pointers folder.

## 📌 Approach

The array contains only `0`, `1`, and `2`. Sort it in-place.

Example:

```text
Input:  [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
```

### 1️⃣ Brute Force

```java
class Solution {
    public void sortColors(int[] nums) {
        Arrays.sort(nums);
    }
}
```

- Time: O(n log n)
- Space: depends on implementation

### 2️⃣ Counting Sort

```java
class Solution {
    public void sortColors(int[] nums) {
        int zero = 0, one = 0, two = 0;

        for (int num : nums) {
            if (num == 0) {
                zero++;
            } else if (num == 1) {
                one++;
            } else {
                two++;
            }
        }

        int index = 0;
        while (zero-- > 0) nums[index++] = 0;
        while (one-- > 0) nums[index++] = 1;
        while (two-- > 0) nums[index++] = 2;
    }
}
```

- Time: O(n)
- Space: O(1)

### 3️⃣ Best — Dutch National Flag / Three Pointer ⭐

Maintain three regions:

```text
0s | processed 1s | unknown | 2s
```

Pointers:

- `low` → next position for `0`
- `mid` → current element
- `high` → next position for `2`

```java
class Solution {
    public void sortColors(int[] nums) {
        int low = 0;
        int mid = 0;
        int high = nums.length - 1;

        while (mid <= high) {
            if (nums[mid] == 0) {
                swap(nums, low, mid);
                low++;
                mid++;
            } else if (nums[mid] == 1) {
                mid++;
            } else {
                swap(nums, mid, high);
                high--;
                // mid is NOT incremented here.
            }
        }
    }

    private void swap(int[] nums, int i, int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

- Time: O(n)
- Space: O(1)

### ⭐ Why `mid` Does Not Move When Value Is `2`

Suppose:

```text
2 1 0
```

Swap `nums[mid]` with `nums[high]`:

```text
0 1 2
```

The new value at `mid` has not been examined yet. Therefore `mid` must stay where it is until that value is classified.

### 🧠 Revision Shortcut

```text
Only 0, 1, 2
→ low / mid / high
→ 0 → swap(low, mid), low++, mid++
→ 1 → mid++
→ 2 → swap(mid, high), high--
→ for 2, do NOT increment mid
```

### 🎤 Interview Script

“Because the array contains only three values, I can partition it into three regions using the Dutch National Flag algorithm. `low` tracks the next position for zero, `mid` scans the unknown region, and `high` tracks the next position for two. Zero moves left, two moves right, and one stays in the middle. When I swap a two with the high position, I do not increment `mid` because the newly swapped value still needs to be processed. The algorithm is O(n) time and O(1) extra space.”
