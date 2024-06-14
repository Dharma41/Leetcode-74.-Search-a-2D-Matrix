# Leetcode-74.-Search-a-2D-Matrix
You are given an m x n integer matrix matrix with the following two properties:  Each row is sorted in non-decreasing order. The first integer of each row is greater than the last integer of the previous row. Given an integer target, return true if target is in matrix or false otherwise.  You must write a solution in O(log(m * n)) time complexity.

Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Output: true

Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false



code:

class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int m= matrix.length;
        int n= matrix[0].length;
        int i=0;
        int j=n-1;
        while(i<=m-1 && j>=0){
            if(matrix[i][j]==target){
                return true;
            }else if(target>matrix[i][j]){
                i++;
            }else if(target<matrix[i][j]){
                j--;
            }
        }
       return false;     
    }
}
