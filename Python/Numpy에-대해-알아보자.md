# Numpy
`import numpy as np`

기본적으로 numpy를 import할땐 별칭인 np를 사용해 임포트한다.

## Numpy 배열의 기초
### 데이터 타입 이해하기
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/1.png)

파이썬 리스트를 토대로 배열을 만든다.

array에선 모든 타입이 같아야 하며, dtype='타입이름' 을 통해 타입을 지정 해줄 수도 있다.

### 배열 만들기
![2.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/2.png)

```zeros(원소개수, (타입)) //값을 전부 0으로 채움```

```ones(원소개수, (타입)) // 값을 전부 0으로 채움```

```full(원소개수, 지정값, (타입))```

`// n차원으로 원소 지정 생성 가능 튜플형식`

`arrange(시작값, 마지막값, 간격)`

![3.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/3.png)

`linespace(시작값, 마지막값, 개수) // 개수만큼 시작값~마지막값 일정 간격으로 생성한다.`

`random(튜플) //튜플(행렬)로 0~1사이 난수 채워서 생성`

`normal(평균, 표준편차, 튜플) //추가로 평균, 표준편차 설정`

`randint(시작값, 마지막값, 튜플) 시작값 ~마지막-1 값 사이로 채운 행렬 생성`

![4.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/4.png)

`eye(정수값) //정수값 * 정수값의 단위행렬을 생성`

`empty(정수값) // 정수값의 크기를 가지는 초기화되지 않은 배열 만들기. 초기화 되지 않은 메모리값으로 채워져 있음`

### Numpy 표준 데이터 타입
|Data type		|Description|
| ------------------ | -------------------------- |
|bool_		|Boolean (True or False) stored as a byte|
|int_		|Default integer type (same as C long; normally either int64 or int32)|
|intc		|Identical to C int (normally int32 or int64)|
|intp		|Integer used for indexing (same as C ssize_t; normally either int32 or int64)|
|int8		|Byte (-128 to 127)|
|int16		|Integer (-32768 to 32767)|
|int32		|Integer (-2147483648 to 2147483647)|
|int64		|Integer (-9223372036854775808 to 9223372036854775807)|
|uint8		|Unsigned integer (0 to 255)|
|uint16		|Unsigned integer (0 to 65535)|
|uint32		|Unsigned integer (0 to 4294967295)|
|uint64		|Unsigned integer (0 to 18446744073709551615)|
|float_		|Shorthand for float64|
|float16	|Half precision float: sign bit, 5 bits exponent, 10 bits mantissa|
|float32	|Single precision float: sign bit, 8 bits exponent, 23 bits mantissa|
|float64	|Double precision float: sign bit, 11 bits exponent, 52 bits mantissa|
|complex_	|Shorthand for complex128|
|complex64	|Complex number, represented by two 32-bit floats|
|complex128	|Complex number, represented by two 64-bit floats|

## Numpy 배열 조작 & 사용법
Numpy는 배열을 기반으로 만들어졌다.

### 배열 속성 지정
배열의 크기, 모양, 메모리 소비량, 데이터 타입을 결정한다.

![5.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/5.png)

각 배열은 속성으로 `ndim(차원개수), shape(각 차원의 크기), size(전체 배열 크기)`를 가지고 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/6.png)

이외 유용한 속성으로 배열 데이터 타입인 dtype, 배열 요소 크기를 나타내는 itemsize, 배열 전체크기를 나타내는 nbytes가 있다.

### 배열 인덱싱 : 단일 요소에 접근하기
개별 배열 요소값을 가져오고 설정한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/7.png)

그냥 리스트에 접근하는거처럼 접근 가능하다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/8.png)

다차원 배열은 튜플을 써서 배열 항목에 접근한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/9.png)

원소 값이 정해질때는 array 타입을 따른다.

### 배열 슬라이싱 : 하위 배열에 접근하기
큰 배열 내에 있는 작은 하위 배열을 가져오고 설정한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/10.png)

리스트마냥 쓰면된다. `x[start:stop:step]` 형식이다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/11.png)

세번째 인자를 음수로하면 역으로 나열 된다. default로 1인걸 확인가능.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/12.png)

다차원 배열 역시 튜플로 슬라이싱한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/13.png)

슬라이싱 한것을 다른 변수로 받아서 수정하면 본체에도 영향이 간다.

아마 새로운 array 객체로 슬라이싱한것에 대한 정보를 인스턴스에 저장하는데 같은 주소값을 가르키게 설계된것 같다.

만약 같은 주소값을 가르키는 슬라이싱이 싫다면 copy()함수를 이용할 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/14.png)


