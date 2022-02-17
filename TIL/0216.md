# sliding window

* 연속된 arr의 5개의 값의 합 중 max 값 출력


```

arr = [3,7,4,1,1,100,2,3,4,5,7]

max = 0
for i in range(len(arr)-5):
    t= sum(arr[i:i+5])
    if(t > max):
        max= t
print(max)

```

* 이런식으로 풀면 O(n*m)의 속도가 나온다.


```
arr = [3,7,4,1,1,100,2,3,4,5,7]
t = sum(arr[0:5])
max = t
for i in range(6):
  t = t+arr[5+i]-arr[i]
  if (max < t):
    max = t

```

* 이렇게 슬라이딩 윈도우로 바꾸면 O(n)의 속도로 풀 수 있다.

```
arr = list(map(int,input().split()))
N = int(input())

t = sum(arr[0:N])
max = t
for i in range(len(arr)-N):
  t = t+arr[N+i]-arr[i]
  if (max < t):
    max = t
print(max)
```

* 구간 합을 먼저 한개 만들고 다음 1개의 원소를 더하고 맨 앞의 원소를 빼주면 간단하게 구현된다.

* 기존의 max값과 비교하여 최대값을 구하면 된다.




# 투포인터

* start, end의 index를 가져간다.
* 현재 구간합이 작다면 end +1 증가
* 연속된 구간합이 크다면 start +1 증가
* 모든 경우를 확인할 때까지 2-4번 과정을 반복한다.


```
n = 5  # 데이터의 개수 N
m = 5  # 찾고자하는 부분합 M

count = 0
interval_sum = 0
end = 0

# start를 차례대로 증가시키며 반복
for start in range(n):
    # end만큼 이동시키기
    while interval_sum < m and end < n:
        interval_sum += data[end]
        end += 1
    # 부분합이 m일 때 카운트 증가
    if interval_sum == m:
        count += 1
    interval_sum -= data[start]

print(count)
```




# 두가지의 차이점

* 슬라이딩 윈도 
  * 구간이 정해져 있을 때,
* 투포인터 
  * 구간이 정해져 있지 않을 때도

 *속도는 둘다 O(n)*