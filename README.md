# Exp 01 Matrix Multiplication using MapReduce

### Royce Niran George A (212223060231)

## AIM:
To implement Matrix Vector Multiplication using the MapReduce programming model.
## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python/Java project in the preferred IDE (Eclipse/IntelliJ IDEA/VS Code).

### Step 3:
Create the Python/Java program for Matrix Vector Multiplication using the MapReduce concept.

### Step 4:
Implement the **Mapper** phase to generate intermediate key-value pairs from the input matrices.

### Step 5:
Implement the **Shuffle and Sort** phase to group intermediate values based on common keys.

### Step 6:
Implement the **Reducer** phase to compute the final matrix vector multiplication results.

### Step 7:
Compile and execute the program.

### Step 8:
Verify and display the resulting product matrix.

## PROGRAM:

``` python
# Matrix-Vector Multiplication using MapReduce
# Royce Niran George A 212223060231

from functools import reduce
# Matrix
A = [[21,62,23],[25, 95, 46],[29, 78, 89]]
# Vector
B = [33, 27, 63]
# Mapper function
def mapper(row):
    # Multiply corresponding elements
    products = [x * y for x, y in zip(row, B)]
    return products
# Reducer function
def reducer(products):
    # Add all products to get one result element
    return reduce(lambda x, y: x + y, products)
# Map phase
mapped = list(map(mapper, A))
# Reduce phase
result = list(map(reducer, mapped))
# Display results
print("Matrix:")
for row in A:
    print(row)

print("\nVector:")
print(B)

print("\nMapped values:")
for row in mapped:
    print(row)

print("\nResultant Vector:")
print(result)

```

## OUTPUT:

<img width="537" height="407" alt="image" src="https://github.com/user-attachments/assets/4d3891d7-1e99-45ce-b8cf-6ac2b60d0298" />


## RESULT:

The Matrix Multiplication using the MapReduce programming model was implemented successfully, and the resultant matrix was computed correctly.