### 배열 재구조화
해당 배열의 형상을 변경한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/15.png)

reshape(튜플) 을 이용하여 배열의 꼴을 바꿀수 있다. 물론 배열의 사이즈를 맞추어 줘야한다.

np.newaxis는 슬라이싱과 함께 새로운 행 또는 열을 만드는데 사용된다.

`행 : x[np.newaxis, 슬라이싱]`

`렬 : x[슬라이싱, np.newaxis]`

### 배열 결합 및 분할
여러 배열을 하나로 결합하고 하나의 배열을 여러 개로 분할한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/16.png)

기본적으로 최고차 꼴로 결합이 된다. 1차원이면 1차원꼴로 2차원이면 2차원꼴로

default로 axis=0인데 합칠때 1차원으로 합치고 싶으면 n-1, 2차원으로 합치고 싶으면 n-2, n차원으로 합치고싶으면 0 으로 하면 된다.(n은 차원을 의미한다.)

위에 예제에서는 axis=0일때 4 * 3, 1일때 2 * 6 꼴로 된건 확인 할 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/17.png)

또한 vstack, hstack을 사용하여 수직, 수평으로 혼합된 차원의 배열을 합칠수 있다.

결합과 반대로 분할은, np.split, np,hsplit, np.vsplit 함수로 구현된다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/18.png)

`split(arr, [나눌 경계선 좌표])`

`vsplit(arr, [수평으로 나눌 경계선 좌표])`

`hsplit(arr, [수직으로 나눌 경계선 좌표])`

## NumPy 배열 연산 - 유니버셜 함수
Numpy는 데이터 배열을 사용하여 최적화된 연산을 위한 쉽고 유연한 인터페이스를 제공한다.

이 연산을 빠르게 만드는 핵심은 벡터화 연산을 사용하는 것인데. 일반적으로 Numpy의 유니버셜 함수를 통해 구현된다.

### 루프는 느리다
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/19.png)

백만 번 연산하고 그 결과를 저장하는데 수 초가 걸리다. 휴대전화의 처리 속도도 초당 수십억의 수치 연산(Giga-FLOPS)로 측정되는 상황에서 이것은 터무니 없을 정도로 느려보인다. 이것은 연산 자체에 문제가 있는 것이 아닌 CPython이 루프의 사이클마다 수행해야 하는 타입 확인과 함수 디스패치가 발생하기 때문이다.

### UFuncs
Numpy는 여러 종류의 연산에 대해 이러한 종류의 정적 타입 체계를 가진 컴파일된 루틴에 편리한 인터페이스를 제공한다. 이를 벡터화 연산이라 한다. 벡터화 연산은 간단히 배열에 연산을 수행해 각 요소에 적용함으로써 수행할 수 있다. 이 벡터화 방식은 루프를 Numpy의 기저를 이루는 컴파일 계층으로 밀어 넣음으로써 훨씬 빠르게 수행 되도록 설계했다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/20.png)

s 단위가 ms 단위로 바뀌는걸 눈으로 볼 수 있다.

유니버셜 함수는 매우 유연하여 배열간의 연산, 다 차원 배열의 연산도 가능하다.

### 배열의 산술 연산
파이썬의 기본 산술 연산자를 사용하기 때문에 자연스럽게 표준 덧셈, 뺄셈, 곱셈, 나눗셈 모두 사용할 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/21.png)

이외에도 **, %, // 가 있다.

이는 사용상 편의를 위해 Numpy에 내장된 특정 함수를 감싼 것이다.

| Operator | Equivalent ufunc  | Description                           |
| -------- | ----------------- | ------------------------------------- |
| `+`      | `np.add`          | Addition (e.g., `1 + 1 = 2`)          |
| `-`      | `np.subtract`     | Subtraction (e.g., `3 - 2 = 1`)       |
| `-`      | `np.negative`     | Unary negation (e.g., `-2`)           |
| `*`      | `np.multiply`     | Multiplication (e.g., `2 * 3 = 6`)    |
| `/`      | `np.divide`       | Division (e.g., `3 / 2 = 1.5`)        |
| `//`     | `np.floor_divide` | Floor division (e.g., `3 // 2 = 1`)   |
| `**`     | `np.power`        | Exponentiation (e.g., `2 ** 3 = 8`)   |
| `%`      | `np.mod`          | Modulus/remainder (e.g., `9 % 4 = 1`) |

### 절댓값 함수
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/22.png)

absolute의 별칭인 abs로 사용이 가능하다.

복소수 데이터도 처리 가능하며 이 경우 절대 값은 크기를 반환한다.

### 삼각함수
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/23.png)

