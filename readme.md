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

트리형태로 구현하는 방법


누적 구간을 구하는 공식

1. for문 사용 (제일느림)

2. imos [누적합 배열사용] 
(대부분의 경우 사용)


3. [segment tree](https://yabmoons.tistory.com/431?category=838490) [누적합 트리 사용] (배열의 값이 자주 바뀔 때) + Lazy Propagation



4. [FenwickTree](https://yabmoons.tistory.com/438?category=838490)

# 에드혹



# 그래프 탐색
```
Q. 한 정점에서 다른 모든 도착점까지 드는 최소비용을 구하라(전부 양수 일 때)

-> 다익스트라


Q. 한 정점에서 다른 모든 도착점까지 드는 최소비용(음수도 포함)

-> 벨만포드


Q. 모든 정점에서 다른 모든 정점까지 최단거리?

-> 플루이드 와샬

```


# 1. 다익스트라


## 다익스트라 개요
```
Q. 한 정점에서 다른 모든 도착점까지 드는 최소비용을 구하라(전부 양수 일 때)

-> 다익스트라


BFS나 DFS도 가능하지만

다익스트라가 빠르다.

양방향 단방향 가능

음의 가중치는 X -> 벨만포드 사용

```

## 동작방식(이중 for문 사용, 인접행렬)

```

step 1. 초기화

경유지 -> A,B,C,E,D
used 배열 -> [0,0,0,0,0] 경유지를 선택했는지 여부
result 결과 누적 합 배열 -> [INF,INF,INF,INF,INF]
arr 인접행렬 -> 
[ 0 ,INF,INF,INF,INF]
[INF, 0 ,INF,INF,INF]
[INF,INF, 0 ,INF,INF]
[INF,INF,INF, 0 ,INF]
[INF,INF,INF,INF, 0 ]


STEP 2. 각 경유지의 정보를 받는다.
A B 3
A D 9
A E 5
B C 7
B E 1
C D 1



arr
[ 0 , 3 ,INF, 9 , 5 ]
[INF, 0 , 7 ,INF, 1 ]
[INF,INF, 0 , 1 ,INF]
[INF,INF,INF, 0 ,INF]
[INF,INF,INF,INF, 0 ]

result = [0,3,INF,9,5]
used 배열 -> [1,0,0,0,0]



while(min(used) == 0){
1. 경유지 선택
시작 -> 경유지까지 비용이 가장 적은 것 중 used[i] 가 0일 때

2. 선택하면 used 업데이트

3. 경유지의 값 + 경유지의 노드값 vs 기존 result 더 적은 것을
result에 업데이트

}






```
## 동작방식(우선순위 큐, 인접 리스트)
```








```




# 2. 벨만 포드

```

Q. 한 정점에서 다른 모든 도착점까지 드는 최소비용(음수도 포함)

-> 벨만포드

음의 사이클이 생기면 사용 X


```





# 3. 플루이드 와샬
