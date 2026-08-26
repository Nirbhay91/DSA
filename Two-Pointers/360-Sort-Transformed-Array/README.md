# 360. Sort Transformed Array — My Solution

> ⚠️ **Important:** The linked Notion page titled **360. Sort Transformed Array** currently contains the solution for **167. Two Sum II — Input Array Is Sorted**, not problem 360. The Notion content was preserved as-is rather than being mislabeled as a 360 solution. fileciteturn452file0

## Content currently available on the Notion page

The page provides three approaches for **167. Two Sum II**:

### 1. Brute Force
Check every pair.

Time `O(n²)`, Space `O(1)`.

### 2. Binary Search
Fix one value and binary-search its complement.

Time `O(n log n)`, Space `O(1)`.

### 3. Two Pointer ⭐
```java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int left = 0;
        int right = numbers.length - 1;

        while (left < right) {
            int sum = numbers[left] + numbers[right];

            if (sum == target) {
                return new int[]{left + 1, right + 1};
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }
        return new int[]{};
    }
}
```

Time `O(n)`, Space `O(1)`.

## Action Needed for Problem 360

For the actual **Sort Transformed Array** problem, the solution should use the quadratic transformation:

`f(x) = ax² + bx + c`

and exploit the fact that the parabola's extremum determines whether the largest or smallest transformed value comes from the ends. That actual 360 solution has not been copied because the provided Notion page contains a different problem's content.

Source: provided Notion page. fileciteturn452file0