np.linespace(시작값, 끝값, 원소수) // 시작값~끝값을 n-1간격으로 n개의 원소 배열을 만들어 반환한다.

### 지수와 로그
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/24.png)

np.expm1(x), np.log1p(x) 처럼 매우 작은 입력값의 정확도를 유지하고자 할 때 쓰는 함수도 있다.

이 함수들은 x가 매우 작을때 np.log, np.exp를 사용했을 때보다 더 정확한 값을 내놓는다.

### 특화된 유니버셜 함수
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/25.png)

ufunc의 서브 모듈인 scipy.special이 있는데 잘 알려지지 않은 수학 함수를 사용하여 데이터를 계산할 수 있다.

### 고급 Ufunc 기능
* **출력 지정**

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/26.png)

* **집계**

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/27.png)

reduce 메서드는 결과가 하나 남을 때까지 해당 연산을 배열 요소에서 반복해서 적용한다.

첫번째 결과는 1 + 2 + 3 + 4 + 5 = 15 이다.

만약 reduce 연산을 할때의 모든 결과 값을 저장하고 싶다면 accumulate를 사용 하면 된다.

* **외적 산출물(Outer products)**

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/28.png)

outer 메서드를 이용해 서로 다른 두 입력 값의 모든 상에 대한 출력값을 계산 할 수 있다.

## 집계: 최소값, 최대값, 그리고 그 사이의 모든 것

### 배열의 값의 합 구하기
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/29.png)

sum 함수, 역시나 numpy에 내장된 함수가 더 빠르다.

또한 np.sum은 다중 배열 차원을 인지한다.

### 최소값과 최대값
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/30.png)

### 다차원 집계
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/31.png)

axis 값이 k이라 했을때 n차원에서 n-k 에서 해당 연산을 지원함 (ex. 2차원에서 min 함수 사용할때 axis=0 : 각 열에 대한 최솟값 반환, axis=1 : 각 해에 대한 최솟값 반환)

| Function Name   | NaN-safe Version   | Description                               |
| --------------- | ------------------ | ----------------------------------------- |
| `np.sum`        | `np.nansum`        | Compute sum of elements                   |
| `np.prod`       | `np.nanprod`       | Compute product of elements               |
| `np.mean`       | `np.nanmean`       | Compute mean of elements                  |
| `np.std`        | `np.nanstd`        | Compute standard deviation                |
| `np.var`        | `np.nanvar`        | Compute variance                          |
| `np.min`        | `np.nanmin`        | Find minimum value                        |
| `np.max`        | `np.nanmax`        | Find maximum value                        |
| `np.argmin`     | `np.nanargmin`     | Find index of minimum value               |
| `np.argmax`     | `np.nanargmax`     | Find index of maximum value               |
| `np.median`     | `np.nanmedian`     | Compute median of elements                |
| `np.percentile` | `np.nanpercentile` | Compute rank-based statistics of elements |
| `np.any`        | N/A                | Evaluate whether any elements are true    |
| `np.all`        | N/A                | Evaluate whether all elements are true    |

## 배열 연산 - 브로드 캐스팅
느린 루프를 제거하기 위해 벡터화하는 Numpy 유니버셜 함수 사용법을 알아 봤다. 벡터화 연산의 또 다른 방법은 Numpy의 브로드캐스팅 기능을 사용하는 것이다. 브로드캐스팅은 단지 다른 크기의 배열에 이항 유니버셜 함수(덧셈, 뺄셈, 곱셈 등)을 적용하기 위한 규칙의 집합일 뿐이다.

### 브로드캐스팅 소개
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/32.png)

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/33.png)

a + 5 에서 값 5를 배열 [5, 5, 5]로 확장하거나 복제하고 그 결과를 더하는 연산이 된다.

마찬가지로 1차원 배열인 a가 2차원 배열로 확장되어 M과 연산이 된다.

마지막으로 3 * 1 행렬과 1 * 3 행렬의 연산이 브로드캐스팅을 통해 3 * 3 결과로 나오는걸 알 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/34.png)

### 브로드캐스팅 규칙
규칙 1 : 두 배열의 차원 수가 다르면 더 작은 수의 차원을 가진 배열 형상의 앞쪽(왼쪽)을 1로 채운다.

규칙 2 : 두 배열의 형상이 어떤 차원에서도 일치하지 않는다면 해당 차원의 형상이 1인 배열이 다른 형상과 일치하도록 늘어난다.

규칙 3 : 임의의 차원에서 크기가 일치하지 않고 1도 아니라면 오류가 발생한다

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/35.png)

