# union find

* 독립된 data들을 그룹화
* hash table을 통해서 구현

```

A B C D E F 
0 0 0 0 0 0

이렇게 있을 때

union(A,B)

A B C D E F 
0 A 0 0 0 0


union(D,E)

A B C D E F 
0 A 0 0 D 0


union(A,E)

A B C D E F 
0 A 0 0 D 0

0이 나올 때 까지 탐색
E -> D -> 0 그룹 장
A -> 0 그룹 장

둘 중 어느거나 선택해서 그룹장의 index 적어줌

A B C D E F 
0 A 0 A D 0


```

## python code
```
# union find
# 알파벳으로 이루어진 union 함수 구현


arr = [0]*200
def find_reader(a):
    if type(a) == type('c'):
        a = ord(a)
    if arr[a] == 0:
        return a
    else:
        return find_reader(arr[a])





def union(a,b):
    # 두개를 묶어줘야함
    index_a,index_b = ord(a),ord(b)
    index_boss_a=find_reader(index_a)
    index_boss_b=find_reader(index_b)
    if index_boss_a == index_boss_b:
        return
    else: arr[index_b]  = index_a

union('A','B')
union('B','E')


x,y = input().split()
if find_reader(x) == find_reader(y):
    print('같음')
else: print('다름')

```

## 최적화 방법

```

이동하면서 index를 갱신하면 된다.
find_reader 에서 return 전에 reader의 값으로 바꿔준다.


def find_reader(a):
    if type(a) == type('c'):
        a = ord(a)
    if arr[a] == 0:
        return a
    else:
        return find_reader(arr[a])

```
```
def find_reader(a):
    if type(a) == type('c'):
        a = ord(a)
    if arr[a] == 0:
        return a
    else:
      reader = find_reader(arr[a])
      arr[a] = reader
      return reader
```


# 최소신장트리

```
cycle이 발생하지 않고 모든 정점을 연결한 트리
union find를 사용

사이클이 발생하면 끝


arr = [0]*200
def find_reader(a):
    if type(a) == type('c'):
        a = ord(a)
    if arr[a] == 0:
        return a
    else:
        return find_reader(arr[a])





def union(a,b):
    # 두개를 묶어줘야함
    index_a,index_b = ord(a),ord(b)
    index_boss_a=find_reader(index_a)
    index_boss_b=find_reader(index_b)
    if index_boss_a == index_boss_b:
        return False
    else: arr[index_b]  = index_a
    return True








N = int(input()) # N 정점의 개수
M = int(input()) # M 노드의 개수
node = []
for i in range(M):
    node.append(input().split())
    node[i][2] = int(node[i][2])


node.sort(key= lambda x:x[2])


count = 0
sum_cost = 0
while(True):
    t = node.pop(0)
    A,B,cost = t[0],t[1],t[2]
    if union(A,B):
        sum_cost += cost
        count += 1
    if count >= N:
        break
print(sum_cost)

```
