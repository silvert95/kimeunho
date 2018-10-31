# 2014261066 / kimeunho

Github 마크다운 정리 및 git 사용법

## Github 마크다운

헤더
H1 ~ H6까지 테그를 #으로 표현

```
# 헤더 스타일 (h1)
## 헤더 스타일 (h2)
### 헤더 스타일 (h3)
#### 헤더 스타일 (h4)
##### 헤더 스타일 (h5)
###### 헤더 스타일 (h6)
```

출력 결과
헤더 스타일 (h1)
헤더 스타일 (h2)
헤더 스타일 (h3)
헤더 스타일 (h4)
헤더 스타일 (h5)
헤더 스타일 (h6)
효과: 다음과 같은 코드와 동일한 결과가 됨
```
<h1>헤더 스타일 (h1)</h1>
<h2>헤더 스타일 (h2)</h2>
<h3>헤더 스타일 (h3)</h3>
<h4>헤더 스타일 (h4)</h4>
<h5>헤더 스타일 (h5)</h5>
<h6>헤더 스타일 (h6)</h6>
```
수평선

’-‘, ‘*‘, ‘_‘을 세개 이상 나열하면 수평선을 만듦

단락 나누기 용도로 많이 사용.

```
***
___
___
```

출력 결과

텍스트 출력

별도의 테그 없이 입력된 내용은 <p> ~ <\p> 처리가 됨
```
markdown은 직관적이고 간단한 문법으로 컨텐츠 관리에 매우 효과적입니다.
```

텍스트 강조
```
*single asterisks* - 기울임체
_single underscores_ - 기울임체
**double asterisks** - 굵은글씨체
__double underscores__ - 기울임체/굵은글씨체
***triple underscores*** - 기울임체/굵은글씨체
~~cancelline~~ - 취소줄
```

결과 출력

single asterisks - 기울임체
single underscores - 기울임체
double asterisks - 굵은글씨체 
double underscores - 기울임체/굵은글씨체
triple underscores - 기울임체/굵은글씨체 
cancelline - 취소줄

인용 (top)

분문 중 인용된 글을 표시할 때 사용하며, “>” 기호를 모든 줄 앞에 붙임.

”>” 기호의 개수에 따라 들여쓰기 레벨 조정 가능

인용 블록 안에서 다른 마크다운 테그를 포함할 수 있음

인용 블록 안에서 중첩 인용 표기 가능

인용 예제 1: 기본 스타일

> 인용되는 글입니다. > 인용되는 글의 두 번째 줄. > 인용되는 글의 세 번째 줄.
출력 결과
인용되는 글입니다. 
인용되는 글의 두 번째 줄.
인용되는 글의 세 번째 줄. 

인용문의 레벨을 설정 할 수 있음
인용 예제 2: 중첩 인용 및 스타일 적용
```
> 인용되는 첫 번째 줄입니다.
>> 인용되는 내용 안에서 다시 인용되는 부분입니다.
> (인용 수준을 변경할 때 이렇게 빈 줄 하나 넣어주세요)
> 꺽쇠 한 번만 쓰면 다시 상위 수준으로 표시됩니다.
> ###### 인용문 내부 헤더
인용되는 첫 번째 줄입니다.
```

인용되는 내용 안에서 다시 인용되는 부분입니다.

(인용 수준을 변경할 때 이렇게 빈 줄 하나 넣어주세요)

꺽쇠 한 번만 쓰면 다시 상위 수준으로 표시됩니다.

인용문 내부 헤더
인용 예제 2: tab 을 적용한 인용
인용 기호 앞에 tab을 입력하면 인용문의 들여 쓰기를 작성 가능.
> 인용되는 글입니다. > 인용되는 글의 두 번째 줄. > 인용되는 글의 세 번째 줄.
출력 결과

인용되는 글입니다. 
인용되는 글의 두 번째 줄.
인용되는 글의 세 번째 줄. 
인용문의 레벨을 설정 할 수 있음










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
