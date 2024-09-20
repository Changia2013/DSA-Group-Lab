# Lab 2


### function 1:

Analyze the following function with respect to number

```python
def function1(number):
	total=0; 			# 1 operation

	for i in range(0,number):	# n operations for the loop
       						# (n loop iterations)
        					# 1 operation for the addition of i + 1 inside each iteration
		x = (i+1)		# 1 operations
		total+=(x*x)		# 2 operations
        					# 1 operation for the multiplication (x * x)
        					# 1 operation for the addition (total += ...)

	return total			# 1 operation for return
					# Total operations: 1 + 3n + 1 = 3n + 2
					# Time complexity: O(n)
```

### function 2:

Analyze the following function with respect to number

```python
def function2(number):
	return  ((number)*(number+1)*(2*number + 1))/6	#7 operations in total:
							    # 1 for (number * (number + 1))
							    # 1 for (number + 1)
							    # 1 for (2 * number + 1)
							    # 2 for the multiplications
							    # 1 for the final multiplication of the three terms
							    # 1 for the division by 6
							# Total operations: 7
							# Time complexity: O(1)

```

### function 3:

Analyze the following with respect to the length of the list.  Note that the function call len() which returns the length of the list is constant (O(1)) with respect to the length of the list.
```python

def function3(list):
	for i in range (0,len(list)-1):			# n - 1 loop iterations
	        						# (n-1 loop iterations for outer loop)
								# 1 operation (length of list)
		for j in range(0,len(list)-1-i):	# (n*(n - 1))/2
								# (n - 1) + (n - 2) + ... + 1 operations for inner loop
            							# Inner loop runs decreasing number of times as i increases
            							# Iterations of inner loop: (n - 1), (n - 2), ..., 1 
			if(list[j]>list[j+1]):		# (n * (n - 1)) / 2
				tmp=list[j]			# 1 operation               					
				list[j]=list[j+1]		# 1 operation 
				list[j+1]=tmp			# 1 operation 
		# Total operations:n - 1 + (n*(n - 1))/2 + 3*(n*(n - 1))/2 = 2n² - n - 1
		# Time complexity: O(n²)					
```
### function 4:

Analyze the following function with respect to number

```python
def function4(number):
	total=1				# 1 operation
	for i in range(1 to number):	# n - 1 loop iterations        				
		total=total*(i+1)		# 2 operations
				        		# 1 operation for addition (i + 1)
				        		# 1 operation for multiplication (total *= ...)
	return total			# 1 operation
	# Total operations: 1 + 2(n - 1) + 1 = 2n
	# Time complexity: O(n)
```


## In class portion


### Group members
List the members of your group member below:

	* Name 
	* Thanh Long Vo
	* Eduardo Cam Chang

### Timing Data

grab a screenshot of your excel graphs and put it here
![1](https://github.com/user-attachments/assets/1af99849-ccea-48c4-a08f-2bd6f80b1a30)
![2](https://github.com/user-attachments/assets/84d4395e-5666-4329-a3e5-ff06adee9b2f)
![3](https://github.com/user-attachments/assets/ab210909-c566-44c1-92bf-a470b7e77967)



### Summary 
|function| runtime based on analysis | Most similar curve | 
|---|---|---|
|partb_one()| O(n²) | Quadratic curve |
|partb_two()| O(n log n)  | Log-linear curve  |
|partb_three()| O(n)  | Linear curve  |


### Discussion:

Look at the code from lab 1 and discuss the differences between fastest/slowest versions. Was it a difference in syntax? A difference in approach?  Write down your observations.
	Fastest function: fibonacci(n) – This function makes use of iteration, hence no repeated calculation is carried out. It's efficient by running in O(n) time. It is faster because it only needs to loop once to calculate the Fibonacci sequence.
 	The slowest function is sum_to_goal(nums, goal): It contains two nested loops for checking all possible pairs, hence it has O(n²) time complexity. This is very slow because it checks all possible combinations of the numbers; this becomes very inefficient when the size of the dataset to be dealt with is large.
  	The critical insight is that the fastest function, fibonacci, does simple operations in a single loop, while the slowest, sum_to_goal, does two nested loops which increase the operations exponentially.

## Reflection:

1. for each function what growth rate best match your results?
	- partb_one: It best fits O(n²) because it is quadratic growth, and its execution time drastically escalates when the increase in data size reflects its quadratic nature.
	- partb_two: Growth rate is O(n log n) Log-linear growth. This corresponds to a steadier rise in execution time with size increase compared with partb_one.
	- partb_three: O(n) -linear growth. Execution time increases very slow and about linearly with data size.
3. Does your analysis match your analysis?  If not, where do you suppose the error occurred?
	Yes, the analysis corresponds to the results. In other words, the theoretical growth rates via complexity analysis O(n²), O(n log n), and O(n) correspond to the actual execution times as seen in the results.
5. What sort of conclusions can you draw based on your observations?
	- This is because partb_one has a time complexity of O(n²) and, for greater data sizes, it becomes much slower. Therefore, it is not able to handle large inputs well.
	- partb_two runs more efficiently compared to partb_one since it has an O(n log n) time complexity and can handle big inputs.
	- The partb_three version outperforms all other versions since its time complexity is O(n); that means it will scale to very large inputs.
	- The crucial observation is that the choice of algorithm dramatically influences the performance, mainly for large input sizes.


