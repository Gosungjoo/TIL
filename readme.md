# 유클리드 호제법
# 숫자 2개 입력
# 입력받은 두 숫자의 최대 공약수 구하기


한 연산 값의 모듈러 값을 이용하여
지속 연산
GCD = 1 서로소

```
def GCD(x,y):

    
    r = -1
    while(True):
        r = x % y
        if  r == 0:
            return y
        else:
            x = y
            y = r



print(GCD(24,11))
```

```
def GCD(x,y):
    Max = max(x,y)
    Min = min(x,y)
    r = Max % Min
    if  r == 0:
        return Min
    else:
        return GCD(r,Min)

print(GCD(24,16))

```

## 입력받은 두개의 최소공배수
* 최대공약수 활용

```
def GCD(x, y):
    r = -1
    while (True):
        r = x % y
        if r == 0:
            return y
        else:
            x = y
            y = r


print(GCD(24, 16))


def LCM(x,y):
    gcd=GCD(x,y)
    dx=x/gcd
    dy=y/gcd
    return int(dx*dy*gcd)

print(LCM(24, 16))
```



# 에라토스테네스의 체

## 그냥 소수 구하기

```

def prime(x):
    for i in range(2,int(x**(1/2))):
        if x%i == 0:
            return False
    else:
        return True


print(prime(999))
```
x**(1/2) 까지만 하는 이유?
 이제까지 자기 자신의 루트보다 큰 수로는 나눌 수 없다. -> 잘 생각해보자

 

## 에라토스테네스의 체


a = int(input())
answer=[]
check=[0]*(a+1)

for i in range(2,a+1):
if check[i] == 0:
  answer.append(i)
for j in range(i+i,a+1,i):
  check[j] = 1
print(*answer)
