def fibo(n):
    if n<=1:
        return n
    return (fibo(n-1)+fibo(n-2))

n=int(input("n="))
for i in range(n):
    print(fibo(i))
    **********************************************************
    i=0
j=1
sum=0
print(i,j)
n=int(input("n="))
for i in range(2,n):
    sum=i+j
    print(sum)
    i=j
    j=sum
