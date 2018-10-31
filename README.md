# 2014261066 / kimeunho

Github 마크다운 정리 및 git 사용법

## Github 마크다운

## 1. 헤더Headers

큰제목: 문서 제목
```
This is an H1
=============
```
# This is an H1

작은제목: 문서 부제목
```
This is an H2
-------------
```
### This is an H2
글머리: 1~6까지만 지원
```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6+
```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
####### This is a 7.

## 2. BlockQuote

이메일에서 사용하는 ```>``` 블럭인용문자를 이용한다.
```
> This is a blockqute.
```
> This is a first blockqute.

>> This is a second blockqute.

>>> This is a third blockqute.

## 3. 목록
● 순서있는 목록(번호)
순서있는 목록은 숫자와 점을 사용한다.
```
1. 첫번째
2. 두번째
3. 세번째
```
1. 첫번째
2. 두번째
3. 세번째

현재까지는 어떤 번호를 입력해도 순서는 내림차순으로 정의된다.
```
1. 첫번째
3. 세번째
2. 두번째
```
1. 첫번째
3. 세번째
2. 두번째


● 순서없는 목록(글머리 기호)
```
* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑
```
* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑



## 4. 코드```<pre><code></code></pre>```

4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.

  한줄 띄어쓰면 인식이 제대로 안되는 문제가 발생하곤 합니다.
```
This is a normal paragraph:

    This is a code block.
end code block.
```

``` '''This is a normal paragraph: This is a code block. end code block.''' ```

실제로 적용해보면, This is a normal paragraph:
```
This is a code block.
```
end code block.

## 5. 수평선```<hr/>```
아래 줄은 모두 수평선을 만든다. 마크다운 문서를 미리보기로 출력할 때 페이지 나누기 용도로 많이 사용한다.
```
* * *

***

*****

- - -

---------------------------------------
```

* * *

***

*****

- - -

---------------------------------------

## 6. 링크
참조링크
```
[link keyword][id]
[id]: URL "Optional Title here"

Link: [Google][googlelink]
[googlelink]: https://google.com "Go google"
```
Link: [Google][googlelink] [googlelink]: https://google.com "Go google"

인라인 링크
```
syntax: [Title](link)
```
syntax: [Naver](https://www.naver.com/)

자동연결
```
<http://example.com/>
<address@example.com>
```
<https://www.google.com/>
<silvert95@gmail.com>

## 7. 강조
```
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
++underline++
~~cancelline~~
```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

++underline++

~~cancelline~~


## 8. 이미지
```
![Alt text](/path/to/img.jpg)
![Alt text](/path/to/img.jpg "Optional title")
```
![Alt text](http://post.phinf.naver.net/MjAxNzA1MDRfNzkg/MDAxNDkzODc1MzI4MTA1.SeMv8PKRDv6DyCN7YI8CaTXNf-HsRHu1hQSId9bgZ84g.-h_UPI8KszFE8r_d2Sbu9j1mUjTFkByNp_s81TeauOog.JPEG/IJ0kjmNatss4OOXL2oS94njQyhqs.jpg)



사이즈 조절 기능은 없기 때문에 <img width="" height=""></img>를 이용한다.


## Git 명령어 정리

Alt text

우선 적으로 git repo관리를 위해 사용자 설정을 해줘야한다. repo별 설정 조회는 각 .git이 생성된 폴더로 경로를 이동하여 하여야한다

### 전역 사용자

git config --global user.name "이름" git config --global user.email "메일주소"

### repo별 사용자

git config user.name "이름" git config user.email "메일주소"

user설정은 필수며 미입력시 commit 집계도 되지않고 누가 커밋시켯는지 모르게된다

## 다음은 설정 정보 조회

### 전역 설정 조회

git config --global --list

### repo별 설정 조회

git config --list

### 저장소 초기화 (첫 설정)

git init

### 저장소 복제 (내려받기)

git clone "저장소 URL"

### 원격 저장소 추가하기

git remote add "원격 저장소" "저장소 URL" ""

### 새 파일 추가하거나 기존파일 스테이징과 커밋

git add "파일"

git add -p "파일" "파일"

git commit -m "메세제"

### 모든 변경사항 커밋

git commit -m "메세지" -a

### 작업 트리 되돌리기

git checkout HEAD "파일" "파일"

### 스테이징된 기본사항 리셋

git reset HEAD "파일" "파일"

### 라스트 커밋 픽스

git commit -m "메세지" --amend

### 이전 커밋 수정하고 재활용하기

git commit -C HEAD --amend

## 위까지는 마스터에 적용되는사항이며 밑에는 브랜치에 관하여 적는다

### 브랜치 리스트

git branch

### 리모트 브랜치 리스트

git branch -r

### 로컬 및 리모트 모든 브랜치 리스트

git branch -a

### 현재 브랜치에서 새로운 브랜치 추가

git branch "새 브랜치이름"

### 다른 브랜치 체크아웃

git checkout "브랜치"

### 현재 브랜치에서 새로운 브랜치 생성후 체크아웃

git checkout -b "새 브랜치이름"

### 브랜치 복사하기 (덮어쓰기)

git branch -f "기존브랜치" "새 브랜치"

### 브랜치 이동 혹은 리네임

git checkout -m "기존브랜치 "새 브랜치"

### 새 브랜치가 존재하지 않을경우

git checkout -M "기존브랜치" "새 브랜치"

### 브랜치 합치기

git merge "브랜치"

### 커밋하지 않고 합치기

git merge --no-commit "브랜치"

### 브랜치 삭제하기

git branch -d "브랜치"

## 로그

### 모든 로그보기

git log

### 변경사항과 함께 로그

git log -p

### 특정 갯수의 로그 보기

git log -숫자 git log -1 위는 1개만 보이기

### 1달간의 커밋 로그

git log -since="1hours"

### 3일전까지의 커밋 로그

git log --before="2days"

### x개 이전의 커밋 보그

git log -1 HEAD-x git log -1 HEAD-1 위는 1개이전

### 작업 트리와 인덱스 차이 보기

git diff

### 인덱스와 repo 차이점

git diff --cached

### 작업트리와 repo 차이점

git diff HEAD

### 파일 커밋정보 줄단위 보기

git blame "파일"

### 파일 복사,붙여넣기,이동정보 줄단위 보기

git blame -M "파일"

### 파일 이동과 원본파일 정보 줄단위로 보기

**git blame -C-C "파일"

### repo 복제시 마지막 x개 커밋만 포함하여 복제

git clone --depth x "저장소 URL" git clone --depth 100 "저장소 URL" 위는 마지막 100개의 커밋만 포함

### origin 저장소에 합치지 않고 로컬 브랜치로 변경사항 가져오기

git fetch

### 리모트 저장소에 합치지 않고 지역 브랜치로 변경사항 가져오기

git fetch "저장소 URL"

### 리모트 저장소에서 변경사항 가져와 현재 브랜치에 합치기

git pull "저장소 URL"

### origin 저장소에서 변경사항 가져와 현재 로컬브랜치에 합치기

git pull

### 로컬 브랜치를 리모트 브랜치에 푸시

git push <저장소 URL> <로컬 브랜치>:<리모트 브랜치>

### 로컬 브랜치를 동일한 이름의 리모트 브랜치에 푸시

git push <저장소 URL> <로컬 브랜치>

### 새로운 로컬 브랜치를 리모트 저장소에 푸시

git push <저장소 URL> <로컬 브랜치>

### 원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기

git remote prune <저장소 URL>

### 원격 저장소를 제거하고 관련된 브랜치도 제거하기

git remote rm <저장소 URL>
