# 151. Reverse Words in a String — My Solution

## 📌 Approach

Words ka order reverse karna hai; leading, trailing aur multiple spaces ko normalize karna hai.

### 1️⃣ Brute Force
```java
class Solution {
  public String reverseWords(String s) {
    String[] words = s.trim().split("\\s+");
    StringBuilder result = new StringBuilder();

    for (int i = words.length - 1; i >= 0; i--) {
      result.append(words[i]);
      if (i != 0) {
        result.append(" ");
      }
    }
    return result.toString();
  }
}
```
**Time:** O(n)  
**Space:** O(n)

### 2️⃣ Two Pointer on Word Array ⭐
```java
class Solution {
  public String reverseWords(String s) {
    String[] words = s.trim().split("\\s+");
    int left = 0;
    int right = words.length - 1;

    while (left < right) {
      String temp = words[left];
      words[left] = words[right];
      words[right] = temp;
      left++;
      right--;
    }

    return String.join(" ", words);
  }
}
```
**Time:** O(n)  
**Space:** O(n) because of `split()` and output array.

### 🎯 Interview Line
> “After tokenizing the words, I reverse the word array using two pointers. The core pattern is left/right swapping, although the Java solution still uses O(n) space for tokenization.”
