# 변수(Variables)

## [1] 변수란?

### (1) 변수는 상자이다.

- 변수란 데이터의 값을 저장하는 `상자`와 같다.
- 사실 변수는 상자가 아니다. 변수는 객체의 참조(reference)를 저장할 뿐이다.
```python
number = 100
```

</aside>

### (2) 할당(assignment)

- 할당이란 변수에 값을 담는 것을 말한다.
- 변수를 생성할 때는 `할당 연산자(=)`를 사용한다.
- `변수 이름 = 변수에 저장되는 값`의 형식으로 작성한다.
- 수학의 등호(=)처럼 왼쪽과 오른쪽이 같다는 의미가 아니다. **오른쪽 값이 왼쪽 변수에 할당된다**라고 생각해야 한다.
- 변수를 출력하면, 해당 변수에 담긴 데이터의 값이 출력된다.
    
    ```python
    name = "kyle"  # name 변수에 문자열 "kyle"을 할당
    age = 20  # age 변수에 정수 20을 할당
    is_male = True  # is_male 변수에 불린형 True를 할당
    
    print(name)
    print(age)
    print(is_male)
    ```
    
    ```
    kyle
    20
    True
    ```
    
- 이제 `type()` 내장함수에 값 대신 변수를 넣어서, 해당 데이터의 타입을 알 수 있다.
    
    ```python
    name = "kyle"
    age = 20
    is_male = True
    
    print(type(name))
    print(type(age))
    print(type(is_male))
    ```
    
    ```
    <class 'str'>
    <class 'int'>
    <class 'bool'>
    ```
    

### (3) 변수의 필요성

1. **변수는 데이터에 의미를 부여한다.**
    - 숫자 값 `20` 의 의미를 알 수 있는 코드
        
        ```python
        age = 20  # 정수 20이 나이를 의미
        
        print(age)
        ```
        
        ```
        20
        ```
        

2. **변수는 코드의 재사용성과 가독성을 높여준다.**
    - 변수만 5번 반복해서 작성한 코드
        
        ```python
        sentence = "Life is too short, You need Python."
        
        print(sentence)
        print(sentence)
        print(sentence)
        print(sentence)
        print(sentence)
        ```
        
        ```
        Life is too short, You need Python.
        Life is too short, You need Python.
        Life is too short, You need Python.
        Life is too short, You need Python.
        Life is too short, You need Python.
        ```
        

3. **변수는 유지보수를 쉽게 해준다.**
    - 변수로 만들어서 사용하면, 1번만 수정하면 되므로 유지 보수가 쉬워진다.
        
        ```python
        sentence = "Life is too short, We need Python."
        
        print(sentence)
        print(sentence)
        print(sentence)
        print(sentence)
        print(sentence)
        ```
        
        ```
        Life is too short, We need Python.
        Life is too short, We need Python.
        Life is too short, We need Python.
        Life is too short, We need Python.
        Life is too short, We need Python.
        ```
        

## [2] 식별자와 리터럴

### (1) 식별자(Identifiers)

- 식별자는 `변수의 이름`을 뜻한다.
- 할당 연산자(=)에서 왼쪽에 해당하는 부분이다.
    
    ```
    변수명(식별자) 작성 규칙
    
    1) 알파벳, 언더바(_), 숫자로 구성되어야 한다.    # number, my_note, car1
    2) 첫 글자에는 숫자가 올 수 없다.              # 1car는 불가능
    3) 대소문자를 구별한다.                      # 변수 a와 변수 A는 서로 다른 변수
    4) 띄어쓰기가 필요한 경우 언더바(_)로 구분한다.   # 식별자에는 공백이 있으면 안되므로 my_list 와 같은 식으로 공백을 표현
    5) 예약어로 지을 수 없다.


### (2) 리터럴(Literal)

- 리터럴은 `데이터의 값`을 뜻한다.
- 할당 연산자(=)에서 오른쪽에 해당하는 부분이다.
- 예를 들어, 100은 정수 리터럴이다. “Python”은 문자열 리터럴이다.

**정리하자면 `변수는 박스`이고 `식별자는 박스에 붙은 이름`이며 `리터럴은 박스에 담긴 값`이라고 할 수 있다.**

```python
number = 100  # 식별자가 number인 변수에 정수 리터럴 100을 할당
```

## [3] 재할당

재할당이란 기존 존재하던 변수에 새로운 값을 할당(저장)하는 행위이다.

```python
number = 100  # 할당
print(number)

number = 200  # 재 할당
print(number)
```

```
100
200
```

재할당 시 `변수는 가장 마지막으로 할당한 값을 가지고 있음`에 주의한다.

```python
number = 100
number = 200
number = 300

print(number)
```

```
300
```

## **[4] 변수와 메모리 주소, 참조**

파이썬의 변수는 C/Java와 달리, ‘상자 안에 값이 담기는 것’이 아니라, ‘이름(변수)이 어떤 객체를 가리키는 꼬리표(tag, reference)’에 가깝다.

> **예시**
> 

```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)  # [1, 2, 3, 4]
```

- `a`와 `b`는 같은 리스트 객체를 ‘가리키는’ 상태이고,
- `b`는 `a`의 복사본이 아니라, 같은 곳을 참조하고 있다.
- 또한 파이썬에서 각 객체는 고유의 id(메모리 주소)가 있다.

> **예시**
> 

```python
x = [10, 20]
print(id(x)) # 메모리 주소(객체 id) 확인

y = x
print(id(y))  # x와 y의 id는 동일
```

- 이처럼 변수는 실제 데이터를 담는 것이 아니라, 객체의 메모리 위치(주소, id)를 참조한다.