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

### 12월 25일 : CH4 세상에 선보이는 파이보 서비스!
- 깃으로 버전 관리하기
- 깃허브 사용해 보기
- 파이보를 위한 서버 운영 방법 알아보기
- AWS 라이트세일 사용해 보기
- 세상에 파이보 공개하기

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

### 파이참 설치
- 윈도우용 파이참 설치 : https://www.jetbrains.com/ko-kr/pycharm/download/#section=windows
```python
<Professional>과 <Community> 중 무료 버전인 <Community>를 선택하자. 파이참 설치 파일을 내려받은 후 설치를 진행하자.
설치할 때 특별히 주의할 점은 없으므로 끝까지 <Next>를 선택하여 설치하면 된다.
```
![](/img/파이참설치01.png)

### 파이참 실행하기
```python
[윈도우 키]를 누르고 프로그램 목록에서 [JetBrains → PyCharm Community Edition]을 선택하면 파이참이 실행된다. 파이참을 처음 실행하는 독자라면 다음과 같은 설정 창이 나타날 것이다.
테마, 플러그인 등의 옵션은 기본값으로 선택하고 넘어가자.
필자는 책에 담을 화면을 갈무리하고자 다음과 같이 바탕이 흰색인 Light 테마를 설정했다.
```

![](/img/파이참설치02.png)

```python
이어서 다음과 같은 창이 나오면 두 번째 메뉴인 <Open>을 선택하여 
앞에서 우리가 생성한 장고 프로젝트인 C:/projects/mysite를 선택하자.
```

![](/img/파이참설치03.png)

```python
여기까지 문제없이 진행했다면 다음과 같이 파이참이 정상으로 실행된다.
```

![](/img/파이참설치04.png)

```python
처음 프로젝트를 만들면 mysite 디렉터리 안에 main.py 파일이 자동으로 생성될 수 있다.
파일이 있다면 삭제 후 실습을 진행하자.
```

### 파이참 인터프리터 설정하고 개발 서버 한글로 실행하기
```python
파이참으로 장고 프로젝트를 불러온 후 가장 먼저 해야 할 일은 장고 프로젝트가 바라봐야 할
파이썬 인터프리터 위치를 설정하는 것이다.
```

### 현재 파이썬 인터프리터 위치 확인하기
```python
파이참 메뉴에서 [File → Settings]를 눌러 설정 창을 열고 [Project: mysite → Project Interpreter]를 순서대로 눌러 파이썬 인터프리터 위치를 설정할 수 있는 창을 열자. 
그런 다음 오른쪽 위에 보이는 Python Interpreter를 보자. 
아마도 파이썬을 설치한 디렉터리로 설정되어 있을 것이다.
```

![](/img/파이참설치05.png)

### 파이썬 인터프리터 위치를 가상 환경 위치로 수정하기
```python
하지만 지금은 가상 환경을 사용하므로 파이썬 인터프리터 위치를 가상 환경 위치로 수정해 야 한다. 
다음처럼 Python Interpreter 오른쪽에 보이는 톱니바퀴 모양 아이콘을 누른 다음 <Add>를 누르자.
```

![](/img/파이참설치06.png)

```python
톱니바퀴 모양 아이콘이 가려져 있으므로 그림 참고 시 주의!
```

```python
다음처럼 파이썬 인터프리터 위치를 설정할 수 있는 'Add Python Interpreter' 창이 나타난다. 
여기서 <Existing environment>를 누른 다음 Interpreter 오른쪽에 보이는 <...>을 누르자.
```

![](/img/파이참설치07.png)

```python
그리고 다음처럼 C:/venvs/mysite/Scripts/python.exe를 선택한 후 <OK>를 누른다.
```

![](/img/파이참설치08.png)

```python
나머지 창도 를 눌러 설정을 마치면 파이참이 mysite 가상 환경에 있는 파이썬 인터프리터를 인식하기 시작한다.
```

### 파이참에서 settings.py 파일 수정하기
```python
이제 파이참으로 장고를 개발할 준비가 완료되었다. 
장고 개발을 맛보는 차원에서 장고의 설정값이 들어 있는 settings.py 파일을 수정해 보자.
파이참에서 settings.py 파일을 열어 LANGUAGE_CODE와 TIME_ZONE 설정값을 수정하자.
LANGUAGE_CODE를 en-us에서 ko-kr로 수정하고
TIME_ZONE을 UTC에서 Asia/Seoul로 수정했다. 언어와 시간을 한국 값으로 바꾼 것이다.
```
- 파일이름: C:/projects/mysite/config/settings.py
```python
(... 생략 ...)
# ---------------------------------- [edit] ---------------------------------- #
LANGUAGE_CODE = 'ko-kr'

TIME_ZONE = 'Asia/Seoul'
# ---------------------------------------------------------------------------- #
(생략)
```

### 개발 서버 다시 구동하기
```python
앞의 실습을 잘 진행했다면 개발 서버가 종료된 상태이다. 개발 서버를 다시 구동하자.
localhost:8000으로 접속하면 초기 화면이 영어에서 한글로 바뀌어 있다.
python manage.py runserver로 서버 구동!
```

![](/img/파이참설치09.png)

## 12월 22일 : CH2 장고의 기본 요소 익히기
### 2-01 주소와 화면을 연결하는 URL과 뷰 

