# 웹사이트 배포
## (참고:점프 투 장고:https://wikidocs.net/book/4223)

# 날짜
### 12월 17일
점프 투 장고를 이용해 LightSail 로 웹사이트 배포 계획 수립
### 12월 18일
점프 투 장고 공부 ,조언,회의
### 12월 19일
- 파이썬 설치
- 가상환경(virtualenv) 생성
- 장고 설치
- pip 업그레이드
### 12월 22일
### 프로젝트 디렉터리
- 프로젝트 루트 디렉터리 생성하기
- 프로젝트 루트 디렉터리 안에서 가상 환경에 진입하기
- 장고 프로젝트를 담을 디렉터리 생성하고 이동하기
- 장고 프로젝트 생성하기
- 장고 프로젝트 내용물 확인하기
### 개발 서버 구동하고 웹 사이트에 접속해 보기
- 개발 서버 구동하기
- 개발 서버 종료하기
### mysite 가상 환경에 간단히 진입하기
- mysite.cmd 배치 파일 생성하기
- 배치 파일 위치를 PATH 환경 변수에 추가하기
- PATH 환경 변수 확인하기
- 배치 파일 실행하여 가상 환경에 진입하기


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
### 12 월 22일
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
mysite 디렉터리에서 django-admin이라는 도구로 장고 프로젝트를 생성

config 다음에 점 기호(.)가 있음. 점 기호 : ‘현재 디렉터리를 프로젝트 디렉터리로 만들라’는 의미
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
개발 서버가 구동된 상태를 유지하고 웹 브라우저를 이용하여 127.0.0.1:8000에 접속해 봅시다.

그러면 장고가 기본으로 만든 웹 사이트 화면을 볼 수 있습니다.
- 개발 서버는 127.0.0.0, 즉 localhost(로컬호스트)로 실행되므로 로컬 서버라 부르기도 합니다.
- 127.0.0.1과 localhost 는 현재 컴퓨터를 가리키는 아이피 주소입니다.
### runserver 실행 후 웹사이트 모습

![](/img/runserver.png)