# 986. Interval List Intersections — My Solution

## 📌 Approach

Dono interval lists sorted hain. Current intervals ka intersection:

`start = max(start1, start2)`
`end = min(end1, end2)`

Overlap tabhi hai jab `start <= end`.

### Brute Force
Har interval ko doosri list ke har interval se compare karo.

Time `O(n*m)`, Space `O(k)` for output.

### Best — Two Pointer ⭐
`i` → first list, `j` → second list. Har step overlap calculate karo aur jis interval ka end pehle finish hota hai, uska pointer move karo.

```java
class Solution {
    public int[][] intervalIntersection(int[][] firstList, int[][] secondList) {
        List<int[]> result = new ArrayList<>();
        int i = 0, j = 0;

        while (i < firstList.length && j < secondList.length) {
            int start = Math.max(firstList[i][0], secondList[j][0]);
            int end = Math.min(firstList[i][1], secondList[j][1]);

            if (start <= end) {
                result.add(new int[]{start, end});
            }

            if (firstList[i][1] < secondList[j][1]) {
                i++;
            } else {
                j++;
            }
        }

        return result.toArray(new int[result.size()][]);
    }
}
```
Time `O(n+m)`, Space `O(k)` for output.

### Golden Rule
Interval overlap → `max(start)` + `min(end)`. Pointer → move interval with smaller end.

Source: Notion solution. fileciteturn451file0