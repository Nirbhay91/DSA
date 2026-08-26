# 125. Valid Palindrome — My Solution

## 📌 Approach

Sirf alphanumeric characters consider karo aur case ignore karke palindrome check karo.

### 1️⃣ Brute Force
```java
class Solution {
  public boolean isPalindrome(String s) {
    StringBuilder cleaned = new StringBuilder();
    for (char ch : s.toCharArray()) {
      if (Character.isLetterOrDigit(ch)) {
        cleaned.append(Character.toLowerCase(ch));
      }
    }
    String original = cleaned.toString();
    String reversed = cleaned.reverse().toString();
    return original.equals(reversed);
  }
}
```
**Time:** O(n)  
**Space:** O(n)

### 2️⃣ Best — Two Pointer ⭐
```java
class Solution {
  public boolean isPalindrome(String s) {
    int left = 0;
    int right = s.length() - 1;

    while (left < right) {
      while (left < right && !Character.isLetterOrDigit(s.charAt(left))) {
        left++;
      }
      while (left < right && !Character.isLetterOrDigit(s.charAt(right))) {
        right--;
      }

      if (Character.toLowerCase(s.charAt(left)) !=
          Character.toLowerCase(s.charAt(right))) {
        return false;
      }
      left++;
      right--;
    }
    return true;
  }
}
```
**Time:** O(n)  
**Space:** O(1)

### 🎯 Interview Line
> “I avoid creating a cleaned string. I move two pointers from both ends, skip non-alphanumeric characters, compare case-insensitively, and move inward.”