### 앱 생성하고 확인하기
```python
1장에서 mysite 프로젝트를 생성했다. 
프로젝트에는 장고가 제공하는 기본 앱과 개발자(여러분)가 직접 만든 앱이 포함될 수 있으며,
장고에서 말하는 '앱'은 안드로이드 앱과 성격이 다르다고 언급했다. 
그러면 장고의 앱이란 정말로 무엇일까? 우리의 파이보 서비스에 필요한 pybo 앱을 만들어 보며 알아보자.
```

### pybo 앱 생성하기
```python
명령 프롬프트에서 django-damin의 startapp 명령을 이용하여 pybo 앱을 생성하자.
```
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>django-admin startapp pybo
(mysite) C:\projects\mysite>
```

### 생성된 앱 확인하기
```python
1단계를 진행하면 아무런 메시지가 나타나지 않을 것이다. 
하지만 파이참에서 다음의 프로젝트 디렉터리 목록을 살펴보면 
pybo라는 이름의 디렉터리가 생성되었음을 확인할 수 있다.
```

![](/img/파이참설치09.png)

[pybo 디렉터리를 펼친 모습]
```python
> 모양으로 되어 있는 디렉터리는 디렉터리가 접혀 있는 상태를 의미하며,
디렉터리 이름을 더블클릭하면 디렉터리가 펼쳐진다.

__init__.py, admin.py, apps.py 같은 파일이 바로 pybo 앱을 위한 것이다. 
이 파일들은 실습을 진행하며 작성 또는 수정할 것이다.
```

### 안녕하세요 파이보?
```python
지금부터 실습을 시작해 보자. 실습을 진행하면 파이보 서비스가 조금씩 완성될 것이다. 
여기서 필자가 여러분에게 한 가지 부탁하고 싶은 것이 있다. 
결과를 보기 위해 실습을 무작정 따라 하지 않길 바란다. 
결과를 보고 싶은 조급한 마음은 이해하지만, 결과가 나온 이유를 명확하게 이해하면서 
따라 해야 좋은 개발자가 될 수 있다.
```

### 개발 서버 구동하기
개발 서버를 구동하자.
- 명령 프롬프트
```python
(mysite) C:\projects\mysite> python manage.py runserver
```

### localhost:8000/pybo에 접속하기
```python
우리는 아직 아무런 작업도 하지 않았다. 하지만 그냥 웹 브라우저 주소창에 다음을 입력하여 접속해 보자. 
앞으로 이 과정을 '페이지를 요청한다' 또는 localhost:8000을 생략하여 '/pybo/를 요청한다'라고 할 것이다.
```
- 상세 내용
```python
localhost:8000/pybo
```

###  오류 메시지 확인하기
그러면 'Page not found (404)' 오류 페이지가 보인다.

![](/img/page.error.png)

[웹 브라우저에서 볼 수 있는 Page not found (404) 화면]

```python
명령 프롬프트에도 같은 오류가 보인다.
```
![](/img/cmd.error.png)

명령 프롬프트에서 볼 수 있는 Page not found (404) 화면
```python
404는 HTTP 오류 코드 중 하나로, 사용자가 요청한 페이지를 찾을 수 없는 경우 발생하는 오류이다. 
장고는 오류 발생 시 오류 원인을 웹 브라우저 또는 명령 프롬프트에 자세히 보여 준다.

이 오류는 왜 발생했을까? 장고는 사용자가 웹 브라우저에서 /pybo/라는 페이지를 요청하면 해당 페이지를 가져오는 URL 매핑이 있는지 
config/urls.py 파일을 뒤져 찾아본다. 
그런데 아직 /pybo/ 페이지에 해당하는 URL 매핑을 장고에 등록하지 않았다. 
그래서 장고는 /pybo/ 페이지를 찾을 수 없다고 메시지를 보낸 것이다.
```

### config/urls.py 수정하기
```python
그럼 이제 할 일은 정해졌다.
장고가 사용자의 페이지 요청을 이해할 수 있도록 
config/urls.py 파일을 수정하자. 앞으로 이를 'URL 매핑을 추가한다'고 말할 것이다. 
URL 매핑을 추가하기 위해 config/urls.py 파일을 수정하자.

- config/urls.py 파일은 페이지 요청 시 가장 먼저 호출되며, 요청 URL과 뷰 함수를 1:1로 연결해 준다.
- 뷰 함수는 아직 살펴보지 않았다. 뷰 함수는 화면을 보여 주기 위한 함수로, views.py에 있는 함수다. 이 함수도 곧 공부할 것이다.
```
- 파일이름: C:\projects\mysite\config\urls.py
```python
from django.contrib import admin
from django.urls import path
# ---------------------------------- [edit] ---------------------------------- #
from pybo import views
# ---------------------------------------------------------------------------- #

urlpatterns = [
    path('admin/', admin.site.urls),
# ---------------------------------- [edit] ---------------------------------- #    
    path('pybo/', views.index),
# ---------------------------------------------------------------------------- #    
]
```
코드의 urlpatterns 변수를 보면 path 함수를 사용하여 pybo/ URL과 views.index를 매핑했다. 
views.index는 views.py 파일의 index 함수를 의미한다. 장고는 이런 식으로 URL과 뷰 함수를 매핑했다.

![](/img/연결.png)