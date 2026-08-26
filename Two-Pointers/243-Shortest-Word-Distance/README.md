# 243. Shortest Word Distance — My Solution

> ⚠️ The supplied Notion page is currently empty and says it should be filled with the 243 solution. I am not inventing/copying a different solution into this folder. fileciteturn470file0

## Expected Two-Pointer Pattern

Given a list of words and two target words, track the latest index of each target while scanning once. When both have been seen, update the minimum absolute distance.

### Java Code

```java
class Solution {
    public int shortestDistance(String[] wordsDict, String word1, String word2) {
        int index1 = -1;
        int index2 = -1;
        int minDistance = Integer.MAX_VALUE;

        for (int i = 0; i < wordsDict.length; i++) {
            if (wordsDict[i].equals(word1)) {
                index1 = i;
            }

            if (wordsDict[i].equals(word2)) {
                index2 = i;
            }

            if (index1 != -1 && index2 != -1) {
                minDistance = Math.min(minDistance, Math.abs(index1 - index2));
            }
        }

        return minDistance;
    }
}
```

**Time:** O(n)  
**Space:** O(1)

### 🎯 Interview Line

> “I keep the latest position of both target words and update the minimum distance whenever both positions are available. This gives a single O(n) pass and O(1) extra space.”
