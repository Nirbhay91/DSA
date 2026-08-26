# 844. Backspace String Compare — My Solution

## 📌 Approach

`#` previous character ko delete karta hai. Goal: final processed strings equal hain ya nahi.

### Brute Force
StringBuilder se dono strings process karke compare karo.

Time `O(n+m)`, Space `O(n+m)`.

### Better — Stack
Character push karo, `#` par pop karo.

Time `O(n+m)`, Space `O(n+m)`.

### Best — Two Pointer ⭐
End se traverse karo aur backspace ke liye `skip` counters maintain karo.

```java
class Solution {
    public boolean backspaceCompare(String s, String t) {
        int i = s.length() - 1;
        int j = t.length() - 1;
        int skipS = 0;
        int skipT = 0;

        while (i >= 0 || j >= 0) {
            while (i >= 0) {
                if (s.charAt(i) == '#') {
                    skipS++;
                    i--;
                } else if (skipS > 0) {
                    skipS--;
                    i--;
                } else {
                    break;
                }
            }

            while (j >= 0) {
                if (t.charAt(j) == '#') {
                    skipT++;
                    j--;
                } else if (skipT > 0) {
                    skipT--;
                    j--;
                } else {
                    break;
                }
            }

            if (i >= 0 && j >= 0 && s.charAt(i) != t.charAt(j)) {
                return false;
            }
            if ((i >= 0) != (j >= 0)) {
                return false;
            }

            i--;
            j--;
        }
        return true;
    }
}
```
Time `O(n+m)`, Space `O(1)`.

### Revision Shortcut
Backspace/delete → end se traverse → `#` par skip++ → normal char + skip > 0 ho to skip → valid chars compare.

Source: Notion solution. fileciteturn449file0