- main topic: [[algo and ds]]
- [[review]]: get O(n)
- problem attributes
    - [[string & array]]
- solution attributes:
    - [[greedy]], [[one-pass]]
- ref: https://leetcode.com/problems/smallest-range-ii/discuss/174928/c%2B%2B-O(n)-time-solution!-Take-the-challenge!-With-very-very-detail-description-and-comments
- description:
    - Given an array A of integers, for each integer A[i] we need to choose **either x = -K or x = K**, and add x to A[i] **(only once)**.
    - After this process, we have some array B.
    - Return the smallest possible difference between the maximum value of B and the minimum value of B.
- Solution:
    - intuition: greedy
        - there is some index i where we should add for every elem on left (+ itself) and reduce for every elem on right
        - sort it to take advantage
        - one-pass: start with some assumed lower bound state, store max, min, and return val, updating based on iteration is O(1), after iterating through all, optimal value is secured
        - max difference will always be (max(A[-1]-K, A[i]+k) - min(A[0]+k, A[i+1]-k))
    - def smallestRangeII(self, A: List[int], K: int) -> int:
        A.sort()
        # base lower bound is existing biggest difference
        min_range = A[-1] - A[0]
        
        for idx in range(len(A)-1):  # when idx = len(A) - 1, 
                                ## that is base case + causes base case error
            mn = min(A[0]+K, A[idx+1]-K)
            mx = max(A[-1]-K, A[idx]+K)
            min_range = min(min_range, mx-mn)
        return min_range
- 
