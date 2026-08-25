# 1. Two Sum — My Solution

> Source: [Notion — 1. Two Sum — My Solution](https://app.notion.com/p/3a9b63f7c2ee8122b334cc3bf04e52c3)

## 📌 Problem

Ek array `nums` aur ek `target` diya hai. Aise **2 numbers** find karne hain jinka sum target ke equal ho. Return **unke indices**.

### Example

```text
Input:  nums = [2,7,11,15], target = 9
Output: [0,1]
Reason: 2 + 7 = 9
```

---

## 1️⃣ Brute Force Approach

### Idea

Har possible pair check karo.

### Java Code

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
        }

        return new int[]{};
    }
}
```

### Complexity

```text
Time  : O(n²)
Space : O(1)
```

### Dry Run

```text
nums = [2,7,11,15], target = 9

i = 0 → 2
j = 1 → 7
2 + 7 = 9 → Match → [0,1]
```

---

## 2️⃣ Better Approach — HashMap ⭐

### Main Idea

Current value ke liye required value:

```text
Complement = Target - Current
```

Example:

```text
Target  = 9
Current = 2
Complement = 7
```

Check karo ki complement map me pehle se hai ya nahi.

### Java Code

```java
import java.util.HashMap;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];

            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }

            map.put(nums[i], i);
        }

        return new int[]{};
    }
}
```

### Dry Run

```text
nums = [2,7,11,15], target = 9

Initially: {}

i = 0
Current = 2
Complement = 7
7 not found
Store 2 → 0

Map = {2 → 0}

 i = 1
Current = 7
Complement = 2
2 found at index 0

Return [0,1]
```

### Complexity

```text
Time  : O(n) average
Space : O(n)
```

---

## 3️⃣ Two Pointer Approach

### ⚠️ Important Interview Point

Ye approach **LeetCode 1 — Two Sum** ke original unsorted array + original indices requirement ke liye generally direct solution nahi hai.

Two Pointer approach tab appropriate hai jab:

- array already sorted ho
- jaise **Two Sum II — LeetCode 167**
- ya original indices ki requirement na ho / sorting-index mapping separately maintain ki jaye

### Idea

Sorted array me:

```text
left  → beginning
right → end
```

Rules:

```text
sum == target → answer
sum < target  → left++
sum > target  → right--
```

### Java Code — Two Sum II

```java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int left = 0;
        int right = numbers.length - 1;

        while (left < right) {
            int sum = numbers[left] + numbers[right];

            if (sum == target) {
                // Two Sum II uses 1-based indexing.
                return new int[]{left + 1, right + 1};
            }

            if (sum < target) {
                left++;
            } else {
                right--;
            }
        }

        return new int[]{};
    }
}
```

### Dry Run

```text
numbers = [2,7,11,15], target = 9

left = 0 → 2
right = 3 → 15
2 + 15 = 17 → too big → right--

2 + 11 = 13 → too big → right--

2 + 7 = 9 → Match

Return [1,2]
```

### Complexity

```text
Time  : O(n)
Space : O(1)
```

---

## 🎯 Interview Script

1. **Brute Force:** “Har possible pair check karenge. Time O(n²), Space O(1).”

2. **HashMap:** “Har current element ka complement `target - current` calculate karunga. Agar complement map me mil gaya to answer mil gaya, warna current value aur index store karunga. Time O(n) average aur Space O(n). Ye LeetCode 1 ka standard optimized solution hai.”

3. **Two Pointer:** “Agar array sorted hai, jaise Two Sum II, to left aur right pointer se O(n) time aur O(1) extra space me solve kar sakte hain.”

---

## 🚀 Revision Shortcut

| # | Approach | Key Idea | Time | Space |
|---|---|---|---|---|
| 1 | Brute Force | Check every pair | O(n²) | O(1) |
| 2 | HashMap ⭐ | `target - current` complement lookup | O(n) average | O(n) |
| 3 | Two Pointer | Sorted array + left/right pointers | O(n) | O(1) |

### Golden Rule

```text
LeetCode 1 — Two Sum
→ HashMap is the standard optimized approach.

LeetCode 167 — Two Sum II
→ Two Pointers is the canonical approach.
```
