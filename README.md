# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
## step1:
Intialize the matrix Q and u
## step2:
The vector u and e is given by 

![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/0744933e-278a-4aa5-8bd6-7e2de6578ead) 
![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/c44352fa-9f39-472a-9d6a-f76e313899b6)
![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/190db081-ab66-4cfc-b344-4aaf79ae732f)

## step3:
Obtain the Q matrix
![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/3e69cf93-d2d4-49e0-923f-b7b2cace2969)

## step4:
Construct the upper triangular matrix R ![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/3ccdefff-5b46-4ce4-aaa3-326f7fc55817)


## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: DIVYA K
RegisterNumber: 212222230035
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0] / np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])* Q[:,j]
            Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
    
    
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
![image](https://github.com/divyakumars/QRdecomposition/assets/119393621/b64e3db4-82ca-460a-b390-7204265c9151)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
