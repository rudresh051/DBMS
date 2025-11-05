# Normalization in Databases 3NF, BCNF

# 3NF
A relation R is said to be in 3NF if it is already in 2NF and there is no any non-prime attribute in R which is transitively dependent on the key of R

Example 1 -   

![alt text](image-36.png)

* Remove D from original relation and keep it in other relation with C

Example 2 -  

![alt text](image-37.png)

Decompose above  

R(A,B,C,F)  
FD => A -> BCF  
R2(C,D,E)  
FD => C -> DE

Example 3 -  

![alt text](image-38.png)

## BCNF(Boyce Codd Normal Form)
A relation R is said to be in BCNF if it is already in 3NF and for every functional dependency a -> b , a should be super key in R
![alt text](image-41.png)

![alt text](image-40.png)

![alt text](image-42.png)

So to make above BCNF , we need to decomposition 

![>](image-43.png)

