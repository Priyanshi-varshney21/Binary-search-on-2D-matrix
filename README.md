# Binary-search-on-2D-matrix
# TRAVESRE A MATRIX
mat= [[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12], [13, 14, 15, 16]]
for i in range(len(mat)):
  for j in range(len(mat[0])):
    print(mat[i][j],end=" ")
  print()

# FIND ROW WITH MAXIMUM NO OF 1'S
def rowWithMax1s(self, matrix):
        max_ones=0
        row=-1
        for i in range(len(matrix)):
            low=0
            high=len(matrix[0])-1
            while low<=high:
                mid=low+(high-low)//2
                if matrix[i][mid]==1:
                    high=mid-1
                else:
                    low=mid+1
            ones=len(matrix[i])-low
            if ones>max_ones:
                max_ones=ones
                row=i
        return row

# SEARCH IN A 2-D MATRIX
def searchMatrix(self, matrix, target):
        for i in range(len(matrix)):
            low=0
            high=len(matrix[i])-1
            while low<=high:
                mid=low+(high-low)//2
                if matrix[i][mid]==target:
                    return True
                elif target>matrix[i][mid]:
                    low=mid+1
                else:
                    high=mid-1
        return False

# FIND PEAK ELEMENT
def findPeakGrid(self, mat):
        low=0
        high=len(mat)-1
        while low<=high:
            mid=low+(high-low)//2
            col = 0
            for j in range(len(mat[0])):
                if mat[mid][j] > mat[mid][col]:
                    col = j
        # if element below is bigger
            if mid + 1 < len(mat) and mat[mid + 1][col] > mat[mid][col]:
                low = mid + 1
            else:
                 high = mid - 1
        return [low, col]
