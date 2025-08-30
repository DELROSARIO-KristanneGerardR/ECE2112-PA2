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
print(X)

normalized=np.load("X_normalized.npy")
normalized
```
<br>

## Divisible by 3 Problem:
Step 1: Same as the previous problem, we import the ```numpy``` library before we try to code as its functions will be required. Though Python alone can handle this, the inclusion of the NumPy library gives faster operations and built-in methods for arrays, reshaping, and math.
```py
import numpy as np
```

Step 2: <p align="justify"> We now want an array of perfect squares from 1 to 100. We can use this by using the ```np.arange()``` function. However, this will only list the integers from 1 to 100 and will not list their perfect squares. So, we need to raise each number in the array by a power of 2 using the ```**2``` operator. We can now then store this under the variable ```squared_values```.</p>
```py
squared_values = np.arange(1, 101) ** 2
```

Step 3: We now need to transform this array from 1D to a 2D array with 10 rows and 10 columns. We can use the ```.reshape()``` function and assign it under a variable ```integer_arr```.
```py
integer_arr = values.reshape(10, 10)
```

Step 4: Though this step is not important, but we can print out the 10x10 array to visually verify if its created and reshaped correctly.
```py
integer_arr
```

Step 5: <p align="justify"> Now that we have the 10x10 array which has the squares of the first 100 integers, we can now proceed to the other part, which is to determine the elements that are divisible by 3. We can create a boolean array for divisibility. This takes every element in the array, computes the remainder when dividing by 3 (```%3```), and checks if the remainder is equal to zero (```==0```). We will now finally store it under a variable named ```division```, which will print out the said array with the same dimensions with True if the element is divisible by 3 and False if not. </p>
```py
division=(integer_arr %3==0)
```

Step 6: Again, this step is not crucial, but can be useful to visualize/verify the output of the boolean array.
```py
division
```

Step 7: We now need to list out the elements in the array where its divisible by 3. We can use the boolean array as an index for the original array, which will return an array of only those numbers where its boolean value is True. We then store this under the variable ```divisible```.
```py
divisible_by_3=array[division]
```

Step 8: We now print the array for verification purposes.
```py
divisible_by_3
```

Step 9: We can finally save the values stored in variable ```divisible_by_3``` into a ```.npy``` file named ```div_by_3.npy```.
```py
np.save("div_by_3.npy", divisible_by_3)
```

Step 10: Run ```div_by_3.npy``` to check whether it saved the values.
```py
loaded=np.load("div_by_3.npy")
loaded
```

