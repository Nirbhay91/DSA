# 647. Palindromic Substrings — My Solution

## 📌 Approach

String me total palindromic substrings count karne hain.

### 1️⃣ Brute Force

Har possible substring check karo.

```java
class Solution {
  public int countSubstrings(String s) {
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
      for (int j = i; j < s.length(); j++) {
        if (isPalindrome(s, i, j)) {
          count++;
        }
      }
    }
    return count;
  }

  private boolean isPalindrome(String s, int left, int right) {
    while (left < right) {
      if (s.charAt(left) != s.charAt(right)) return false;
      left++;
      right--;
    }
    return true;
  }
}
```
**Time:** O(n³)  
**Space:** O(1)

### 2️⃣ Best — Expand Around Center ⭐

Har palindrome ke center se expand karo. Odd ke liye `(i,i)`, even ke liye `(i,i+1)`.

```java
class Solution {
  public int countSubstrings(String s) {
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
      count += expand(s, i, i);
      count += expand(s, i, i + 1);
    }
    return count;
  }

  private int expand(String s, int left, int right) {
    int count = 0;

    while (left >= 0 && right < s.length()
            && s.charAt(left) == s.charAt(right)) {
      count++;
      left--;
      right++;
    }
    return count;
  }
}
```
**Time:** O(n²)  
**Space:** O(1)

### 3️⃣ Dynamic Programming

`dp[i][j]` true hai agar `s[i..j]` palindrome hai.

**Time:** O(n²)  
**Space:** O(n²)

### 🎯 Interview Line
> “Every palindrome has a center. I expand around every odd and even center, and every successful expansion contributes one palindromic substring.”
