# TIL
##  git 구조 4단계<br>
RemoteRepo.<br>
LocalRepo.<br>
Staging Area <commit 대기실><br>
작업 폴더



##  단계 별 정리
1. 작업파일 변화/생성/수정
2. 변화가 있으면 감지(auto) [추적]
3. 추적된 파일을 Staging Area에 올린다. [add]
4. Commit을 통해 Local 에 올린다.
5. Push를 통해 Remote 에 올린다.


---

## ignore
* ignore 파일 생성 (.gitignore)<br>
### 해당 파일 양식
* 해당 폴더의 파일 이름을 확장자까지 작성
> abc.txt

* *을 삽입하게 되면 그 이후 단어는 전부 포함
> abc1.txt abc2.txt ....<br>
> abc*

* 폴더는 /를 통해서 구분
> cache/<br>
> cache/*<br>

---
## 인증 Factor

* Single Factor 인증
    * 1개로 인증한다.
    > Password
* Two Factor 인증
    * 2개로 인증한다.
    > Password , 휴대폰
* Multi Factor 인증
    * 2가지 이상의 여러개로 인증한다.
    >  id , 지문, 홍채..<br>

    
 이런 Facotr 중 Keyfile은 Git에 올리면 안된다.