```
두 배열 2차원 배열과 1차원 배열이다.

M.shape = (2, 3)
a.shape = (3,)
규칙 1에 따라 배열 a가 더 작은 차원을 가지므로 왼쪽을 1로 채운다.

M.shape -> (2, 3)
a.shape -> (1, 3)
규칙 2에 따라 첫 번째 차원이 일치하지 않으므로 이 차원이 일치하도록 늘린다
M.shape -> (2, 3)
a.shape -> (2, 3)
```
```
a.shape = (3, 1)
b.shape = (3,)
첫번째 룰에 따라 b의 왼쪽에 1을 채운다

a.shape -> (3, 1)
b.shape -> (1, 3)
두번째 룰에 따라 a의 두번째, b의 두번째를 패딩시켜준다.

a.shape -> (3, 3)
b.shape -> (3, 3)
```

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/36.png)

```
M.shape = (3, 2)
a.shape = (3,)
첫번째 규칙 a의 왼쪽에 1을 추가한다.

M.shape -> (3, 2)
a.shape -> (1, 3)
두번째 규칙 a의 첫번째를 패딩시켜준다.

M.shape -> (3, 2)
a.shape -> (3, 3)
세번째 규칙에 따라 최종 형상이 서로 일치하지 않으므로 이 두 배열은 호환되지 않으며 오류를 발생한다.
```

이러한 오류를 해결하기 위해 np.newaxis 키워드로 배열을 재구성하는 방법이 있다.

## 비교, 마스크, 부울 로직
### ufunc으로서의 비교 연산자
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/37.png)

표준 비교 연산자 여섯개 ( <, >, <=. >=, !=, ==) 모두 사용 할 수 있다.


|Operator	|Equivalent ufunc		|Operator	|Equivalent ufunc|
| --------------- | ------------------ | -------------------|---------------------- |
|==	|np.equal		|!=	|np.not_equal|
|<	|np.less		|<=	|np.less_equal|
|>	|np.greater		|>=	|np.greater_equal|

### 부울 배열로 작업하기
* **요소 개수 세기**

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/38.png)

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/39.png)

np.count_nozero(조건) 조건에서 true(1)인 값을 센다.

np.sum(조건) 조건에서 true(1)의 값을 모두 합친다.

np.any(조건) 어떤 원소가 만족하면 참, 아니면 거짓을 반환한다.

np.all(조건) 모든 원소가 조건을 만족하면 참, 아니면 거짓을 반환한다.

* **부울 연산자**
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/40.png)

| Operator | Equivalent ufunc | Operator | Equivalent ufunc |
| -------- | ---------------- | -------- | ---------------- |
| `&`      | np.bitwise_and   | `l`      | np.bitwise_or    |
| `^`      | np.bitwise_xor   | `~`      | np.bitwise_not   |

### 마스크로서의 부울 배열
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/41.png)

배열에서 조건에 맞는 값들을 선택하려면 간단히 부울 인덱스를 사용하면 된다.

x[x < 5] #조건에 맞는 모든 값, 즉 마스크 배열이 True인 위치에 있는 모든 값으로 채워진 1차원 배열을 반환한다.

## 팬시 인덱싱
팬시 인덱싱은 단일 인덱싱과 비슷하지만 단일 스칼라 대신 인덱스 배열을 전달한다. 이로써 복잡한 배열 값의 하위 집합에 매우 빠르게 접근해 그것을 수정할 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/42.png)

배열에 접근 하듯이 각요소에 접근이 가능하다.

index를 리스트나 배열을 전달해 여러 요소에 접근할수도 있다.

인덱싱 배열의 형상을 한다. 말그대로 해당 인덱스 자리에 값을 채워 넣는것

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/43.png)

row, col을 정의해 배열이 n차원 접근하듯이 X[row, col] (like X[row][col]) 한다.

np.newaxis와 브로드캐스팅을 통해 2차원 결과를 얻을수도 있다.

### 결합 인덱싱
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/44.png)

펜시 인덱스와 단순 인덱스는 결합 할 수 있다.

또한, 펜시 인덱싱과 슬라이싱을 결합할 수 있다.

그리고 팬시 인덱싱과 마스킹을 결합할 수 있다.

### 팬시 인덱싱으로 값 변경하기
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/45.png)

팬시 인덱싱이 배열의 일부에 접근하는데 사용되는 것과 마찬가지로 배열의 일부를 수정하는데도 사용 될 수 있다.

x[[0, 0]] = [4, 6] 구문에서 4는 어디로 갔을까? x[0]=4 가 할당되고, x[0]=6이 할당되서 결과적으로 x[0]은 6의 값을 가지게 된것이다.

