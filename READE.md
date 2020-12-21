# 웹사이트 배포
## (참고:점프 투 장고:https://wikidocs.net/book/4223)

## 날짜
### 12월 17일
점프 투 장고를 이용해 LightSail 로 웹사이트 배포 계획 수립
### 12월 18일
점프 투 장고 공부 ,조언,회의
### 12월 19일
- 파이썬 설치
- 가상환경(virtualenv) 생성
- 장고 설치
- pip 업그레이드

## 추가된 소스 
### 12월 19일(금일 추가된 모든 소스코드는 CMD 에서 실행하셔야 합니다.)
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

