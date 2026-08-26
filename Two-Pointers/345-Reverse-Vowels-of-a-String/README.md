# 345. Reverse Vowels of a String — My Solution

## 📌 Approach

Sirf vowels (`a,e,i,o,u`) ki positions reverse karni hain; baaki characters same rahenge.

### 1️⃣ Brute Force
```java
class Solution {
  public String reverseVowels(String s) {
    String vowels = "aeiouAEIOU";
    List<Character> vowelList = new ArrayList<>();

    for (char ch : s.toCharArray()) {
      if (vowels.indexOf(ch) != -1) {
        vowelList.add(ch);
      }
    }

    char[] arr = s.toCharArray();
    int index = vowelList.size() - 1;

    for (int i = 0; i < arr.length; i++) {
      if (vowels.indexOf(arr[i]) != -1) {
        arr[i] = vowelList.get(index--);
      }
    }
    return new String(arr);
  }
}
```
**Time:** O(n)  
**Space:** O(n)

### 2️⃣ Best — Two Pointer ⭐
```java
class Solution {
  public String reverseVowels(String s) {
    char[] arr = s.toCharArray();
    int left = 0;
    int right = arr.length - 1;

    while (left < right) {
      while (left < right && !isVowel(arr[left])) {
        left++;
      }
      while (left < right && !isVowel(arr[right])) {
        right--;
      }

      char temp = arr[left];
      arr[left] = arr[right];
      arr[right] = temp;
      left++;
      right--;
    }
    return new String(arr);
  }

  private boolean isVowel(char ch) {
    return "aeiouAEIOU".indexOf(ch) >= 0;
  }
}
```
**Time:** O(n)  
**Space:** O(1) extra

### 🎯 Interview Line
> “Move two pointers inward until both point to vowels, swap them, and continue. Non-vowels are simply skipped.”
