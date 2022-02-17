# anagram
* 문자열의 순서를 조절하여 다른 단어로 만드는 것


```
anagram('listen') == anagram('slient')
```


ex)

```
a , b = input().split()

DAT_a = [0]*52
DAT_b = [0]*52


for i in a:
    if('A' <= i <= 'Z'):
        k = 'A'
        p = 26
    else:
        k = 'a'
        p = 0
    DAT_a[ord(i)-ord(k)+p] += 1

for i in b:
    if('A' <= i <= 'Z'):
        k = 'A'
        p = 26
    else:
        k = 'a'
        p = 0
    DAT_b[ord(i)-ord(k)+p] += 1

if(DAT_a == DAT_b):
    print('anagram')
else:
    print('not anagram')
```
