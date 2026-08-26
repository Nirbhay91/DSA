# 5. Longest Palindromic Substring — My Solution

## 📌 Approach

Longest palindromic substring find karna hai.

### 1️⃣ Brute Force

Saare substrings generate karke palindrome check karo.

```java
class Solution {
  public String longestPalindrome(String s) {
    String longest = "";

    for (int i = 0; i < s.length(); i++) {
      for (int j = i; j < s.length(); j++) {
        String sub = s.substring(i, j + 1);
        if (isPalindrome(sub) && sub.length() > longest.length()) {
          longest = sub;
        }
      }
    }
    return longest;
  }

  private boolean isPalindrome(String str) {
    int left = 0;
    int right = str.length() - 1;
    while (left < right) {
      if (str.charAt(left) != str.charAt(right)) return false;
      left++;
      right--;
    }
    return true;
  }
}
```
**Time:** O(n³)  
**Space:** O(1) auxiliary (substring allocations can add cost)

### 2️⃣ Best — Expand Around Center ⭐

Odd palindrome ke liye `(i,i)` aur even palindrome ke liye `(i,i+1)` se expand karo.

```java
class Solution {
  public String longestPalindrome(String s) {
    int start = 0;
    int end = 0;

    for (int i = 0; i < s.length(); i++) {
      int len1 = expand(s, i, i);
      int len2 = expand(s, i, i + 1);
      int len = Math.max(len1, len2);

      if (len > end - start) {
        start = i - (len - 1) / 2;
        end = i + len / 2;
      }
    }
    return s.substring(start, end + 1);
  }

  private int expand(String s, int left, int right) {
    while (left >= 0 && right < s.length()
            && s.charAt(left) == s.charAt(right)) {
      left--;
      right++;
    }
    return right - left - 1;
  }
}
```
**Time:** O(n²)  
**Space:** O(1)

### 3️⃣ Dynamic Programming

`dp[i][j] = true` when `s[i..j]` is a palindrome.

**Time:** O(n²)  
**Space:** O(n²)

> Expand Around Center is the preferred interview solution. Manacher's Algorithm can achieve O(n), but is usually only needed for advanced algorithmic interviews.

### 🎯 Interview Line
> “Every palindrome has a center. I expand around every possible odd and even center, keeping the longest interval.”
