## IPython & Jupyther 이란?

### IPython
python + shell 이라고 생각하면 된다. 프롬프트내에서 쉘 명령어가 가능하기 때문에 디렉토리 내에 있는 파일을 참조하면서 프로그래밍이 가능하다.

### Jupyet notebook
대화형 기술 문서를 작성하기 위한 싱글 유저를 위한 제품이다. 40개 이상의 언어를 제공하며, 노트북 공유(Dropbox, Github, Jupyter Notebook Viewer), 실시간 대화형 위젯, 빅데이터 통합(Spark 연동) 등 기능이 있다.


## python의 도움말과 문서
### help(len)
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/1.png)

len 명령어에 대해 설명해줌. 괄호안에 궁금한 명령어 넣으면 됨

### len?
![2.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/2.png)

명령어 관련 정보를 접근하는 단축키로 뒤에 ?를 붙이면 된다.

![3.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/3.png)

자신이 선언한 객체나 함수, 변수에 대해서도 문서를 제공한다.

![4.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/4.png)

docstring을 위처럼 선언도 가능

### <TAB> 자동 완성 기능

![5.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/5.png)

![6.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/6.png)

객체 내용의 탭을 자동완성시켜준다. 정보가 부족할경우 관련 정보를 던져준다.

### (*)을 이용한 검색
![7.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/7.png)

*은 빈문자열을 대신 채워 검색해준다.

## 단축키

### 탐색 단축키
| 키 입력            | 동작                       |
| ------------------ | -------------------------- |
| ctrl + a           | 커서를 줄의 맨 앞으로 옮김 |
| ctrl + e           | 커서를 줄의 맨 뒤로 옮김   |
| ctrl + b	(or →) | 커서를 한 글자 뒤로 옮김   |
| ctrl + f	(or ←) | 커서를 한 글자 앞으로 옮김 |


### 텍스트 입력 단축키
|키 입력	|동작|
| ------------------ | -------------------------- |
|백스페이스 키	|커서의 이전 문자 삭제|
|Ctrl + d	|커서의 다음 문자 삭제|
|Ctrl + k	|현재 커서 위치에서 그 줄 마지막까지 텍스트를 잘라냄|
|Ctrl + u	|그 줄의 처음부터 현재 커서 위치까지 텍스트를 잘라냄|
|Ctrl + y	|이전에 잘라냄 텍스트를 끌어당김(yank, 즉 붙여넣기를함)|
|Ctrl + t	|앞의 두글자의 위치를 바꿈|

### 명령어 이력 단축키
|키 입력		|동작|
| ------------------ | -------------------------- |
|Ctrl + p(또는 ↑)	|이력에서 이전 명령어에 접근|
|Ctrl + n(또는 ↓)	|이력에서 다음 명령어에 접근|
|Ctrl + r	|명령어 이력을 역탐색|


### 기타 단축키
|키 입력		|동작|
| ------------------ | -------------------------- |
|Ctrl + l	|터미널 화면을 지움|
|Ctrl + c	|현재 파이썬 명령어를 중단|
|Ctrl + d	|Ipython 션을 종료|



## Ipython 매직 명령어
맨앞에 %기호를 붙여 일반 파이썬 구문을 추가한것을 매직 명령어라 한다.
%을 접두사로 붙인 한라인에만 동작하는 라인 매직, %%을 접두사로 붙인 여러줄에 동작하는 셀 매직이 있다.

### 코드 블록 붙여넣기 : %paste 와 %cpaste
![8.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/8.png)

Ipython 인터프리터에 들여쓰기와 인터프리터 표시자가 포함될 경우 예기치 않은 오류가 발생할 수 있다. 이때 ctrl + v 가 아닌 %paste를 사용하여 붙여 넣어준다.

%cpaste 는 한번에 실행할 한개이상의 코드 뭉치를 복사할 수 있는 멀티라인 대화형 프롬프트를 연다. 마지막줄에 --로 마무리

### 외부 코드 실행 : %run
말그대로 외부 .py 코드를 실행한다. %run <경로/.py파일이름>

### 코드 실행 시간 측정 : %timeit
![9.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/9.png)

뒤에 한 줄의 파이썬 문장의 실행 시간을 자동으로 측정한다.
%%timeit 을 사용하면 여러줄도 가능!

### 매직 함수에 관한 도움말 : %magic, %lsmagic
%magic은 사용 가능한 매직 함수의 일반적인 설명을 몇가지 예제와 보고 싶을때, %lsmagic은  사용 가능한 모든 매직 함수의 목록만 간단히 보고 싶을때 사용한다.


## 입력/출력 이력
### print(_)
이전에 출력된 값을 출력한다. _이 두개 일경우 두번 이전의 값, 세번까지 가능하다.

### 출력값 숨기기, 세미콜론(;)
세미콜론을 붙이면 출력값이 나오지 않는다. Out 딕셔너리에도 저장되지 않는다.

### 여러 이력 조회 %history
![10.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/10.png)

## Ipython과 셸 명령어

### !명령어
쉘 명령어 앞에 !를 붙이면 쉘 명령을 실행할 수 있다. 인터프리터와 쉘을 왔다갔다 하지 않아도 되는 장점이 있다.

### 에러 제어 : %xmode
![11.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/11.png)

![12.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Ipython%26Jupyter/12.png)

%xmode 는 단일 인수로 그 모드를 취하며, 모드 값으로는 Plain, Context, Verbose를 받을 수 있다.

### 디버깅 : %debug
up, down으로 가르키는 라인을 바꿀수 있음, 종료시 quit

자동으로 디버거가 실행되기를 바란다면 %pdb on 을 입력하면 된다.

### 코드 프로파일링 및 시간 측정
%time
단일 문장의 실행 시간을 측정
%timeit
단일 문장을 반복 실행해 더 정확하게 실행 시간을 측정
%prun
프로파일러로 코드를 실행할
%lprun
라인 단위 프로파일러로 코드를 실행
%memit
단일 문장의 메모리 사용량을 측정
%mprun
라인 단위 메모리 프로파일러로 코드를 실행

prun ~ mprun은 기본적으로 포함되어 있지 않으므로 line_profiler와 memory_pofiler 확장 모듈을 설치해야 한다.
