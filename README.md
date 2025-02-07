# Daily-Leetcode-Problem1
PROBLEM

You are given an integer limit and a 2D array queries of size n x 2.
There are limit + 1 balls with distinct labels in the range [0, limit]. Initially, all balls are uncolored. For every query in queries that is of the form [x, y], you mark ball x with the color y. After each query, you need to find the number of distinct colors among the balls.
Return an array result of length n, where result[i] denotes the number of distinct colors after ith query.
Note that when answering a query, lack of a color will not be considered as a color.

Intuition

An unordered_map to keep track of colors and an unordered_set to maintain distinct colors efficiently

Approach

Data Structures Used:
unordered_map<int, int> ballColor: Stores the color of each ball.
unordered_set distinctColors: Keeps track of unique colors.
Processing Each Query:
If a ball already has a color and is being recolored, check if the old color still exists elsewhere.
If the old color is unique to that ball, remove it from distinctColors.
Assign the new color and add it to distinctColors.
Store the count of distinct colors in the result array.

Complexity

Time complexity:
Each query takes O(1) on average due to unordered_map and unordered_set operations.
Checking if a previous color still exists takes O(limit) worst case but is efficient in practice.
Overall complexity: O(n * limit) in the worst case, but typically O(n)

Space complexity:
O(limit)

 
