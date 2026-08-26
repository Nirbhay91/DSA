# 344. Reverse String — My Solution

## 📌 Approach

Ek character array `s[]` diya hai. Ise **in-place reverse** karna hai, extra array allowed nahi.

### 1️⃣ Brute Force
```java
class Solution {
  public void reverseString(char[] s) {
    char[] temp = new char[s.length];
    int count = 0;

    for (int i = s.length - 1; i >= 0; i--) {
      temp[count++] = s[i];
    }

    for (int i = 0; i < temp.length; i++) {
      s[i] = temp[i];
    }
  }
}
```
**Time:** O(n)  
**Space:** O(n)

### 2️⃣ Best — Two Pointer ⭐
```java
class Solution {
  public void reverseString(char[] s) {
    int left = 0;
    int right = s.length - 1;

    while (left < right) {
      char temp = s[left];
      s[left] = s[right];
      s[right] = temp;
      left++;
      right--;
    }
  }
}
```
**Time:** O(n)  
**Space:** O(1)

### 🎯 Interview Line
> “I use two pointers from both ends, swap the characters, and move inward. This gives O(n) time and O(1) extra space.”

### 🚀 Golden Rule
**Start + End se simultaneously kaam karna ho → Two Pointer socho.**
