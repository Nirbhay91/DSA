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

**Steps**

- Do nested loops lagao.
- Har pair `(i, j)` ke liye area calculate karo.
- Maximum area update karte raho.

### Java Code (with line-by-line comments)

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

### Complexity

- **Time Complexity:** `O(n²)`
- **Space Complexity:** `O(1)`

---

## 2️⃣ Best Approach — Two Pointer ⭐⭐⭐⭐⭐

### Main Observation

```text
Area = Width × Minimum Height
```

Area do cheezon par depend karta hai:

- **Width** = `right - left`
- **Height** = `min(height[left], height[right])`

### Idea

- `left` pointer start par.
- `right` pointer end par.
- Har step par current area calculate karo.
- Maximum area update karo.
- Jis pointer ki height chhoti hai, usi ko move karo.

### Why smaller height move karte hain?

Suppose:

```text
left height  = 1
right height = 7
```

Current area `1 × width` se limited hai.

Agar bigger height (`7`) ko move karenge:

- width kam hogi
- limiting height `1` hi reh sakti hai
- area improve hone ka useful chance nahi hai

Agar smaller height (`1`) ko move karenge:

- width zaroor kam hogi
- lekin new position par larger height mil sakti hai
- isliye minimum height improve hone ka chance hai

### Java Code (with line-by-line comments)

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

### Dry Run

**Input:**

```text
height = [1,8,6,2,5,4,8,3,7]
```

- Step 1: `L=0 (1)`, `R=8 (7)` → area = `1 × 8 = 8` → max = `8` → smaller = `1` → `left++`
- Step 2: `L=1 (8)`, `R=8 (7)` → area = `7 × 7 = 49` → max = `49` → smaller = `7` → `right--`
- Remaining pointer movements continue in the same way.
- **Final Answer = `49`**

### Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

---

## 🎯 Interview Script

1. **"Sabse pehle brute force approach me har possible pair of lines check karenge. Har pair ke liye area calculate karke maximum track karenge. Is approach ki Time Complexity O(n²) aur Space Complexity O(1) hai."**

2. **"Optimal approach Two Pointer hai. Ek pointer start par aur ek end par rakhte hain. Har step par area calculate karte hain aur maximum update karte hain."**

3. **"Uske baad jis side ki height chhoti hoti hai us pointer ko move karte hain, kyunki area minimum height se limited hota hai. Bigger-height pointer ko move karne se width kam hogi, lekin limiting height improve hone ki guarantee nahi hogi."**

4. **"Is approach ki Time Complexity O(n) aur Space Complexity O(1) hai."**

---

## 🚀 Revision Shortcut

| # | Approach | Key Idea | Time | Space |
|---|---|---|---|---|
| 1 | Brute Force | Check every pair | O(n²) | O(1) |
| 2 | Two Pointer ⭐ | Move smaller-height pointer | O(n) | O(1) |

### 💡 Interview Tip

Agar interviewer puche **"Why do we move the smaller height pointer?"**, bolo:

> **"Current area ki limit smaller height hoti hai. Larger height ko move karne se width kam ho jayegi aur limiting height improve nahi hogi. Isliye smaller height ko move karte hain, taaki future me larger minimum height milne ka chance ho."**

---

## 🔗 Source

[Notion — 11. Container With Most Water — My Solution](https://app.notion.com/p/3a9b63f7c2ee8170b340d38e96abfda7)
