# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
![Screenshot 2023-12-31 135538](https://github.com/PremkumarG3/QRdecomposition/assets/138955646/4839d3a1-678e-4aba-94c3-2acbbc3bd334)
## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by:PREM KUMAR G
RegisterNumber:23003614 
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape
    
    Q = np.empty((n, n))
    u = np.empty((n, n))
    
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1, n):
        
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
            
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R = np.zeros((n,m))
    for i in  range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![Screenshot 2023-12-29 005932](https://github.com/PremkumarG3/QRdecomposition/assets/138955646/c395de81-ecff-4e25-af09-49051c8fed38)
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
