# 입력(input)과 출력(print)

## [1] 입력(input)

### (1) 내장함수 input()

- 파이썬의 내장함수 `input()`을 사용하면 터미널에서 사용자 입력을 받을 수 있다.
- `input()` 함수에 문자열을 작성하면 프롬프트(prompt)가 된다.
- 프롬프트 없이 `input()` 을 사용할 수 있다.
    
    ```python
    name = input("")
    
    print(name)
    ```
    
    ```bash
    # 터미널 화면
    # 메세지없이 입력을 받기 위해 대기합니다.
    ```
    

### (2) 사용자 입력 시 주의사항

1. **입력값의 자료형 문제**
- 사용자 입력에 대한 모든 값의 자료형은 `문자열(str)`이다.
- 숫자 형태의 값을 숫자형으로 사용하기 위해서는 `형 변환` 을 해야한다.

2. **입력 대기(Blocking)로 인한 흐름 정체**
- 파이썬 인터프리터(즉, 코드가 위에서 아래로 한 줄씩 실행되는 환경)에서 `input()` 함수가 실행되면, 코드 실행 흐름이 잠시 멈추고(Blocking) 사용자 입력을 기다린다.
- 사용자가 엔터(Enter)를 칠 때까지 코드의 다음 줄로 넘어가지 않는다.
- 사용자 입력이 없으면 코드가 영원히 멈춰 있을 수 있다는 점에 주의하자.

## [2] 출력(print)

### (1) 내장함수 print()

- 값을 화면(터미널)에 출력하기 위해 사용하는 함수이다.
- 파이썬의 내장함수 `print()`를 사용하면 터미널에 값을 출력할 수 있다.
- 아무 것도 출력하지 않고 한 줄만 띄우고 싶다면 `print()`만 작성한다.
    
    ```python
    word1 = "hello"
    word2 = "python"
    
    print(word1)
    print()  # 한 줄 띄우기
    print(word2)
    ```
    
    ```
    hello
    
    python
    ```
    

- `콤마(,)`를 사용해서 여러 데이터를 넣으면, `공백을 기준으로 출력`된다.
    
    ```python
    word1 = "hello"
    word2 = "python"
    word3 = "yeah!"
    
    print(word1, word2, word3)  # 세 개의 문자열이 공백을 기준으로 출력
    ```
    
    ```
    hello python yeah!
    ```
    

### (2) end 옵션

- print()는 기본적으로 끝에 한 줄을 띄운다고 하였다.
- end 옵션을 사용하면 출력 이후 한 줄을 띄우지 않고, 끝부분에 다른 문자를 출력할 수 있다.
  
```python
print("Hello World", end="!")  # "Hello World"를 출력하고 한 줄을 띄우지 않고 끝에 느낌표(!)를 추가
```

```
Hello World!
```

- end 옵션에 `공백`을 넣어서 띄어쓰기를 할 수도 있다.

```python
word1 = "hello"
word2 = "python"

print(word1, end=" ")  # "hello"를 출력하고 한 줄 띄우지 않고 끝에 공백을 출력
print(word2)
```

```
hello python
```

- end 옵션에 `빈 문자열`을 넣어서 문자열을 붙일 수도 있다.

```python
word1 = "hello"
word2 = "python"

print(word1, end="")  # "hello"를 출력하고 한 줄 띄우지 않고 끝에 빈 문자열을 출력
print(word2)
```

```
hellopython
```