# 925. Long Pressed Name — My Solution

## 📌 Approach

`typed` original `name` ka valid long-pressed version ho sakta hai, jahan existing character repeat ho sakta hai but order change nahi ho sakta.

### Better — Two Pointer
`i` → name, `j` → typed.

- Match → both pointers move
- Repeated previous typed char → only `j` moves
- Otherwise → invalid

### Best — Optimized Two Pointer ⭐
```java
class Solution {
    public boolean isLongPressedName(String name, String typed) {
        int i = 0, j = 0;

        while (j < typed.length()) {
            if (i < name.length() && name.charAt(i) == typed.charAt(j)) {
                i++;
                j++;
            } else if (j > 0 && typed.charAt(j) == typed.charAt(j - 1)) {
                j++;
            } else {
                return false;
            }
        }

        return i == name.length();
    }
}
```
Time `O(n+m)`, Space `O(1)`.

### Revision Shortcut
Match → both move. Mismatch + previous typed same → long press → only typed pointer moves. Else false.

Source: Notion solution. fileciteturn450file0