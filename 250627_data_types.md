# 자료형(Data types)

## [1] 자료형이란?

- 프로그래밍에서 `데이터의 특성`을 의미한다.

    

## [2] 숫자형

### (1) 정수형(int)

- 양의 정수, 음의 정수, 0
- 정수형 혹은 int 타입이라고 한다.

```python
print(100)
print(0)
print(-25)
```

```python
100
0
-25
```

### (2) 실수형(float)

- 소수점이 포함된 숫자를 뜻한다.
- 실수형 혹은 float 타입이라고 한다.

```python
print(1.2)
print(-3.56)
```

```
1.2
-3.56
```

## [3] 문자열

### (1) 문자열(str)

- 한글, 알파벳, 특수 문자 같은 문자들의 나열(Sequence)을 의미한다.
- 문자열 혹은 string (str) 타입이라고 말한다.

### (2) 문자열 생성

- 0개 이상의 문자를 작은따옴표(’) 혹은 큰따옴표(”)로 감싸서 표기한다.

```python
print('Hello Python')
print('파이썬')
print('123')    
print('#$%^&*')
```

```python
print("Hello Python")
print("파이썬")
print("123")
print("#$%^&*")
```

```
Hello Python
파이썬
123
#$%^&*
```

### (3) 문자열 사용 시 주의사항

1. **공백(’ ‘)과 빈 문자열(’’)도 눈에 보이지 않을 뿐이지 하나의 문자열로 취급된다.**
    
    ```python
    print(' ')  # 공백
    print('')  # 빈 문자열
    ```
    
    ```python
      <= 보이지 않지만 공백이 존재
      <= 보이지 않지만 빈 문자열이 존재
    ```
    
2. **작은따옴표와 큰따옴표는 반드시 짝을 맞춰주어야 한다. 섞어서 쓰면 에러가 발생한다.**
    
    ```python
    print('Hello Python")
    ```
    
    ```
    File "/Users/edu/test.py", line 1
        print('Hello Python")
                             ^
    SyntaxError: EOL while scanning string literal
    ```
    
3. **따옴표 안에 따옴표를 표현할 경우에는 서로 다르게 작성해야 한다.**
    
    ```python
    print("큰따옴표 안에 '작은따옴표' 사용하기")
    print('작은따옴표 안에 "큰따옴표" 사용하기')
    ```
    
    ```
    큰따옴표 안에 '작은따옴표' 사용하기
    작은따옴표 안에 "큰따옴표" 사용하기
    ```
    
    만약 같은 따옴표 종류를 중첩으로 사용할 경우 에러가 발생한다.
    
    ```python
    print("큰따옴표 안에 "큰따옴표" 사용하기")
    ```
    
    ```
    File "/Users/edu/test.py", line 1
        print("큰따옴표 안에 "큰따옴표" 사용하기")
                                     ^
    SyntaxError: invalid syntax
    ```
    
4. **숫자 123과 문자열 ‘123’은 엄연히 다르다. (똑같이 123으로 출력된다고 해서 같은 자료라고 생각하면 안 된다.)**
    
    ```python
    print(123)
    print('123')
    
    print(type(123))
    print(type('123'))
    ```
    
    ```
    123
    123
    <class 'int'>
    <class 'str'>
    ```
    

### (4) 문자열 포맷팅 f-string

- 문자열 내부 특정 위치에 변수 또는 표현식을 넣을 수 있다.
- `f"{변수}"`
    
    ```python
    name = "배지원"
    age = 20
    sentence = f"{name}은 {age}살 입니다."
    
    print(sentence)
    ```
    
    ```
    배지원은 20살 입니다.
    ```
    

- **`f"{표현식}"`**
    
    ```python
    age = 20
    
    sentence = f"내년이 되면 {age + 1}살입니다."
    
    print(sentence)
    ```
    
    ```
    내년이 되면 21살입니다.
    ```
    

## [4] 불린형

- 참(True)과 거짓(False)을 뜻한다.
- 불린형 / boolean 타입 / 논리형이라 한다.

```python
print(True)
print(False)
```

