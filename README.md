# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```

Program to QR decomposition using the Gram-Schmidt method
Developed by: NIRAUNJANA GAYATHRI G R
RegisterNumber: 22008369
'''
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape # get the shape of A
    Q = np.empty((n, n)) # initialize matrix Q
    u = np.empty((n, n)) # initialize matrix u
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1, n):
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j] # get each u vector
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i]) # compute each u vector
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
    
    
    
    
a = np.array(eval(input()))
QR_Decomposition(a)







```

## Output
```
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-01-17%2012-08-12.png![image](https://user-images.githubusercontent.com/119395610/212827199-256e0837-1964-4580-91a8-b6e937f359ba.png)
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-01-17%2012-08-37.png![image](https://user-images.githubusercontent.com/119395610/212827282-418caf4a-fa55-41d2-92f8-6901a66b97db.png)



```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
