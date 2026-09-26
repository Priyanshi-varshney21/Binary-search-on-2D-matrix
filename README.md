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