```
True
False
```

<aside>
📌

자료형을 확인하기 위해서 내장함수 `type()`을 사용한다.

</aside>

## [5] 명시적 형 변환

> `형 변환(typecasting)`이란 특정 타입의 자료를 다른 타입의 자료로 변환하는 것을 말한다.
사용자는 **파이썬의 내장 함수를 사용하여 의도적으로 타입을 변환**할 수 있는데, 이를 `명시적 형 변환`이라고 한다.
> 

### (1) 정수형으로 변환

> 실수형 또는 문자열을 `정수형 int`으로 변환한다.
> 
1. **실수형(float) ⇒ 정수형(int)**
    
    실수에서 소수점을 제외하여 정수로 변환한다.
    
    ```python
    print(int(1.5))
    print(int(-1.5))
    print(type(int(1.5)))
    print(type(int(-1.5)))
    ```
    
    ```
    1
    -1
    <class 'int'>
    <class 'int'>
    ```
    
2. **문자열(str) ⇒ 정수형(int)**
    
    정수 형태의 문자열을 정수로 변환한다.
    
    ```python
    print(int('123'))
    print(type(int('123')))
    ```
    
    ```
    123
    <class 'int'>
    ```
    
    단, 정수로 변환될 수 있는 형식일 때만 가능하다.
    
    ```python
    print(int('1.5'))
    ```
    
    ```
    File "/Users/edu/test.py", line 1, in <module>
        print(int('1.5'))
    ValueError: invalid literal for int() with base 10: '1.5'
    ```
    

### (2) 실수형으로 변환

> 문자열 혹은 정수형을 `실수형 float`으로 변환한다.
> 
1. **정수형(int) ⇒ 실수형(float)**
    
    정수에서 소수점을 추가하여 실수로 변환한다.
    
    ```python
    print(float(10))
    print(float(-10))
    print(type(float(10)))
    print(type(float(-10)))
    ```
    
    ```
    10.0
    -10.0
    <class 'float'>
    <class 'float'>
    ```
    
2. **문자열(str) ⇒ 실수형(float)**
    
    실수 형태의 문자열을 실수로 변환한다.
    
    ```python
    print(float('3.5'))
    print(type(float('3.5')))
    ```
    
    ```
    3.5
    <class 'float'>
    ```
    
    단, 실수로 변환될 수 있는 형식일 때만 가능하다.
    
    ```python
    print(float('3/5'))
    ```
    
    ```
    File "/Users/edu/test.py", line 1, in <module>
        print(float('3/5'))
    ValueError: could not convert string to float: '3/5'
    ```
    

### (3) 문자열로 변환

> 문자열이 아닌 자료형을 `문자열 str`로 변환한다.
> 

```python
# int => str
print(str(123))
print(type(str(123)))

# float => str
print(str(10.5))
print(type(str(10.5)))

# bool => str
print(str(True))
print(type(str(True)))
```

```
123
<class 'str'>
10.5
<class 'str'>
True
<class 'str'>
```

출력은 기존 자료형 때와 동일하게 나오지만, 엄연히 문자열로 변경된 것임을 주의한다.

### (4) 불린형으로 변환

> 불린형이 아닌 자료형을 불린형으로 변환할 때 사용하는 함수
> 
- 불린형이 아닌 자료형을 `불린형 bool`으로 변환한다.
- 각 자료형의 값에 따른 불린형 변환표
    - `0, 0.0, ''` 과 같은 비어있음을 뜻하는 값은 모두 `False(거짓)` 으로 변환한다.

| 데이터의 값 | Boolean |
| --- | --- |
| 0 | False |
| 1 | True |
| -1 | True |
| 0.0 | False |
| 1.5 | True |
| ‘’ | False |
| ‘Hello’ | True |
| [] | False |
| [1, 2, 3] | True |

```python
print(bool(1))
print(bool(1.5))
print(bool('hello'))
print(bool([1, 2, 3]))

print(bool(0))
print(bool(0.0))
print(bool(''))
print(bool([]))
```

```
True
True
True
True
False
False
False
False
```