## What is Big O Notation? 
The complexity of data structures and algorithms with respect to space and/or time 
- Every function, method, algorithm, or process will have a given 'complexity' 
  - The way we represent this complexity is with Big O Notation

## Big O, Omega and Theta
In academia, O, Omega, and Theta are used to describe runtimes
- Big 0: The algorithm’s upper bound
  - An algorithm is the most amount of time required, or worst case scenario
- Big Omega (Ω): The algorithm’s lower bound
  - An algorithm is the least amount of time required, or best case scenario  
- Big Theta (Θ): The algorithm's upper and lower bound (tight bound)
  -  tightest bound is the best of all the worst case times


## We get a straight line increasing with a given slope. As you can see, as input size increases, so does the runtime

### Linear Complexity:
  ```
     ar arr = [1,2,3,4,5]; 
    for(int i=0; i<arr.length; i++){ 

      if( arr[i] == 3){ 
        return i; 
      } 
    }
  ```

![Linear Complexity](https://user-images.githubusercontent.com/39278408/194727593-fe7cb08d-3b46-4f33-84f5-316bd5283b8a.png)
)

### Quadratic Complexity:

  ```
    ar arr = [1,2,3,4,5]; 
    for(int i=0; i<arr.length; i++){ 
        for(int i=0; i<arr.length; i++){ 
          if( arr[i] == 3){ 
            return i; 
          } 
       }
    }
  ```

![Quadratic Complexity](https://user-images.githubusercontent.com/39278408/194727778-b080daf5-579c-4d91-ab25-87751560a1da.png)

