# 컨테이너(Container) 자료형

## [1] 컨테이너란?

### 컨테이너 자료형

> `컨테이너(Container)`란, **여러 데이터를 한 곳에 저장할 수 있는 자료형**을 의미한다.
> 

## [2] 컨테이너의 분류

- 컨테이너는 각각 `순서`와 `변경 가능성`에 따라 다르게 분류될 수 있다.

<aside>
💡

변수에 저장된 객체가 변경될 수 있는지 여부에 따라 **가변(Mutable) 자료형**과 **불변(Immutable) 자료형**으로 구분되기도 한다.

</aside>

### **(1) 순서에 따른 분류**

- `순서가 있는 컨테이너 (Sequence)` : 데이터를 연속된 공간에 순서대로 저장하는 컨테이너
    - ex) 리스트, 문자열, 레인지, 튜플
- `순서가 없는 컨테이너 (Non-sequence)` : 데이터를 무작위의 순서로 저장하는 컨테이너
    - ex) 집합, 딕셔너리
    
### **(2) 변경 가능성에 따른 분류**

- `변경 가능한 컨테이너 (Mutable)` : 생성된 이후, 값을 삽입/수정/삭제 할 수 있는 컨테이너
    - ex) 리스트, 집합, 딕셔너리
- `변경 불가능한 컨테이너 (Immutable)` : 생성된 이후, 값을 삽입/수정/삭제 할 수 없는 컨테이너
    - ex) 문자열, 레인지, 튜플
- **내장함수 id로 알아보는 변경 가능성**
    - `내장함수 id`는 파이썬 객체의 고유값(주소값)을 반환한다.
    - `변경 가능한 컨테이너`는 값을 삽입/수정/삭제해도 고유값이 유지된다. 즉, 컨테이너 객체는 그대로 유지되고 내부만 변경된다.
        
        ```python
        number_list = [1, 2, 3, 4]  # 리스트
        print(number_list)
        print(id(number_list))
        
        number_list.append(5)  # number_list의 맨 끝에 5를 삽입
        print(number_list)
        print(id(number_list))
        ```
        
        ```
        [1, 2, 3, 4]
        4381713472
        [1, 2, 3, 4, 5]
        4381713472
        ```
        
    - `변경 불가능한 컨테이너`는 값을 삽입/수정/삭제할 수 없다.
        
        ```python
        number_tuple = (1, 2, 3, 4)  # 튜플
        number_tuple[0] = 9  # number_tuple의 맨 앞 값을 1에서 9로 수정 시도
        ```
        
        ```
        Traceback (most recent call last):
          File "/test.py", line 2, in <module>
            number_tuple[0] = 9
        TypeError: 'tuple' object does not support item assignment
        ```
        
    - `변경 불가능한 컨테이너`는 연산자를 이용해 마치 변경된 것처럼 보이도록 할 수 있으나, 이는 내부가 변경된 것이 아니라 변경된 모습의 새로운 컨테이너가 `재할당`된 것이다.
    - 따라서, 고유값이 달라진다.
        
        ```python
        number_tuple = (1, 2, 3, 4)  # 튜플
        print(number_tuple)
        print(id(number_tuple))
        
        number_tuple += (5,)  # number_tuple의 맨 끝에 5를 삽입
        print(number_tuple)
        print(id(number_tuple))
        ```
        
        ```
        (1, 2, 3, 4)
        4311686416
        (1, 2, 3, 4, 5)
        4310304784
        ```