# CLI

Command Line Interface

커맨드(명령어)를 통해 작동하는 인터페이스 <-> GUI(Graphic User Interface, 보통의 프로그램)



# 기초 명령어

### (1)  pwd

* pwd (print working directory) : 현재 폴더의 경로를 알려줌
* ~(Home directory) :  처음 열면 나오는 기본 폴더

### (2) ls(숨겨진 파일은 보여주지 않음)

* ls : 내용물들 출력
* ls -a : 숨겨진 파일까지 보여줌

### (3) cd + 폴더명(폴더명 치다가 tab누르면 자동완성이된다.)

* cd : 디렉토리를 바꿀 때 사용
* cd .. : 상위 디렉토리로 이동
* cd . : 현재 디렉토리로 이동

### (4) mkdir +폴더명

* mkdir(Make Directory) : 폴더 생성

### (5) rm

* rm + 파일명 : 파일 삭제
* rm -r + 폴더명 : 해당폴더 삭제

### (6) touch + 파일명.확장자

* touch : 파일생성

### (7) cp

* cp + 파일명/폴더 + 위치 : 파일 복사
* cp 파일명/폴더.확장자 ./바꿀파일명/폴더.확장자 : 현재 디렉토리에 b라는 a의 파일/폴더를 만들어줌

### (8) mv + 파일/폴더명 + 바꿀파일/폴더명

* mv(move) : 파일명 변셩
* mv aa/ bb : aa라는 폴더를 bb로 변경
* 파일 또는 폴더를 이동할 수 있음 (mv b.txt bb) : b.txt가 bb라는 폴더로 경로 이동됨

### (9) ''

* '를 시작하면 '를 써서 끝내줘야 한다.









# Git

Source Code Management : 코드 관리 도구 (버전을 통해 관리)

Version Control System : 버전 컨트롤 시스템



## 주요사항

### (1) git은 폴더를 기준으로 프로젝트(코드)를 관리한다.

### (2) git init

* 현재 폴더에서 코드 관리를 시작(init)한다.

* .git 폴더 생성 : git으로 폴더 관리되고 있다.
* .git 폴더 삭제 : git으로 폴더 관리를 중지한다. ( rm -rf .git/ )

### (3) git status (**)

* 현재 상태를 보여준다.

``` branch master ( master )
On branch master ( master 브랜치에 있음 )

No commits yet ( 아직 commit 없음 )

nothing to commit (create/copy files and use "git add" to track)
( commit 할게 없음 )
```

* 새로운 파일이 생성된 경우

``` On branch master
On branch master ( master 브랜치에 있음 )

No commits yet ( 아직 commit 없음 )

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt

nothing added to commit but untracked files present (use "git add" to track)
```

### (3) git add + 파일명

* 버전을 만들 ( commit을 할 또는 스냅샷을 찍을 ) 파일을 추가
*  git add 이후 git status

``` On branch master
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt
```

### (4) git commit

* 버전을 만듬( commit, snapshot )
* message를 필수적으로 입력해야 한다. commit할 때 메세지를 넣어주면 된다. ( git commit -m "message" 사용 ) 그렇지 않으면 새로 열린 장업창에서 esc 3회 이상 누른후 :q 또는 :q!를 이용해서 작업창에서 나온다.

### (5) git log

* 현재까지의 스냅샷을 확인 할 수 있다.
* 이메일 설정 : git config --global user.email "이메일"
* 이름 설정 : git config --global user.name "이름"

---

## 반복작업

### (1) 기존 파일에  내용 추가

* a.txt파일에 hello 라는 내용 추가
* git status로 확인

``` On branch master
On branch master
Changes not staged for commit: (commint 하기 위해 변화들이 git에 추가되지 않음)
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)

```

* 내용이 변경 되었을 경우
  * git add 텍스트명.확장자
* 커밋
  * git commit -m "텍스트 텍스트명.확장자"
* 커밋 확인
  * git log ( commit 내용 전부 확인 )
  * git log --oneline ( commit 내용 한줄로 확인 가능 )
* 특정 커밋단계로 넘어갈 경우
  * git checkout 커밋앞에 있는 노란 별칭 ( 내용을 건드리면 안됨 )
* 되돌아 오기
  * git checkout master ( 원래 작업하던 커밋상태로 돌아옴 )



# 원격저장소

### (1) git remote add + 저장소의 이름 + 저장소의 URL

* 저장소의 이름 : origin
* git remote add origin https://github.com/lby5293/TIL.git

### (2) git remote -v

* 원격 저장소의 정보 출력

### (3) git push origin master

* origin이라는 저장소에 master 브랜치를 업로드

### (4) git remote remove + 저장소이름



## 실습2 - http://bit.do/01_TIL

> 01_TIL.md 파일 작성 후 add,commit,push를 통해 github에 올리기