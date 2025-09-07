# Programming-Assignment-2

## 1. Normalization Problem 
This function works by first creating a random 5x5 array using NumPy, then normalizing its values. Normalization is done by subtracting the mean and dividing by the standard deviation of the dataset. The result is saved in _.npy_ format.

   **Code**

     import numpy as np # import the NumPy library with the 'np'

     X = np.random.rand (5, 5) # create a 5x5 array filled with random float numbers between 0 and 1
     print ("Original array X:") # label and print to indicate the original (unnormalized) array
     print (X) # print the contents of the array X

     X_normalized = (X - X.mean()) / X.std() # normalize X using the formula Z = (X - mean) / std
     print("\nNormalized array X:") # label and print to indicate that the contents are the Normalized Array
     print(X_normalized) # print the array

     np.save('X_normalized.npy', X_normalized) # save the normalized array with the file name X_normalized.npy
     print("\nNormalized array saved as 'X_normalized.npy'") # print to confirm that the file has been saved

  **Output**
    
    Original array X:
    [[0.1776342  0.57704216 0.23915709 0.96082686 0.73985412]
     [0.4339007  0.05191411 0.61247685 0.54095802 0.67134365]
     [0.12890651 0.06126694 0.18407051 0.31359245 0.80190885]
     [0.87789692 0.53974643 0.81134419 0.37634833 0.77633622]
     [0.53949434 0.75783353 0.42785424 0.65036754 0.46056141]]

    Normalized array X:
    [[-1.27594555  0.26429953 -1.03869359  1.74429631  0.89215463]
     [-0.28769981 -1.76076253  0.40094704  0.1251475   0.6279563 ]
     [-1.46385513 -1.72469499 -1.25112509 -0.75164698  1.13145756]
     [ 1.42449191  0.12047526  1.16784325 -0.50964018  1.03284127]
     [ 0.11950311  0.96148898 -0.31101691  0.54706567 -0.18488756]]

    Normalized array saved as 'X_normalized.npy'

  **Conclusion**

To conclude, I created a NumPy program that generates a random 5x5 array and normalizes it using the formula (X - mean) / std. The mean was obtained using .mean() and the standard deviation using .std(). Finally, the normalized array was saved into a .npy file using np.save(). This technique is useful in data preprocessing, ensuring values are scaled consistently.


## 2. Divisible by 3 Problem 
This function works by creating a 10x10 NumPy array of the squares of the first 100 positive integers. After forming the matrix, the program filters and prints all the numbers divisible by 3, and then saves them into a _.npy_ file.

   **Code**

    A = (np.arange(1, 101) ** 2).reshape(10, 10) # square each element then reshape the result into a 10x10 2D array which is a matrix
    print("Array A (squares of first 100 integers):") # label and print the matrix
    print(A) # print the contents of the matrix

    div_by_3 = A[A % 3 == 0] # find all elements in the matrix that are divisible by 3
    print("\nElements divisible by 3:") # label and print to indicate the elements that are divisible by 3
    print(div_by_3) # print all the values that are divisible by 3

    np.save('div_by_3.npy', div_by_3) # save the values that are divisible by 3 with the file name div_by_3.npy
    print("\nDivisible by 3 elements saved as 'div_by_3.npy'") # print to confirm that the file has been saved

  **Output**

    Array A (squares of first 100 integers):
    [[    1     4     9    16    25    36    49    64    81   100]
     [  121   144   169   196   225   256   289   324   361   400]
     [  441   484   529   576   625   676   729   784   841   900]
     [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
     [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
     [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
     [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
     [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
     [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
     [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

    Elements divisible by 3:
    [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
     2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
     7569 8100 8649 9216 9801]

    Divisible by 3 elements saved as 'div_by_3.npy'

  **Conclusion**
  
In conclusion, I created a 10x10 NumPy matrix consisting of the squares of numbers 1 to 100 using np.arange(1, 101) ** 2 and reshaping it into a 10x10 array. I then extracted the numbers divisible by 3 using array filtering (A % 3 == 0). Finally, the results were saved to a .npy file with np.save(). This demonstrates how NumPy can be used to generate structured arrays and apply conditional filtering.
