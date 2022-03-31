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


# 우선순위 큐

# heapq



# min heap
```
import heapq

arr = []
heapq.heappush(arr,4) # min heap
heapq.heappush(arr,1)
heapq.heappush(arr,9)
heapq.heappush(arr,10)
heapq.heappush(arr,3)

print(heapq.heappop(arr)) # min heap pop



arr = [2,13,3,1,5]
heapq.heapfy(arr)

```

```
import heapq

arr=[]
heapq.heappush(arr,[4,'gg'])
heapq.heappush(arr,[1,'banana'])
heapq.heappush(arr,[6,'as'])
heapq.heappush(arr,[9,'adsf'])
heapq.heappush(arr,[2,'asdaw1qweq'])

while arr:
    print(heapq.heappop(arr)[1])
```


# max heap 만들기

arr = []
heapq.heappush(arr,-4) # min heap
heapq.heappush(arr,-1)
heapq.heappush(arr,-9)
heapq.heappush(arr,-10)
heapq.heappush(arr,-3)


1. 튜플이용
2. 음수 사용

arr = list(map(lammbda x:-x,arr))



# 해쉬
# 세그먼트 트리
```
트리형태로 구현하는 방법


누적 구간을 구하는 공식
1. for문 사용 (제일느림)
2. imos[누적합 배열사용] (대부분의 경우 사용)
3. segment tree[누적합 트리 사용] (배열의 값이 자주 바뀔 때)

```

# 에드혹


# 다익스트라
# 벨만 포드
# 플루이드 와샬
