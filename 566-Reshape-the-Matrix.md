>In MATLAB, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size but keep its original data.

>You're given a matrix represented by a two-dimensional array, and two positive integers r and c representing the row number and column number of the wanted reshaped matrix, respectively.

>The reshaped matrix need to be filled with all the elements of the original matrix in the same row-traversing order as they were.

>If the 'reshape' operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

# Example:
Input: 
nums = 
[[1,2],
 [3,4]]
r = 1, c = 4
Output: 
[[1,2,3,4]]
Explanation:
The row-traversing of nums is [1,2,3,4]. The new reshaped matrix is a 1 * 4 matrix, fill it row by row by using the previous list.

# Code
```
def matrixReshape(self, nums, r, c):
        """
        :type nums: List[List[int]]
        :type r: int
        :type c: int
        :rtype: List[List[int]]
        """                 
        h, w = len(nums), len(nums[0])
        if h * w != r * c: return nums
        ans = []
        p = q = 0
        for x in range(r):
            row = []
            for y in range(c):
                row.append(nums[p][q])
                q += 1
                if q == w:
                    p += 1
                    q = 0
            ans.append(row)
        return ans
```
