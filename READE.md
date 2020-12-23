# 웹사이트 배포
## (참고:점프 투 장고:https://wikidocs.net/book/4223)

# 날짜
### 12월 17일
점프 투 장고를 이용해 LightSail 로 웹사이트 배포 계획 수립
### 12월 18일
점프 투 장고 공부 ,조언,회의
### 12월 19일 : CH1 장고 개발 준비
- 파이썬 설치하기
- 장고 개발 환경 준비하기
- 장고 프로젝트 생성하기
- 파이참 설치하고 장고 개발 서버 실행하기
### 12월 22일 : CH2 장고의 기본 요소 익히기
- 주소와 화면울 연결하는 URL 과 뷰
- 데이터를 관리하는 모델
- 개발 편의를 제공하는 장고 Admin
- 질문 목록과 질문 상세 기능 구현하기
- URL 더 똑똑하게 사용하기
- 답변 등록 기능 만들기
- 스태틱 화면 예쁘게 꾸미기
- 부트스트랩으로 더 쉽게 화면 꾸미기
- 표준 HTML 과 템플릿 상속 사용해 보기
- 질문 등록 기능 만들기
### 12월 23일 : CH3 파이보(저는 Hello) 서비스 개발
- 내비게이션 기능 추가하기
- 게시판 페이징 기능 추가하기
- 템플릿 필터 직접 만들어 보기
- 질문에 달린 답변 개수 표시하기
- 로그인 로그아웃 구현하기
- 회원가입 구현하기
- 모델에 글쓴이 추가하기
- 글쓴이 표시하기
- 게시물 수정 & 삭제 기능 추가하기
- 댓글 기능 추가하기

