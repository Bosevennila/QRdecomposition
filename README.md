# Algorithm for QR Decomposition

## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.

## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
3.	
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
3.	Obtain the Q matrix   
4.	Construct the upper triangular matrix R

## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: CHANDRAPRIYADHARSHINI C
RegisterNumber: 23013526
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape # get the shape of A 
    Q=np.empty((n,n)) # initialize matrix Q
    u=np.empty((n,n)) # initialize matrix u
    
    u[:, 0]=A[:, 0]
    Q[:, 0]=A[:, 0]/np.linalg.norm(u[:, 0])
    
    for i in range(1,n):
        u[:, i]=A[:, i]
        
        for j in range(i):
            u[:, i]-=(A[:, i]@ Q[:, j])*Q[:, j] # get each u vector
            
        Q[:, i]=u[:, i]/np.linalg.norm(u[:, i]) # compute each e vector
        
    R=np.zeros((n,m))
    
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:, j]@Q[:, i]
            
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output

![image](https://github.com/Bosevennila/QRdecomposition/assets/144870486/d613fe22-7850-4852-88ac-c062d2047de2)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