x[i]+=1 구문에서도 예상과 다른 결과가 나오는데

x[i]+=1은 x[i]=x[i]+1 을 의미하기 때문에 x[i]+1이 평가되고 나면 결과가 x의 인덱스에 할당된다. 따라서 그것은 여러 차례 일어나는 증가가 아니라 할당이므로 보기와는 다른 결과를 가져온다.

이러한 문제를 해결하기 위해 유니버셜 함수의 at() 메서드를 사용 할 수 있다.

at()메서드는 지정한 값을 특정 인덱스에 해당 연산자를 즉시 적용한다.

## 배열 정렬
### Numpy의 빠른 정렬 - np.sort와 np.argsort
np.sort는 기본적으로 퀵 정렬 알고리즘을 사용하지만 병합정렬과 힙 정렬도 사용할 수 있다.

np.argsort는 정렬된 인덱스를 반환한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/46.png)

### 행이나 열 기준으로 정렬하기
다차원 배열에서는 axis를 이요해 특정 행이나 열에 따라 정렬 할 수도 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/47.png)

### 부분 정렬 - 파티션 나누기
np.partition을 통해 K개의 가장 작은 값을 찾을 수 있다. K개의 작은 값이 왼쪽, 나머지가 오른쪽으로 배치되며, 순서는 두 파티션 모두 임의의 순서로 채워진다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/48.png)

## 구조화된 데이터 - Numpy의 구조화된 배열
![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/49.png)

다양한 종류의 데이터를 이름, 나이, 몸무게라고한다. 이 값은 세개의 다른 배열에 저장할 수 있다.

그런데 이렇게 할 경우 세 배열이 서로 연관되어 있음을 알 수가 없다. 모두 단일 구조에 저장하는게 더 좋아 보인다.

Numpy는 복합 데이터 타입을 가지는 배열인 구조화된 배열을 통해 이러한 경우를 처리 할 수 있다.(딕셔너리 자료형을 쓰는것처럼 말이다.)

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/50.png)

### 구조화된 배열 만들기
구조화된 배열 데이터 타입은 여러 가지 방식으로 지정할 수 있다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/51.png)

숫자 타입은 파이썬 타입이나 Numpy dtype으로 지정할 수 있다.

복합 타입은 튜플의 리스트로 지정할 수도 있다.

첫번째 문자 <, > 은 각각 리틀엔디언, 빅엔디언을 의미한다. 그다음 문자는 데이터타입, 그다음 숫자는 객체의 크기를 바이트 단위로 나타낸다.

| Character    | Description            | Example                            |
| ------------ | ---------------------- | ---------------------------------- |
| `'b'`        | Byte                   | `np.dtype('b')`                    |
| `'i'`        | Signed integer         | `np.dtype('i4') == np.int32`       |
| `'u'`        | Unsigned integer       | `np.dtype('u1') == np.uint8`       |
| `'f'`        | Floating point         | `np.dtype('f8') == np.int64`       |
| `'c'`        | Complex floating point | `np.dtype('c16') == np.complex128` |
| `'S'`, `'a'` | String                 | `np.dtype('S5')`                   |
| `'U'`        | Unicode string         | `np.dtype('U') == np.str_`         |
| `'V'`        | Raw data (void)        | `np.dtype('V') == np.void`         |

### 고급 복합 타입
배열이나 행렬을 담고 있는 타입을 만들 수 있다. 3 * 3 부동 소수점 행렬로 구성된 mat 컴포넌트를 가지는 데이터 타입을 만들어 본다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/52.png)

왜 굳이 파이썬에 있는 딕셔너리 자료구조형을 놔두고 이걸 쓰느냐 생각이 들 수 있다. 이는 Numpy dtype이 C구조체 정의에 직접 매핑도이ㅓ 적절하게 작성된 C프로그램에서 배열 내용을 포함하는 버퍼에 직접 접근할 수 있기 때문이다. 구조화된 데이터를 조작하는 C나 포트란 라이브러리에 파이썬 인터페이스를 작성한다면 아마 구조화된 배열이 상당히 유용할 것이다.

### 레코드 배열 - 트위스트를 가진 구조화된 배열
Numpy는 딕셔너리 키 대신 속성으로 필드에 접근할 수 있는 np.recarray 클래스도 제공한다.

![1.png](https://github.com/ghdic/IT-Study/blob/master/Image/Python/Numpy/53.png)

데이터를 레코드 배열로 보면 약간 더 적은 키 입력으로 나이 데이터에 접근할 수 있다.

하지만 레코드 배열의 단점은 필드에 접근 할 때 동일한 구문을 사용해도 부가적인 오버헤드가 발생한다.
