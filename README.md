# ECE2112-PA2
## Normalization Problem: 
Step 1: For this problem, we first need to import the ```numpy``` library, since its needed to be able to use the functions that will later be used in the problem. Also, ```np``` is just an alias to make referencing shorter.
```py
import numpy as np
```

Step 2:  We then need to create a 5x5 array and use the ```random.random(())``` function in order for the array to generate random floats and store it in variable ```X```.  
```py
X=np.random.random((5,5))
```

Step 3.1: Now, we need to first find the mean and standard deviation of the array in order to normalize it. We can use the ```.mean()``` method to find the mean of the array and store it under variable ```mean```.
```py
mean=X.mean()
```

Step 3.2: We use the ```.std()``` method to find the standard deviation of the array and store it under variable ```standard_deviation```.
```py
standard_deviation=X.std()
```

Step 4: We can now normalize the array by using the formula ```Z=(X-x̄)/σ```. Where ```Z``` is the **normalized/standardized value**, ```X``` is the **raw value** of our array, ```x̄``` is the **mean**, and ```σ``` is the **standard deviation**. We then store the values under variable named ```Z_array``` since its an array of normalized values.
```py
Z_array=(X-mean)/standard_deviation
```

Step 5: Now that the calculations are done, we can finally save the values stored into ```Z_array``` to a ```.npy``` file named ```X_normalized.npy```.
```py
np.save("X_normalized.npy", Z_array)
```

Step 6: Print out the variables ```X``` and ```X_normalized.npy``` for verification purposes.
```py
print(repr(X))
array([[0.14180879, 0.61070286, 0.3586823 , 0.86059853, 0.19274675],
       [0.20219922, 0.76311671, 0.3227388 , 0.63289916, 0.59434955],
       [0.55229215, 0.99596099, 0.55039339, 0.11109792, 0.12006031],
       [0.09093524, 0.10067076, 0.67310727, 0.86337194, 0.07252998],
       [0.39344623, 0.51611446, 0.12455799, 0.41292107, 0.21778868]])

normalized=np.load("X_normalized.npy")
normalized
array([[-1.00680811,  0.69627673, -0.21909502,  1.6039306 , -0.82179475],
       [-0.78746213,  1.24986383, -0.34964656,  0.77689661,  0.63687937],
       [ 0.48412136,  2.09558484,  0.47722482, -1.11835402, -1.08580142],
       [-1.1915875 , -1.15622683,  0.92293775,  1.61400398, -1.25843781],
       [-0.09282786,  0.35271924, -1.06946527, -0.0220927 , -0.73083916]])
```
<br>

## Divisible by 3 Problem:
Step 1: Same as the previous problem, we import the ```numpy``` library before we try to code as its functions will be required. Though Python alone can handle this, the inclusion of the NumPy library gives faster operations and built-in methods for arrays, reshaping, and math.
```py
import numpy as np
```

<p align="justify">Step 2: We now want an array of perfect squares from 1 to 100. We can use this by using the ```np.arange()``` function. However, this will only list the integers from 1 to 100 and will not list their perfect squares. So, we need to raise each number in the array by a power of 2 using the ```**2``` operator. We can now then store this under the variable ```squared_values```.</p>

```py
squared_values = np.arange(1, 101) ** 2
```

Step 3: This step is not important, we can print out the array to verify if the output is correct.
```py
squared_values
array([    1,     4,     9,    16,    25,    36,    49,    64,    81,
         100,   121,   144,   169,   196,   225,   256,   289,   324,
         361,   400,   441,   484,   529,   576,   625,   676,   729,
         784,   841,   900,   961,  1024,  1089,  1156,  1225,  1296,
        1369,  1444,  1521,  1600,  1681,  1764,  1849,  1936,  2025,
        2116,  2209,  2304,  2401,  2500,  2601,  2704,  2809,  2916,
        3025,  3136,  3249,  3364,  3481,  3600,  3721,  3844,  3969,
        4096,  4225,  4356,  4489,  4624,  4761,  4900,  5041,  5184,
        5329,  5476,  5625,  5776,  5929,  6084,  6241,  6400,  6561,
        6724,  6889,  7056,  7225,  7396,  7569,  7744,  7921,  8100,
        8281,  8464,  8649,  8836,  9025,  9216,  9409,  9604,  9801,
       10000])
```

Step 4: We now need to transform this array from 1D to a 2D array with 10 rows and 10 columns. We can use the ```.reshape()``` function and assign it under a variable ```integer_arr```.
```py
integer_arr = values.reshape(10, 10)
```

Step 5: Similarly to step 3, this step is not important, but we can print out the 10x10 array to visually verify if its created and reshaped correctly.
```py
integer_arr
array([[    1,     4,     9,    16,    25,    36,    49,    64,    81,
          100],
       [  121,   144,   169,   196,   225,   256,   289,   324,   361,
          400],
       [  441,   484,   529,   576,   625,   676,   729,   784,   841,
          900],
       [  961,  1024,  1089,  1156,  1225,  1296,  1369,  1444,  1521,
         1600],
       [ 1681,  1764,  1849,  1936,  2025,  2116,  2209,  2304,  2401,
         2500],
       [ 2601,  2704,  2809,  2916,  3025,  3136,  3249,  3364,  3481,
         3600],
       [ 3721,  3844,  3969,  4096,  4225,  4356,  4489,  4624,  4761,
         4900],
       [ 5041,  5184,  5329,  5476,  5625,  5776,  5929,  6084,  6241,
         6400],
       [ 6561,  6724,  6889,  7056,  7225,  7396,  7569,  7744,  7921,
         8100],
       [ 8281,  8464,  8649,  8836,  9025,  9216,  9409,  9604,  9801,
        10000]])
```

<p align="justify">Step 6: Now that we have the 10x10 array which has the squares of the first 100 integers, we can now proceed to the other part, which is to determine the elements that are divisible by 3. We can create a boolean array for divisibility. This takes every element in the array, computes the remainder when dividing by 3 (```%3```), and checks if the remainder is equal to zero (```==0```). We will now finally store it under a variable named ```division```, which will print out the said array with the same dimensions with True if the element is divisible by 3 and False if not. </p>

```py
division=(integer_arr %3==0)
```

Step 7: Again, this step is not crucial, but can be useful to visualize/verify the output of the boolean array.
```py
division
array([[False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False]])
```

Step 8: We now need to list out the elements in the array where its divisible by 3. We can use the boolean array as an index for the original array, which will return an array of only those numbers where its boolean value is True. We then store this under the variable ```divisible```.
```py
divisible_by_3=array[division]
```

Step 9: We now print the array for verification purposes.
```py
divisible_by_3
array([[False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False],
       [False,  True, False, False,  True, False, False,  True, False,
        False],
       [ True, False, False,  True, False, False,  True, False, False,
         True],
       [False, False,  True, False, False,  True, False, False,  True,
        False]])
```

Step 10: We can finally save the values stored in variable ```divisible_by_3``` into a ```.npy``` file named ```div_by_3.npy```.
```py
np.save("div_by_3.npy", divisible_by_3)
```

Step 11: Run ```div_by_3.npy``` to check whether it saved the values.
```py
loaded=np.load("div_by_3.npy")
loaded
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```

