# DSA Practice — Pattern Wise

> Pattern-wise DSA sheet in **Problem | Difficulty | Concept | Solution** format. Existing problems are kept, duplicates are avoided within the pattern.

---

## 1. Two Pointers

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Two Sum II — Input Array Is Sorted | Medium | Two Pointers on sorted array | [Solution](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) |
| Container With Most Water | Medium | Two pointers from both ends | [Solution](https://leetcode.com/problems/container-with-most-water/) |
| 3Sum | Medium | Sorting + Two Pointers | [Solution](https://leetcode.com/problems/3sum/) |
| 3Sum Closest | Medium | Sorting + Two Pointers | [Solution](https://leetcode.com/problems/3sum-closest/) |
| 4Sum | Medium | Sorting + Two Pointers | [Solution](https://leetcode.com/problems/4sum/) |
| Remove Duplicates from Sorted Array | Easy | Slow/Fast Pointer | [Solution](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) |
| Remove Element | Easy | In-place Two Pointers | [Solution](https://leetcode.com/problems/remove-element/) |
| Remove Duplicates from Sorted Array II | Medium | Slow/Fast Pointer | [Solution](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/) |
| Merge Sorted Array | Easy | Reverse Two Pointers | [Solution](https://leetcode.com/problems/merge-sorted-array/) |
| Sort Colors | Medium | Dutch National Flag / Three Pointers | [Solution](https://leetcode.com/problems/sort-colors/) |
| Move Zeroes | Easy | In-place Two Pointers | [Solution](https://leetcode.com/problems/move-zeroes/) |
| Squares of a Sorted Array | Easy | Opposite-end Two Pointers | [Solution](https://leetcode.com/problems/squares-of-a-sorted-array/) |
| Trapping Rain Water | Hard | Two Pointers + Running Max | [Solution](https://leetcode.com/problems/trapping-rain-water/) |
| Valid Triangle Number | Medium | Sorting + Two Pointers | [Solution](https://leetcode.com/problems/valid-triangle-number/) |
| Backspace String Compare | Easy | Reverse Two Pointers | [Solution](https://leetcode.com/problems/backspace-string-compare/) |
| Long Pressed Name | Easy | Two Pointers | [Solution](https://leetcode.com/problems/long-pressed-name/) |
| Interval List Intersections | Medium | Two Pointers on Intervals | [Solution](https://leetcode.com/problems/interval-list-intersections/) |
| Sort Transformed Array | Medium | Two Pointers + Parabola Properties | [Solution](https://leetcode.com/problems/sort-transformed-array/) |
| Triplets with Smaller Sum | Medium | Sorting + Two Pointers | [Solution](https://www.geeksforgeeks.org/problems/count-triplets-with-sum-smaller-than-x5549/1) |
| Minimum Window Sort | Medium | Two Pointers + Boundary Expansion | [Solution](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/) |
| Subarrays with Product Less Than a Target | Medium | Sliding Window / Two Pointers | [Solution](https://leetcode.com/problems/subarray-product-less-than-k/) |

### Duplicate check

The following problems were duplicates of the existing pattern-wise list and are retained only once:

```text
Two Sum / Two Sum II → kept the correct Two Sum II variant for Two Pointers
3Sum
3Sum Closest
4Sum
Remove Duplicates from Sorted Array
Sort Colors
Squares of a Sorted Array
Backspace String Compare
Interval List Intersections
```

`Two Sum` itself is primarily a HashMap problem; `Two Sum II` is the canonical two-pointer version for a sorted array.

---

## 2. Fast & Slow Pointers

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Linked List Cycle | Easy | Fast & Slow Pointers | [Solution](https://leetcode.com/problems/linked-list-cycle/) |
| Start of Linked List Cycle | Medium | Fast & Slow Pointers | [Solution](https://leetcode.com/problems/linked-list-cycle-ii/) |
| Happy Number | Medium | Fast & Slow Pointers | [Solution](https://leetcode.com/problems/happy-number/) |
| Find Duplicate Number | Medium | Floyd Cycle Detection | [Solution](https://leetcode.com/problems/find-the-duplicate-number/) |
| Middle of the Linked List | Easy | Fast & Slow Pointers | [Solution](https://leetcode.com/problems/middle-of-the-linked-list/) |
| Palindrome Linked List | Medium | Fast & Slow + Reverse | [Solution](https://leetcode.com/problems/palindrome-linked-list/) |
| Reorder List | Medium | Fast & Slow + Reverse | [Solution](https://leetcode.com/problems/reorder-list/) |
| Circular Array Loop | Medium | Fast & Slow Pointers | [Solution](https://leetcode.com/problems/circular-array-loop/) |

## 3. Sliding Window

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Maximum Sum Subarray of Size K | Easy | Fixed Sliding Window | [Solution](https://www.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1) |
| Minimum Size Subarray Sum | Medium | Variable Sliding Window | [Solution](https://leetcode.com/problems/minimum-size-subarray-sum/) |
| Longest Substring with K Distinct Characters | Medium | Sliding Window + HashMap | [Solution](https://www.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1) |
| Fruit Into Baskets | Medium | Sliding Window + Frequency | [Solution](https://leetcode.com/problems/fruit-into-baskets/) |
| Longest Substring Without Repeating Characters | Medium | Sliding Window + HashSet/Map | [Solution](https://leetcode.com/problems/longest-substring-without-repeating-characters/) |
| Longest Repeating Character Replacement | Medium | Sliding Window + Frequency | [Solution](https://leetcode.com/problems/longest-repeating-character-replacement/) |
| Max Consecutive Ones III | Medium | Sliding Window | [Solution](https://leetcode.com/problems/max-consecutive-ones-iii/) |
| Minimum Window Substring | Hard | Sliding Window + Frequency | [Solution](https://leetcode.com/problems/minimum-window-substring/) |
| Permutation in String | Medium | Sliding Window + Frequency | [Solution](https://leetcode.com/problems/permutation-in-string/) |
| Find All Anagrams in a String | Medium | Sliding Window + Frequency | [Solution](https://leetcode.com/problems/find-all-anagrams-in-a-string/) |
| Substring with Concatenation of All Words | Hard | Sliding Window + Frequency Map | [Solution](https://leetcode.com/problems/substring-with-concatenation-of-all-words/) |

## 4. Kadane Pattern

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Maximum Subarray | Easy | Kadane | [Solution](https://leetcode.com/problems/maximum-subarray/) |
| Minimum Subarray Sum | Easy | Kadane Variant | [Solution](https://www.geeksforgeeks.org/problems/smallest-sum-contiguous-subarray/1) |
| Maximum Product Subarray | Medium | Kadane Variant | [Solution](https://leetcode.com/problems/maximum-product-subarray/) |
| Maximum Subarray Sum with One Deletion | Medium | DP / Kadane | [Solution](https://leetcode.com/problems/maximum-subarray-sum-with-one-deletion/) |
| Maximum Absolute Sum of Any Subarray | Medium | Kadane Variant | [Solution](https://leetcode.com/problems/maximum-absolute-sum-of-any-subarray/) |
| Maximum Sum Circular Subarray | Medium | Kadane + Circular Array | [Solution](https://leetcode.com/problems/maximum-sum-circular-subarray/) |

## 5. Prefix Sum

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Subarray Sum Equals K | Medium | Prefix Sum + HashMap | [Solution](https://leetcode.com/problems/subarray-sum-equals-k/) |
| Find Pivot Index | Easy | Prefix Sum | [Solution](https://leetcode.com/problems/find-pivot-index/) |
| Subarray Sums Divisible by K | Medium | Prefix Sum + Modulo | [Solution](https://leetcode.com/problems/subarray-sums-divisible-by-k/) |
| Contiguous Array | Medium | Prefix Sum + HashMap | [Solution](https://leetcode.com/problems/contiguous-array/) |
| Shortest Subarray with Sum at Least K | Hard | Prefix Sum + Monotonic Deque | [Solution](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/) |
| Count of Range Sum | Hard | Prefix Sum + Merge Sort / BIT | [Solution](https://leetcode.com/problems/count-of-range-sum/) |

## 6. Merge Intervals

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Merge Intervals | Medium | Sorting + Merge | [Solution](https://leetcode.com/problems/merge-intervals/) |
| Insert Interval | Medium | Interval Merge | [Solution](https://leetcode.com/problems/insert-interval/) |
| Interval List Intersections | Medium | Two Pointers on Intervals | [Solution](https://leetcode.com/problems/interval-list-intersections/) |
| Overlapping Intervals | Easy | Sorting + Interval Check | [Solution](https://www.geeksforgeeks.org/check-if-any-two-intervals-overlap-among-a-given-set-of-intervals/) |
| Minimum Meeting Rooms | Hard | Intervals + Heap | [Solution](https://www.geeksforgeeks.org/problems/attend-all-meetings-ii/1) |
| Maximum CPU Load | Hard | Intervals + Heap | [Solution](https://www.geeksforgeeks.org/maximum-cpu-load-from-the-given-list-of-jobs/) |
| Employee Free Time | Hard | Merge Intervals | [Solution](https://www.codertrain.co/employee-free-time) |

## 7. In-place Reversal of Linked List

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Reverse Linked List | Easy | In-place Reversal | [Solution](https://leetcode.com/problems/reverse-linked-list/) |
| Reverse Linked List II | Medium | In-place Reversal | [Solution](https://leetcode.com/problems/reverse-linked-list-ii/) |
| Swap Nodes in Pairs | Medium | In-place Reversal / Pointer Manipulation | [Solution](https://leetcode.com/problems/swap-nodes-in-pairs/) |
| Reverse Nodes in k-Group | Hard | In-place Reversal | [Solution](https://leetcode.com/problems/reverse-nodes-in-k-group/) |
| Reverse Nodes in Even Length Groups | Hard | In-place Reversal | [Solution](https://leetcode.com/problems/reverse-nodes-in-even-length-groups/) |
| Rotate List | Medium | Linked List + Reversal | [Solution](https://leetcode.com/problems/rotate-list/) |

## 8. Stack

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Remove All Adjacent Duplicates in String | Easy | Stack | [Solution](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/) |
| Valid Parentheses | Easy | Stack | [Solution](https://leetcode.com/problems/valid-parentheses/) |
| Next Greater Element II | Medium | Monotonic Stack | [Solution](https://leetcode.com/problems/next-greater-element-ii/) |
| Daily Temperatures | Medium | Monotonic Stack | [Solution](https://leetcode.com/problems/daily-temperatures/) |
| Remove Nodes From Linked List | Medium | Stack | [Solution](https://leetcode.com/problems/remove-nodes-from-linked-list/) |
| Remove All Adjacent Duplicates in String II | Medium | Stack | [Solution](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string-ii/) |
| Simplify Path | Medium | Stack | [Solution](https://leetcode.com/problems/simplify-path/) |
| Remove K Digits | Hard | Monotonic Stack | [Solution](https://leetcode.com/problems/remove-k-digits/) |

## 9. Hash Maps

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| First Unique Character in a String | Easy | HashMap / Frequency | [Solution](https://leetcode.com/problems/first-unique-character-in-a-string/) |
| Maximum Number of Balloons | Easy | HashMap / Frequency | [Solution](https://leetcode.com/problems/maximum-number-of-balloons/) |
| Longest Palindrome | Easy | HashMap / Frequency | [Solution](https://leetcode.com/problems/longest-palindrome/) |
| Ransom Note | Easy | HashMap / Frequency | [Solution](https://leetcode.com/problems/ransom-note/) |

## 10. Binary Search

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Binary Search | Easy | Binary Search | [Solution](https://leetcode.com/problems/binary-search/) |
| Ceiling in a Sorted Array | Easy | Binary Search | [Solution](https://www.geeksforgeeks.org/problems/ceil-in-a-sorted-array/1) |
| Find First and Last Position of Element in Sorted Array | Medium | Binary Search | [Solution](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) |
| Number of Occurrences | Easy | Binary Search | [Solution](https://www.geeksforgeeks.org/problems/number-of-occurrence2259/1) |
| Search in Infinite Sorted Array | Medium | Exponential + Binary Search | [Solution](https://www.geeksforgeeks.org/find-position-element-sorted-array-infinite-numbers/) |
| Peak Index in a Mountain Array | Medium | Binary Search | [Solution](https://leetcode.com/problems/peak-index-in-a-mountain-array/) |
| Find Peak Element | Medium | Binary Search | [Solution](https://leetcode.com/problems/find-peak-element/) |
| Find Minimum in Rotated Sorted Array | Medium | Binary Search | [Solution](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) |
| Number of Rotations | Medium | Binary Search | [Solution](https://www.geeksforgeeks.org/problems/rotation4723/1) |
| Search in Rotated Sorted Array | Medium | Binary Search | [Solution](https://leetcode.com/problems/search-in-rotated-sorted-array/) |
| Koko Eating Bananas | Medium | Binary Search on Answer | [Solution](https://leetcode.com/problems/koko-eating-bananas/) |
| Minimum Number of Days to Make m Bouquets | Medium | Binary Search on Answer | [Solution](https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/) |
| Aggressive Cows | Medium | Binary Search on Answer | [Solution](https://www.geeksforgeeks.org/problems/aggressive-cows/1) |
| H-Index II | Medium | Binary Search | [Solution](https://leetcode.com/problems/h-index-ii/) |
| Maximum Candies Allocated to K Children | Medium | Binary Search on Answer | [Solution](https://leetcode.com/problems/maximum-candies-allocated-to-k-children/) |
| Capacity To Ship Packages Within D Days | Medium | Binary Search on Answer | [Solution](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) |
| Allocate Minimum Number of Pages | Hard | Binary Search on Answer | [Solution](https://www.geeksforgeeks.org/problems/allocate-minimum-number-of-pages0937/1) |
| Split Array Largest Sum | Hard | Binary Search on Answer | [Solution](https://leetcode.com/problems/split-array-largest-sum/) |
| Search a 2D Matrix | Medium | Binary Search | [Solution](https://leetcode.com/problems/search-a-2d-matrix/) |
| Search a 2D Matrix II | Medium | Matrix Search | [Solution](https://leetcode.com/problems/search-a-2d-matrix-ii/) |
| Kth Smallest Element in a Sorted Matrix | Hard | Binary Search on Value | [Solution](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/) |
| Kth Smallest Number in Multiplication Table | Hard | Binary Search on Value | [Solution](https://leetcode.com/problems/kth-smallest-number-in-multiplication-table/) |
| Median of Two Sorted Arrays | Hard | Binary Search + Partition | [Solution](https://leetcode.com/problems/median-of-two-sorted-arrays/) |

## 11. Heap / Priority Queue

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Kth Smallest Element | Medium | Min Heap / Max Heap | [Solution](https://www.geeksforgeeks.org/problems/kth-smallest-element5635/1) |
| Kth Largest Element in an Array | Medium | Heap / Top K | [Solution](https://leetcode.com/problems/kth-largest-element-in-an-array/) |
| Top K Frequent Elements | Medium | HashMap + Heap | [Solution](https://leetcode.com/problems/top-k-frequent-elements/) |
| Top K Frequent Words | Medium | HashMap + Heap | [Solution](https://leetcode.com/problems/top-k-frequent-words/) |
| K Closest Points to Origin | Medium | Heap / Top K | [Solution](https://leetcode.com/problems/k-closest-points-to-origin/) |
| Find K Closest Elements | Medium | Heap / Binary Search | [Solution](https://leetcode.com/problems/find-k-closest-elements/) |
| The K Weakest Rows in a Matrix | Easy | Heap | [Solution](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/) |
| Merge K Sorted Arrays | Hard | Min Heap | [Solution](https://www.geeksforgeeks.org/problems/merge-k-sorted-arrays/1) |
| Kth Smallest Element in a Sorted Matrix | Hard | Heap / Binary Search | [Solution](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/) |
| Last Stone Weight | Easy | Max Heap | [Solution](https://leetcode.com/problems/last-stone-weight/) |
| Task Scheduler | Medium | Greedy + Heap | [Solution](https://leetcode.com/problems/task-scheduler/) |
| Reorganize String | Medium | Greedy + Heap | [Solution](https://leetcode.com/problems/reorganize-string/) |
| Minimum Number of Refueling Stops | Hard | Greedy + Max Heap | [Solution](https://leetcode.com/problems/minimum-number-of-refueling-stops/) |
| IPO | Hard | Greedy + Heap | [Solution](https://leetcode.com/problems/ipo/) |
| Course Schedule III | Hard | Greedy + Heap | [Solution](https://leetcode.com/problems/course-schedule-iii/) |
| Find Median from Data Stream | Hard | Two Heaps | [Solution](https://leetcode.com/problems/find-median-from-data-stream/) |
| Sliding Window Median | Hard | Two Heaps | [Solution](https://leetcode.com/problems/sliding-window-median/) |

## 12. Recursion / Backtracking

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Subsets | Medium | Backtracking | [Solution](https://leetcode.com/problems/subsets/) |
| Permutations | Medium | Backtracking | [Solution](https://leetcode.com/problems/permutations/) |
| Combination Sum | Medium | Backtracking | [Solution](https://leetcode.com/problems/combination-sum/) |
| Generate Parentheses | Medium | Backtracking | [Solution](https://leetcode.com/problems/generate-parentheses/) |
| Letter Combinations of a Phone Number | Medium | Backtracking | [Solution](https://leetcode.com/problems/letter-combinations-of-a-phone-number/) |
| N-Queens | Hard | Backtracking | [Solution](https://leetcode.com/problems/n-queens/) |

## 13. Trees — Traversal

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Binary Tree Preorder Traversal | Easy | DFS | [Solution](https://leetcode.com/problems/binary-tree-preorder-traversal/) |
| Binary Tree Inorder Traversal | Easy | DFS | [Solution](https://leetcode.com/problems/binary-tree-inorder-traversal/) |
| Binary Tree Postorder Traversal | Easy | DFS | [Solution](https://leetcode.com/problems/binary-tree-postorder-traversal/) |
| Binary Tree Level Order Traversal | Medium | BFS | [Solution](https://leetcode.com/problems/binary-tree-level-order-traversal/) |
| Zigzag Level Order Traversal | Medium | BFS | [Solution](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/) |
| Right Side View | Medium | BFS / DFS | [Solution](https://leetcode.com/problems/binary-tree-right-side-view/) |

## 14. Trees — Mirror / Symmetry

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Invert Binary Tree | Easy | DFS / Tree Transformation | [Solution](https://leetcode.com/problems/invert-binary-tree/) |
| Symmetric Tree | Easy | DFS / BFS | [Solution](https://leetcode.com/problems/symmetric-tree/) |
| Same Tree | Easy | DFS | [Solution](https://leetcode.com/problems/same-tree/) |
| Subtree of Another Tree | Easy | DFS | [Solution](https://leetcode.com/problems/subtree-of-another-tree/) |
| Flip Equivalent Binary Trees | Medium | DFS | [Solution](https://leetcode.com/problems/flip-equivalent-binary-trees/) |

## 15. Trees — Search / BST

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Lowest Common Ancestor of a Binary Tree | Medium | DFS | [Solution](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) |
| Search in a Binary Search Tree | Easy | BST Search | [Solution](https://leetcode.com/problems/search-in-a-binary-search-tree/) |
| Lowest Common Ancestor of a BST | Easy | BST Property | [Solution](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) |
| Lowest Common Ancestor of Deepest Leaves | Medium | DFS | [Solution](https://leetcode.com/problems/lowest-common-ancestor-of-deepest-leaves/) |
| Two Sum IV — Input Is a BST | Easy | BST + HashSet | [Solution](https://leetcode.com/problems/two-sum-iv-input-is-a-bst/) |
| Kth Smallest Element in a BST | Medium | Inorder / BST | [Solution](https://leetcode.com/problems/kth-smallest-element-in-a-bst/) |

## 16. Trees — Validation / Path / Construction

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Minimum Depth of Binary Tree | Easy | BFS / DFS | [Solution](https://leetcode.com/problems/minimum-depth-of-binary-tree/) |
| Maximum Depth of Binary Tree | Easy | DFS | [Solution](https://leetcode.com/problems/maximum-depth-of-binary-tree/) |
| Balanced Binary Tree | Easy | DFS | [Solution](https://leetcode.com/problems/balanced-binary-tree/) |
| Diameter of Binary Tree | Easy | DFS + Height | [Solution](https://leetcode.com/problems/diameter-of-binary-tree/) |
| Check Completeness of a Binary Tree | Medium | BFS | [Solution](https://leetcode.com/problems/check-completeness-of-a-binary-tree/) |
| Validate Binary Search Tree | Medium | DFS + Bounds | [Solution](https://leetcode.com/problems/validate-binary-search-tree/) |
| Recover Binary Search Tree | Medium | Inorder | [Solution](https://leetcode.com/problems/recover-binary-search-tree/) |
| Path Sum | Easy | DFS | [Solution](https://leetcode.com/problems/path-sum/) |
| Path Sum II | Medium | DFS + Backtracking | [Solution](https://leetcode.com/problems/path-sum-ii/) |
| Sum Root to Leaf Numbers | Medium | DFS | [Solution](https://leetcode.com/problems/sum-root-to-leaf-numbers/) |
| Binary Tree Maximum Path Sum | Hard | DFS + DP | [Solution](https://leetcode.com/problems/binary-tree-maximum-path-sum/) |
| Construct Binary Tree from Preorder and Inorder Traversal | Medium | Recursion + HashMap | [Solution](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) |
| Construct Binary Tree from Inorder and Postorder Traversal | Medium | Recursion + HashMap | [Solution](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/) |
| Convert Sorted Array to Binary Search Tree | Easy | Divide & Conquer | [Solution](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/) |

## 17. Graphs

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Construct Adjacency List from Edges + Nodes | Easy | Graph Representation | [Solution](https://www.geeksforgeeks.org/problems/print-adjacency-list-1587115620/1) |
| Graph DFS | Easy | DFS | [Solution](https://www.geeksforgeeks.org/problems/depth-first-traversal-for-a-graph/1) |
| Graph BFS | Easy | BFS | [Solution](https://www.geeksforgeeks.org/problems/bfs-traversal-of-graph/1) |
| Number of Islands | Medium | DFS / BFS | [Solution](https://leetcode.com/problems/number-of-islands/) |
| Number of Provinces | Medium | DFS / BFS / DSU | [Solution](https://leetcode.com/problems/number-of-provinces/) |
| Rotting Oranges | Medium | Multi-source BFS | [Solution](https://leetcode.com/problems/rotting-oranges/) |
| Cycle Detection in Undirected Graph | Medium | DFS / BFS / DSU | [Solution](https://www.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1) |
| Cycle Detection in Directed Graph | Medium | DFS / Topological Sort | [Solution](https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1) |
| Topological Sort | Medium | Topological Sort | [Solution](https://www.geeksforgeeks.org/problems/topological-sort/1) |
| Is Graph Bipartite? | Medium | BFS / DFS Coloring | [Solution](https://leetcode.com/problems/is-graph-bipartite/) |
| Surrounded Regions | Medium | DFS / BFS | [Solution](https://leetcode.com/problems/surrounded-regions/) |
| Shortest Path in Undirected Graph with Unit Distance | Medium | BFS | [Solution](https://www.geeksforgeeks.org/problems/shortest-path-in-undirected-graph-having-unit-distance/1) |
| Dijkstra's Algorithm | Medium | Dijkstra / Min Heap | [Solution](https://www.geeksforgeeks.org/problems/implementing-dijkstra-set-1-adjacency-matrix/1) |
| Network Delay Time | Medium | Dijkstra | [Solution](https://leetcode.com/problems/network-delay-time/) |
| Path With Minimum Effort | Medium | Dijkstra / Binary Search | [Solution](https://leetcode.com/problems/path-with-minimum-effort/) |
| Swim in Rising Water | Hard | Dijkstra / Binary Search | [Solution](https://leetcode.com/problems/swim-in-rising-water/) |
| Bellman-Ford | Medium | Bellman-Ford | [Solution](https://www.geeksforgeeks.org/problems/distance-from-the-source-bellman-ford-algorithm/1) |
| Cheapest Flights Within K Stops | Medium | Bellman-Ford Variant / DP | [Solution](https://leetcode.com/problems/cheapest-flights-within-k-stops/) |
| Prim MST | Medium | Minimum Spanning Tree | [Solution](https://www.geeksforgeeks.org/problems/minimum-spanning-tree/1) |
| Word Ladder | Hard | BFS | [Solution](https://leetcode.com/problems/word-ladder/) |

## 18. Dynamic Programming

| Problem | Difficulty | Concept | Solution |
|---|---|---|---|
| Fibonacci Number | Easy | 1D DP | [Solution](https://leetcode.com/problems/fibonacci-number/) |
| Climbing Stairs | Easy | 1D DP | [Solution](https://leetcode.com/problems/climbing-stairs/) |
| House Robber | Medium | 1D DP | [Solution](https://leetcode.com/problems/house-robber/) |
| 0/1 Knapsack | Medium | DP / Knapsack | [Solution](https://www.geeksforgeeks.org/problems/0-1-knapsack-problem0945/1) |
| Subset Sum | Medium | DP / Knapsack | [Solution](https://www.geeksforgeeks.org/problems/subset-sum-problem-1611555638/1) |
| Target Sum | Medium | DP / Knapsack | [Solution](https://www.geeksforgeeks.org/problems/target-sum-1626326450/1) |
| Longest Increasing Subsequence | Medium | DP / LIS | [Solution](https://leetcode.com/problems/longest-increasing-subsequence/) |
| Longest Common Subsequence | Medium | DP / LCS | [Solution](https://leetcode.com/problems/longest-common-subsequence/) |
| Unique Paths | Medium | Grid DP | [Solution](https://leetcode.com/problems/unique-paths/) |
| Best Time to Buy and Sell Stock | Easy | DP / Greedy | [Solution](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) |
| Best Time to Buy and Sell Stock II | Medium | DP / Greedy | [Solution](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/) |
| Best Time to Buy and Sell Stock III | Hard | DP / State Machine | [Solution](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/) |
| Best Time to Buy and Sell Stock IV | Hard | DP / State Machine | [Solution](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv/) |
| Minimum Cost to Cut a Stick | Hard | Interval DP | [Solution](https://leetcode.com/problems/minimum-cost-to-cut-a-stick/) |

---

## 🔥 Interview Revision Order

```text
Two Pointers
→ Fast & Slow
→ Sliding Window
→ Prefix Sum
→ Kadane
→ Merge Intervals
→ Linked List
→ Stack
→ HashMap
→ Binary Search
→ Heap
→ Recursion / Backtracking
→ Trees
→ Graphs
→ Dynamic Programming
```
