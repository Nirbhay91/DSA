# 16. 3Sum Closest — My Solution

## 📌 Approach — 3Sum Closest

Given an array `nums` and a `target`, find three integers whose sum is closest to the target.

### Example

```text
Input: nums = [-1, 2, 1, -4], target = 1
Output: 2
```

---

## Step 1 — Clarify the Problem 🎤

Interview me pehle clarify karo:

- Array me duplicate values ho sakti hain? **Yes**
- At least 3 elements hain? **Yes**
- Equal-distance tie ka rule? Problem constraints ke according unique answer assumed.

---

## 1️⃣ Brute Force Approach

### Idea

3 nested loops se har possible triplet check karo. Har triplet ka sum calculate karke target se absolute difference compare karo.

### Java Code

```java
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        int minDifference = Integer.MAX_VALUE;
        int closestSum = 0;

        for (int i = 0; i < nums.length - 2; i++) {
            for (int j = i + 1; j < nums.length - 1; j++) {
                for (int k = j + 1; k < nums.length; k++) {
                    int sum = nums[i] + nums[j] + nums[k];
                    int difference = Math.abs(target - sum);

                    if (difference < minDifference) {
                        minDifference = difference;
                        closestSum = sum;
                    }
                }
            }
        }

        return closestSum;
    }
}
```

### Complexity

- **Time:** `O(n³)`
- **Space:** `O(1)` auxiliary

---

## 2️⃣ Best Approach — Sort + Two Pointers ⭐⭐⭐⭐⭐

### Idea

1. Array sort karo.
2. Ek element `i` par fix karo.
3. `left = i + 1` and `right = n - 1`.
4. Current triplet sum calculate karo.
5. Closest answer update karo.
6. `sum < target` → `left++`.
7. `sum > target` → `right--`.
8. `sum == target` → exact answer, immediately return.

### Why it works?

Sorting ke baad:

```text
sum < target
    ↓
left badhao
    ↓
sum increase karne ka chance
```

and:

```text
sum > target
    ↓
right kam karo
    ↓
sum decrease karne ka chance
```

### Java Code — Interview Ready

```java
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);

        int closestSum = nums[0] + nums[1] + nums[2];

        for (int i = 0; i < nums.length - 2; i++) {
            int left = i + 1;
            int right = nums.length - 1;

            while (left < right) {
                int currentSum = nums[i] + nums[left] + nums[right];

                // Exact target mil gaya -> best possible answer.
                if (currentSum == target) {
                    return currentSum;
                }

                // Current sum target ke aur paas hai?
                if (Math.abs(target - currentSum)
                        < Math.abs(target - closestSum)) {
                    closestSum = currentSum;
                }

                // Sum ko target ki taraf move karo.
                if (currentSum < target) {
                    left++;
                } else {
                    right--;
                }
            }
        }

        return closestSum;
    }
}
```

### Complexity

- Sorting: `O(n log n)`
- Outer loop + Two Pointer: `O(n²)`
- **Overall Time:** `O(n²)`
- **Auxiliary Space:** `O(1)` excluding sorting implementation details / output

---

## 3️⃣ Dry Run 🔍

**Input**

```text
nums = [-1, 2, 1, -4]
target = 1
```

### Step 1 — Sort

```text
[-4, -1, 1, 2]
```

### `i = 0`

```text
fixed = -4
left = -1
right = 2
sum = -3
```

Difference:

```text
|1 - (-3)| = 4
```

Since:

```text
-3 < 1
```

increase sum → `left++`.

### Next

```text
fixed = -4
left = 1
right = 2
sum = -1
```

Again sum is smaller than target → `left++`.

Continue until all `i` values are processed.

For this input the final answer is:

```text
2
```

---

## 🎯 Interview Script

1. **"Brute force me 3 nested loops se har possible triplet check karunga. Time O(n³), Space O(1)."**

2. **"Optimize karne ke liye array sort karunga, ek number fix karunga aur baaki range par Two Pointer use karunga."**

3. **"Current sum target se chhota hai to left++ karke sum increase karne ki koshish karunga, aur agar bada hai to right-- karke sum decrease karunga."**

4. **"Har iteration par target ke saath absolute difference compare karke closest sum maintain karunga."**

5. **"Exact target mil gaya to immediately return kar sakte hain because usse better answer possible nahi hai."**

6. **"Overall complexity O(n²) hai."**

---

## 🚨 Important Interview Points

### Why sort?

Two Pointer ko predictable movement chahiye. Sorted array me left increase karne se value non-decreasing hoti hai aur right decrease karne se value non-increasing hoti hai.

### Why `Math.abs(target - currentSum)`?

"Closest" ka matlab minimum absolute difference:

```text
|target - sum|
```

### Why immediate return on exact target?

Agar:

```text
currentSum == target
```

then absolute difference `0` hai, jo minimum possible hai.

### Brute Force vs Optimized

```text
Brute Force  → O(n³)
Sort + 2P    → O(n²)
```

---

## 🚀 Revision Shortcut

| Approach | Key Idea | Time | Space |
|---|---|---:|---:|
| Brute Force | Check every triplet | O(n³) | O(1) auxiliary |
| Sort + Two Pointer ⭐ | Fix one + move left/right toward target | O(n²) | O(1) auxiliary |

---

## 🔗 Source

[Notion — 16. 3Sum Closest — My Solution](https://app.notion.com/p/3a9b63f7c2ee81c98a75f1b45e47db2b)
