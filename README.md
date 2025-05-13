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
Developed by: BALAJI ARAMBAKAM  
RegisterNumber: 212224230021
'''
import numpy as np
def QR_Decomposition(A):
    m, n = A.shape
    Q = np.zeros((m, n))
    R = np.zeros((n, n))
    for j in range(n):
        v = A[:, j]
        for i in range(j):
            R[i, j] = np.dot(Q[:, i], A[:, j])
            v = v - R[i, j] * Q[:, i]
        R[j, j] = np.linalg.norm(v)
        Q[:, j] = v / R[j, j]
    return Q, R
    
a = np.array(eval(input()))

Q, R = QR_Decomposition(a)
print(f"The Q Matrix is\n {Q}")
print(f"The R Matrix is\n {R}")
```

## Output
![image](https://github.com/user-attachments/assets/92c3ae03-a079-4c09-94b5-700e95ba227c)
![image](https://github.com/user-attachments/assets/78d71346-5e61-40cf-978f-1c9cc3fa0513)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
