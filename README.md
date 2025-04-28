# git

## 1. git 프로그램 설치

- 프로그램 다운로드 : https://git-scm.com/
- 64-bit git for window setup 설치

## 2. git 버전 확인

- 윈도우 키보드 + R 키보드 : `cmd` 입력

```bash
    git --version
```

- 출력창 확인

## 3. VSCord 에 git 설정하기

### 3.1. 터미널 환경을 git bash 로 설정하기

- 윈도우, 맥, 리눅스 의 명령창을 통일하기 위함.
- 관리도구 선택 > 설정메뉴 선택
- 설정화면 > `default:windows` 입력
- `git bash` 선택
- 설정화면 닫고, VSCord 재실행 추천

### 3.2. VSCord 에서 git 옵션 설정하기

- 터미널 실행 : `CTRL + 백틱` 추천

- git 버전 확인

```bash
git --version
```

- 기본 브랜치명을 `main` 으로 설정

```bash
git config --global init.defaultBranch main
```

- 윈도우, 맥, 리눅스 환경에서 Enter 키 처리를 통일함.

```bash
git config --global core.autocrlf true
```

- git commit 명령을 VSCord 에서 작성하도록 설정

```bash
git config --global core.editor "code --wait"
```

- git 사용자 아이디 설정하기

```bash
git config --global user.name "아이디"
```

- git 사용자 아이디 확인하기

```bash
git config --global user.name
```

-- git 사용자 이메일 저장하기

```bash
git config --global user.email "이메일"
```

- git 사용자 이메일 확인하기

```bash
git config --global user.email
```

## 4. git 작업하기 (실습)

### 4.1. git 프로젝트 관리 초기화 하기

```bash
git init
```

### 4.2. git 현재 상태 파악하기

```bash
git status
```

### 4.3. git 현재 수정된 내용, 파일, 폴더 등을 저장하기

- 원하는 파일만 저장하기

```bash
git add README.md
```

- 모든 파일 및 폴더 저장하기(추천)

```bash
git add .
```

### 4.4. 수정 내역 남기기

- 한줄 작업 메모

```bash
git commit -m "깃 작업 관련 설명글 작성"
```

- 여러줄 메모 (제목, 상세내용)

```bash
git commit
```

### 4.5 커밋 내용 컨벤션 알아보기

```bash
[커밋타입]: 커밋 메시지 (옵션)
```

- 커밋타입 : 작업의 분류
- 옵션 : 이슈 또는 수정이 된 작업커밋 번호 또는 추가정보
- 커밋 메시지 : 무엇을 했는지 짧은 내용

#### 4.5.1. 커밋타입

- `[fart]` : 새로운 기능 추가
- `[fix]` : 버그 수정
- `[docs]` : 문서 수정(README.md)
- `[style]` : 코드의 스타일 변경(띄어쓰기, 세미콜론 등)
- `[refector]` : 코드 리팩토링(기능 변경, 코드 정리 등)
- `[test]` : 테스트 코드 추가
- `[chore]` : 기타 (빌드 설정, 패키지 업데이트 등)

#### 4.5.2. 옵션

- 만약 `회원가입 로그인 기능 추가` 라면

- 아래는 이슈 #23 번을 해결하고 기능을 추가했다는 것

```
[feat]: 회원가입 로그인 기능 추가 (#23)
```

#### 4.5.3. 커밋 내용

- Entor 키를 기준으로 제목과 내용을 구분합니다

```
[docs] : 커밋 제목

커밋 상세내용 작성
```

### 4.6. 커밋 내용 확인하기

- 기존의 commit 된 내용을 확인하기

- 상세보기

```bash
git log
```

- 간략하게 보기

```bash
git log -oneline
```

- 하나의 commit 상세보기

```bash
git show 커밋아이디
```

### 4.6.1. 각 항목 관련 사항 이해하기

- commit : 고유한 커밋 번호 (아이디)
- autor : 작성자
- date : 날짜
- 메세지 : 상세 내용

### 4.7. 브랜치 작업 해보기

- `나뭇가지` 라는 의미로 원 줄기로부터 파생되는 것을 말함
- 원 `소스`로부터 파생한 새롭게 `분기한 소스` 관리를 말함
- 브랜치를 생성시에는 add와 commit이 완료되어야

#### 4.7.1. 브렌치 생성하기

```bash
git add .
git commit -m "[docs]:브랜치 실습 test 생성하기"
git branch test
```

#### 4.7.2. 브렌치 목록보기

```bash
git branch -v
```

#### 4.7.3. 브렌치 이동하기

```bash
git switch test
```

#### 4.7.4. 브렌치 삭제하기

```bash
git branch -D test
git branch -v
```

#### 4.7.5. 브렌치 합치기

- 브랜치를 하나로 합쳐주기

- 주의사항 : `main 브랜치에서 test 브랜치를 합쳐줄 겁니다`

```bash
git merge 합쳐주고자 하는 브랜치명
```

### 4.8. git 브랜치 충돌 해결해보기

- git 브랜치를 nerge 하면 많이 발생합니다
- 나는 `main`에서 계속 작업을 하고 있다
- `login 브랜치`에서 나는 로그인 기능을 구현했다

# github

## 1. GitHub 회원가입하기

- https://github.com

## 2. GitHub 프로젝트(Repository) 생성하기

- 만약 til_git 프로젝트 생성해다면 GitHub 에도 동일하게 생성하자
- public 으로 셋팅 : 외부로 소스 공개
- description 은 작성해주자 : 프로젝트 설명

## 3. github 인증하기

### 3.1. 무조건 github 에 로그인 된 상태로 시도하셔야 합니다

### 3.2. `윈도우 > 자격 증명 관리자 > windows 자격 증명` 에서 github 확인

- 새로 생성하길 권장합니다
- PC 정리 또는 자리 이동시 반드시 삭제하셔야 합니다

## 4. github 프로젝트 연결하기

### 4.1. 원격 저장소 주소 지정하기

- `remote` 는 원격(인터넷) 을 말합니다
- `add` 는 추가하라
- `origin`
  - http 주소를 간략하게 별칭을 준 것 입니다
  - 단어는 마음대로 하셔도 되요
  - `원격 이름`을 말함

```bash
git remote add origin https://github.com/dagongim/til_git.git
```

### 4.2. 원격 저장소 목록 보기

```bash
git remote -v
```

### 4.3. 원격 저장소에 소스 등록하기

- 습관적으로 하셨으면 좋은 작업 (ctrl + s, 즉, 저장 후)

```bash
git add .
git commit -m "[docs]:최초등록"
```

- 소스 업로드를 `push 한다` 라고 합니다

```bash
git push -u origin main
```

- `-u` 옵션을 붙이셨다면 이후로는 `git push` 만 하면 됨

### 4.4. 원격 저장소 관리하기

- 목록 보기

```bash
git remote -v
```
