# 15. 3Sum — My Solution

## 📌 Problem

Given an integer array `nums`, find all unique triplets `[nums[i], nums[j], nums[k]]` such that:

```text
nums[i] + nums[j] + nums[k] == 0
```

### Example

```text
Input:  nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
```

---

## 1️⃣ Brute Force Approach

**Idea**

Har possible triplet check karo.

### Java Code

```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();

        for (int i = 0; i < nums.length - 2; i++) {
            for (int j = i + 1; j < nums.length - 1; j++) {
                for (int k = j + 1; k < nums.length; k++) {
                    if (nums[i] + nums[j] + nums[k] == 0) {
                        result.add(Arrays.asList(nums[i], nums[j], nums[k]));
                    }
                }
            }
        }

        return result;
    }
}
```

### Complexity

- **Time:** `O(n³)`
- **Space:** `O(k)` for output; auxiliary space `O(1)` apart from result

This brute-force version does not by itself remove duplicate triplets efficiently.

---

## 2️⃣ Best Approach — Sort + Two Pointers ⭐⭐⭐⭐⭐

### Idea

1. Array sort karo.
2. `i` ko fix karo.
3. `left = i + 1` and `right = n - 1` rakho.
4. Current sum check karo.
5. Sum `< 0` → `left++`.
6. Sum `> 0` → `right--`.
7. Sum `== 0` → triplet save karo and duplicates skip karo.

### Why sorting?

Sorting se:

- duplicate values easily skip kar sakte hain
- two-pointer movement possible hota hai
- sum ke according pointer direction decide hoti hai

### Java Code (interview-ready)

```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();

        Arrays.sort(nums);

        for (int i = 0; i < nums.length - 2; i++) {
            // Same fixed value ko dobara process mat karo.
            if (i > 0 && nums[i] == nums[i - 1]) {
                continue;
            }

            // Since array is sorted, if first value is already > 0,
            // all later values will also be > 0.
            if (nums[i] > 0) {
                break;
            }

            int left = i + 1;
            int right = nums.length - 1;

            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];

                if (sum == 0) {
                    result.add(Arrays.asList(
                            nums[i], nums[left], nums[right]
                    ));

                    // Duplicate left/right values skip karo.
                    while (left < right && nums[left] == nums[left + 1]) {
                        left++;
                    }

                    while (left < right && nums[right] == nums[right - 1]) {
                        right--;
                    }

                    left++;
                    right--;
                } else if (sum < 0) {
                    // Sum badhana hai.
                    left++;
                } else {
                    // Sum ghatana hai.
                    right--;
                }
            }
        }

        return result;
    }
}
```

### Complexity

- **Sorting:** `O(n log n)`
- **Two-pointer scan:** `O(n²)`
- **Overall Time:** `O(n²)`
- **Auxiliary Space:** `O(1)` excluding output; Java primitive-array sort uses implementation-dependent internal details

---

## 3️⃣ Dry Run

**Input:**

```text
nums = [-1, 0, 1, 2, -1, -4]
target = 0
```

After sorting:

```text
[-4, -1, -1, 0, 1, 2]
```

### `i = 0`

```text
fixed = -4
left = -1
right = 2
sum = -3
```

Sum negative hai → `left++`.

No valid triplet for this `i`.

### `i = 1`

```text
fixed = -1
left = -1
right = 2
sum = 0
```

Triplet:

```text
[-1, -1, 2]
```

Move both pointers and continue.

Next valid triplet:

```text
[-1, 0, 1]
```

### Final

```text
[[-1,-1,2],[-1,0,1]]
```

---

## 🎯 Interview Script

1. **"Brute force me 3 nested loops se har triplet check karenge. Iski Time Complexity O(n³) hai."**

2. **"Optimize karne ke liye array sort karenge. Fir ek element fix karke remaining array par Two Pointer use karenge."**

3. **"Agar sum target se chhota hai to left pointer badhayenge, aur agar bada hai to right pointer kam karenge."**

4. **"Duplicate triplets avoid karne ke liye fixed index aur left/right duplicate values skip karenge."**

5. **"Sorting O(n log n) hai, lekin two-pointer traversal O(n²) hai, so overall complexity O(n²) ho jaati hai."**

---

## 🚨 Most Important Interview Points

### Why `i > 0 && nums[i] == nums[i - 1]`?

Same fixed number se same triplets repeat ho sakte hain. Isliye duplicate `i` values skip karte hain.

### Why skip duplicate `left` and `right`?

Agar same boundary values repeat ho rahi hain, to same triplet dobara generate hoga.

### Why can we `break` when `nums[i] > 0`?

Array sorted hai. Agar fixed value positive hai, to `left` aur `right` bhi positive honge, so sum zero ho hi nahi sakta.

### Why two pointers work?

Sorted array me pointer movement sum ko predictably increase/decrease karta hai.

---

## 🚀 Revision Shortcut

| Approach | Key Idea | Time | Space |
|---|---|---:|---:|
| Brute Force | Check every triplet | O(n³) | O(1) auxiliary |
| Sort + Two Pointer ⭐ | Fix one + left/right scan | O(n²) | O(1) auxiliary |

---

## 🔗 Source

[Notion — 15. 3Sum — My Solution](https://app.notion.com/p/3a9b63f7c2ee8116b9e5dd738b43b972)
