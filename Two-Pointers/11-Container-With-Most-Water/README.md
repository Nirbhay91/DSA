# 11. Container With Most Water — My Solution

## 📌 Approach

**Problem**

Ek array `height[]` diya hai. Har index ek vertical line ko represent karta hai. Hume **aisi 2 lines choose karni hain jo maximum water hold kar sake.**

**Formula**

```text
Area = Width × Minimum Height
Area = (right - left) × min(height[left], height[right])
```

**Example**

```text
height = [1,8,6,2,5,4,8,3,7]
Output = 49
```

---

## 1️⃣ Brute Force Approach

**Idea**

Har possible pair of lines check karo.

```java
class Solution {
    public int maxArea(int[] height) {
        int maxArea = 0;
        for (int i = 0; i < height.length - 1; i++) {
            for (int j = i + 1; j < height.length; j++) {
                int width = j - i;
                int currentHeight = Math.min(height[i], height[j]);
                int currentArea = width * currentHeight;
                maxArea = Math.max(maxArea, currentArea);
            }
        }
        return maxArea;
    }
}
```

**Time:** O(n²)  
**Space:** O(1)

---

## 2️⃣ Best Approach — Two Pointer ⭐⭐⭐⭐⭐

### Main Observation

```text
Area = Width × Minimum Height
```

- `left` pointer start par.
- `right` pointer end par.
- Current area calculate karo.
- Maximum update karo.
- **Jiski height chhoti hai, us pointer ko move karo.**

### Java Code

```java
class Solution {
    public int maxArea(int[] height) {
        int left = 0;
        int right = height.length - 1;
        int maxArea = 0;

        while (left < right) {
            int area = Math.min(height[left], height[right]) * (right - left);
            maxArea = Math.max(maxArea, area);

            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }

        return maxArea;
    }
}
```

### Why smaller height move karte hain?

Current area minimum height se limited hai. Bigger-height side ko move karne par width kam hogi aur limiting height improve hone ka useful chance nahi milta. Smaller-height side move karne se new, taller limiting wall milne ka chance hota hai.

**Time:** O(n)  
**Space:** O(1)

---

## 🎯 Interview Script

> "Brute force me har possible pair check karte hain, isliye O(n²) time. Optimal Two Pointer approach me ek pointer start aur ek end par hota hai. Har step par area calculate karte hain aur smaller-height pointer ko move karte hain because area minimum height se limited hota hai. Isse O(n) time aur O(1) extra space milti hai."

---

## 🚀 Revision Shortcut

| # | Approach | Key Idea | Time | Space |
|---|---|---|---|---|
| 1 | Brute Force | Check every pair | O(n²) | O(1) |
| 2 | Two Pointer ⭐ | Move smaller-height pointer | O(n) | O(1) |

### 💡 Golden Rule

**Container problem + two ends → area calculate karo → smaller height ko move karo.**