# 추가된 소스코드
## 12월 19일(금일 추가된 모든 소스코드는 CMD 에서 실행하셔야 합니다.)
- 파이선 설치(link:http://www.python.org/downloads/)
- 가상환경(venvs) 디렉토리 생성(CMD) 

주의! - 밑에 보이는 경로는 제 PC 환경에 맞춰서 짠 경로입니다.각자 PC마다 경로가 다를 것입니다.
```python
C:\Users\user\cd
C:\>mkdir venvs
C:\>cd venvs
C:\venvs>
```
- 파이썬 가상환경을 만들어 주는 명령어 수행
```python
C:\venvs>python -m venv mysite
```
- mysite 가상환경으로 진입
```python
C:\venvs>cd C:\venvs\mysite\Scripts
C:\venvs\mysite\Scripts> activate
(mysite) C:\venvs\mysite\Scripts>
```
- 장고 설치(pip install django : 장고를 설치하라는 명령어입니다.)
```python
(mysite) C:\venvs\mysite\Scripts> pip install django
```
- pip 업그레이드
```python
WARNING: You are using pip version 19.2.3, however version 20.0.2 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.
```
장고를 설치하면 저런문구가 보일겁니다. pip가 최신 버전이 아니라는 내용입니다. pip를 업그레이드해줍시다.
```python
(mysite) C:\venvs\mysite\Scripts> python -m pip install --upgrade pip
```
pip도 최신버전으로 잘 설치가 되었습니다.
## 12 월 22일
- 명령 프롬폼트는 CMD 안에서 작성해 주시기 바랍니다.
- 코드 실행시 정확한 경로에서 실행하셔야 합니다.
### 프로젝트 디렉터리
프로젝트 루트 생성하기(C 드라이브에 프로젝트를 담을 루트 디렉터리를 생성)
- 명령 프롬프트
```python
C:\Users\user\cd \
C:\>mkdir projects
C:\>cd projects
C:\projects>
```
### 프로젝트 루트 디렉터리 안에서 가상 환경 진입하기
프로젝트 루트 디렉터리 안에서 다음 명령어를 입력해 앞에서 만든 mysite 가상 환경에 진입
- 명령 프롬프트
C:\projects>C:\venvs\mysite\Scripts\activate
(mysite) C:\projects>
### 장고 프로젝트를 담을 디렉터리 생성하고 이동하기
장고 프로젝트를 담을 mysite 디렉터리를 생성하고 이동
- 명령 프롬프트
```python
(mysite) C:\projects>mkdir mysite
(mysite) C:\projects>cd mysite
(mysite) C:\projects\mysite>
```
### 장고 프로젝트 생성하기
```python
mysite 디렉터리에서 django-admin이라는 도구로 장고 프로젝트를 생성

config 다음에 점 기호(.)가 있음. 점 기호 : ‘현재 디렉터리를 프로젝트 디렉터리로 만들라’는 의미입니다.
```
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>django-admin startproject config .
```
### 장고 프로젝트 내용물 확인하기
- 디렉터리 구조와 파일
```python
C:\projects\mysite
├── config/
│      ├─ asgi.py
│      ├─ settings.py
│      ├─ urls.py
│      ├─ wsgi.py
│      └─ __init__.py
└── manage.py
```  
### 개발 서버 구동하고 웹 사이트에 접속해 보기
지금까지 웹 사이트를 생성하였다. 개발 서버를 구동하고 웹 사이트에 접속해 봅시다.
### 개발 서버 구동하기
python manage.py runserver : 개발 서버 구동시키는 명령어
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run ‘python manage.py migrate’ to apply them.
April 21, 2020 - 21:51:03
Django version 3.1.3, using settings ‘config.settings’
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```
```python
개발 서버가 구동된 상태를 유지하고 웹 브라우저를 이용하여 127.0.0.1:8000에 접속해 봅시다.
그러면 장고가 기본으로 만든 웹 사이트 화면을 볼 수 있습니다.
- 개발 서버는 127.0.0.0, 즉 localhost(로컬호스트)로 실행되므로 로컬 서버라 부르기도 합니다.
- 127.0.0.1과 localhost 는 현재 컴퓨터를 가리키는 아이피 주소입니다.
```
### runserver 실행 후 웹사이트 모습
![](/img/runserver.png)
```python
아쉽게도 아직은 개발 서버 환경에서 사이트가 실행되고 있으므로
개발 서버 환경을 실행한 컴퓨터(여러분의 컴퓨터)에서만 사이트에 접속할 수 있습니다.
```
### 개발 서버 종료하기
- <Ctrl+C> 를 눌러 개발 서버를 종료해 봅시다.

![](/img/End.png)

### 로컬 아이피 주소로 다른 사람이 접속할 수 없는 이유
```python
앞에서 ‘아직은 여러분이 만든 사이트에 다른 사람이 접속할 수 없다’라고 말씀드렸습니다. 
다른 사람이 여러분이 만든 사이트에 접속하려면 localhost나 127.0.0.1이라는 로컬 아이피 주소가 아닌 
15.165.210.240 과 같은 인터넷 세상 속의 아이피 주소 또는 Hello.kr과 같은 도메인이 필요하기 때문입니다. 
로컬 아이피 주소의 ‘로컬’ 은 지역이라는 뜻이며, 이는 곧 ‘ 내 PC’ 를 의미합니다.
4장에서 인터넷 세상 속의 아이피 주소로 여러분이 만든 사이트에 접속하는 방법을 소개하겠습니다.
```
### mysite 가상 환경에 간단히 진입하기
```python
mysite 가상 환경에 진입하려면 매번 명령 프롬프트를 실행하고 C:/venvs/mysite/Scripts 디렉터리로 
이동하여 activate 명령을 수행해야 합니다.
이런 일련의 과정을 한 번에 수행할 수 있는 배치 프로그램을 만들어 귀찮음을 덜어 봅시다.
```
### mysite.cmd 배치 파일 생성하기
```python
mysite.cmd 파일을 venvs 디렉터리에 만들고 다음과 같이 작성하여 저장하자. 확장자 .cmd가 붙은 파일은 배치(batch) 파일이라 부르며,
명령어 입력과 실행을 한 번에 해주는 파일이라 생각하면 된다.
```
- 파일 이름 : mysite(메모장으로 작성하셔도 됩니다.)
- 파일 경로 : C:/venvs/mysite.cmd]
- 파일 안에 들어가야할 코드
- 파일 내용 : c:\Users\user\projects\mysite 디렉터리로 이동한 다음, C:/venvs/mysite/scripts/activate 명령을 수행하라
```python
@echo off
@cd c:\Users\user\projects\mysite
@c:\Users\user\venvs\mysite\scripts\activate
```
경로는 제 pc에 맞춰서 코딩한 것이므로 여러분은 여러분 pc 경로에 맞춰서 코드를 작성해 주세요.
### 배피 파일 위치를 PATH 환경 변수에 추가하기
```python
이 배치 파일이 명령 프롬프트 어느 곳에서나 수행될 수 있도록 C:/venvs 디렉터리를 시스템의 환경 변수 PATH에 추가해야 합니다. 
먼저 <윈도우키+R> 키를 입력하여 다음처럼 sysdm.cpl 명령을 입력한 다음 확인을 눌러주세요.
```

![](/img/실행.png)

![](/img/시스템속성.png)

![](/img/환경변수.png)

![](/img/환경변수편집.png)

![](/img/환경변수편집2.png)

```python
사진에는 C:/venvs라는 디렉터리를 추가했지만 제 경로는 C:\Users\user\venvs 였습니다.
```
### PATH 환경 변수 확인하기
```python
환경 변수 PATH에 C:\Users\user\venvs 디렉터리가 추가되어 mysite.cmd 명령을 어디서든 실행 할 수 있습니다.
명령 프롬프트를 다시 시작합시다.(변경된 환경 변수 PATH가 제대로 반영) 그리고 set path 명령을 실행하여
변경된 환경 변수 PATH의 내용을 확인해 봅시다. C:\Users\user\venvs 라는 디렉터리가 환경 변수 PATH에 포함되어 있어야 합니다.
```
![](/img/setpath.png)

### 배치 파일 실행하여 가상 환경에 진입하기
```python
mysite 명령(배치 파일 이름)을 실행하여 가상 환경에 잘 진입하는지 확인해 봅시다.
참고로 윈도우에서 확장자가 .cmd인 파일은 확장자를 빼고 입력해도 된다.(안돼면 .cmd써주세요)
```
- 명령 프롬프트: c:\Users\user\projects>mysite.cmd

![](/img/mysite.cmd.png)





