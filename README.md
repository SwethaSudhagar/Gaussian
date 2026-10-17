# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries, such as os, numpy, and sys.
2. Read the number of unknown variables from the user and store it in n.
3. Create a NumPy array of size n × (n+1) and initialize it with zeros to store the augmented matrix.
4. Create a NumPy array of size n and initialize it with zeros to store the solution vector.
5. Read the coefficients and constant values of the augmented matrix from the user.
6. Apply the Gauss Elimination Method to convert the augmented matrix into an upper triangular matrix.
7. Check whether the pivot element is zero. If it is zero, display the message "Divide by zero detected" and terminate the program.
8. Calculate the ratio and eliminate the elements below the pivot element.
9. Apply back substitution to calculate the values of the unknown variables.
10. Display the final solution of each variable using the print() statement.

## Program
# '''Program to solve a matrix using Gaussian elimination without partial pivoting.
# Developed by: swetha s
# RegisterNumber: 26012309
# '''
# import os
# os.environ["OPENBLAS_NUM_THREADS"]="1"
# import numpy as np
# import sys
#Reading number of unknowns
n = int(input())
#Making numpy array of n*n+1 size and initializing
#to zero for storing augmented matrix
a = np.zeros((n,n+1))
#Making numpy array of n size and initializing
#to zero for storing solution vector
x = np.zeros(n)
#Reading augmented matrix coefficients
for i in range(n):
  for j in range(n+1):
     a[i][j] = float(input())
# Applying Gauss Elimination 
for i in range(n):
  if a[i][i] == 0.0:
    sys.exit('Divide by zero detected!')
  for j in range(i+1, n):
   ratio = a[j][i]/a[i][i]
   for k in range(n+1):
    a[j][k] = a[j][k] - ratio*a[i][k]
# Back Substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
  x[i] = a[i][n]
  for j in range(i+1,n):
    x[i] = x[i] - a[i][j]*x[j]
  x[i] = x[i]/a[i][i]
# Displaying solution
for i in range(n):
  print('X%d = %0.2f' %(i,x[i]),
end=' ')

## Output:
<img width="836" height="711" alt="image" src="https://github.com/user-attachments/assets/2455edf6-41b3-4773-bd88-c239f0921de8" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

