# TIL
Today I Learned/오늘 배운것
1. 프로그래밍 언어란?

프로그램: 컴퓨터가 수행할 명령어들의 집합.
프로그래밍 언어: 사람이 작성한 명령을 컴퓨터가 이해할 수 있도록 번역하는 도구.
프로그래머: 프로그램을 만드는 사람.

계산적 사고방식: 문제를 부분적으로 나눠서, 각요소 별로 작업을 시키기위한 패턴인식, 디자인 의 사고방식
->논리적 문제 해결 능력과 창의력을 기를 수 있다.

2. 파이썬(Python) 소개
1991년 귀도 반 로섬이 개발.
장점:
-문법이 간단하고 직관적 → 초보자 친화적.
-다양한 분야 활용 (웹, 데이터 분석, AI, 자동화 등).
-풍부한 라이브러리와 다양한 플랫폼 지원.

3. 파이썬 기초 실습
IDLE 실행: 윈도우 시작 메뉴 → "IDLE".

대화형 모드(쉘): >>> 프롬프트 뒤에 코드 입력 → 결과 즉시 출력.

스크립트 모드: .py 파일 작성 후 실행.

예시
print("Hello, World!")   # 출력
"강아지" + "고양이"      # 문자열 연결 → "강아지고양이"
"반가워요" * 3          # 문자열 반복 → "반가워요반가워요반가워요"

<어떤 언어에서든 문자열 "100"과 정수 100은 다름>

4. 터틀 그래픽 (그림 그리기)

거북이 모양으로 선을 그려주는 라이브러리.

주요 명령어:

import turtle as t
t.shape("turtle")
t.forward(100)   # 앞으로 전진
t.left(90)       # 왼쪽으로 90도 회전
t.circle(50)     # 반지름 50짜리 원
t.done()         # 그림창 종료


[실습 예제]
사각형, 원, 자동차, 컬러 패턴 등 다양한 도형 그리기.

5. 오류 다루기
문법 오류 (SyntaxError): 잘못된 코드 작성.

예: pront("Hello")
실행 오류 (RuntimeError): 실행 중 발생.

예: "안녕" + 3 → TypeError.


[파이썬 코딩순서와 소스 형태]

1. 긴 프로그램 실행 방법
.py 파일을 실행할 때 창이 바로 닫히지 않게 하려면:

터틀 그래픽 사용 시 → t.done()
일반 프로그램 → input() (사용자가 엔터를 눌러야 종료됨)

2. 프로그램 코딩 순서

IDLE에서 새 파일 작성 (File → New File).

.py 확장자로 저장.
[Run → Run Module] 실행.
결과 확인 후 오류 수정.

3. 기본 프로그램 구조 (예시)
# 출력
print("안녕하세요")

# 입력
name = input("이름을 입력하세요: ")
print("반가워요,", name)

# 반복문
for i in range(5):
    print(i)

[터틀 라이브러리 사용법]

1. 터틀 모듈 불러오기 (3가지 방법)
import turtle as t     # t.forward() 형태로 사용
import turtle          # turtle.forward() 형태로 사용
from turtle import *  # forward() 형태로 직접 사용

2. 기본 예제
import turtle as t
t.shape("turtle")              # 거북이 모양 커서
t.color("red", "yellow")       # 펜색=빨강, 채우기색=노랑
t.begin_fill()

while True:
    t.forward(200)
    t.left(170)
    if abs(t.pos()) < 1:       # 원점 근처로 돌아오면 반복 종료
        break

t.end_fill()
t.done()

→ 다각형 겹치며 예쁜 별꽃 모양 패턴 생성.

3. 주요 메소드 

showturtle() : (0,0) 위치에서 시작, 기본 방향은 오른쪽.
shape("turtle/arrow/circle/square/triangle/classic")
width(px) : 선 굵기 지정.
speed(n) : 그리는 속도.
bgcolor("색상") : 배경색 변경.
color("펜색"), fillcolor("채울색")
또는 color("펜색","채울색")
begin_fill(), end_fill() : 도형 내부 색 채우기.
clear() : 화면 지우기.
reset() : 초기화.
forward(n) / fd(n) : 앞으로 n픽셀.
backward(n) / bk(n) : 뒤로 n픽셀.
right(각도) / rt(각도) : 오른쪽 회전.
left(각도) / lt(각도) : 왼쪽 회전.

setheading(각도) : 펜의 방향 지정
(0=동, 90=북, 180=서, 270=남).
write("문자열", font=("글꼴",크기,"bold/italic")) : 글자 출력.
up() / down() : 펜 들어올리기 / 내리기.
goto(x,y) : 좌표 이동.
circle(r, extent, steps) : 원 그리기
circle(100) → 반지름 100 원
circle(100, steps=3) → 삼각형
circle(100, steps=4) → 사각형
undo() : 직전 작업 취소.
