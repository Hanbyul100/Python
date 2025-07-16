# 순서가 없는 컨테이너(Non-Sequence)

## [1] 딕셔너리(Dictionary)

### (1) 딕셔너리란?

- 0개 이상의 항목(Item)을 저장하는 비시퀀스 자료형으로 하나의 속성은 **key: value** 쌍으로 이루어져있다.
- key는 딕셔너리 내부에서 **유일하며** 매핑된 값을 통해 데이터를 효율적으로 관리한다.

### (2) 딕셔너리 생성

- **중괄호 `{}`** 를 사용해서 생성한다.
- **중괄호 `{}`** 내부에서 항목(Item)을 쉼표 `,` 로 구분해서 작성한다.
    - key, value는 콜론 `:` 으로 구분한다.
    - key는 숫자형, 불리언형, 문자열, 튜플을 사용할 수 있다.
    - value는 자료형을 구분하지 않고, 사용할 수 있다.

### (3) 딕셔너리 value 접근

- 딕셔너리에 저장된 key를 통해 연결된 value에 접근해서 사용하거나 재할당 할 수 있다.
- 이때, 저장되지 않은 key에 접근하면 새로운 **key: value** 쌍을 생성한다.
- **`dict[key]`**
    - key에 연결된 value에 접근한다.
    - key에 연결된 value를 재할당할 수 있다.
    
    ```python
    my_dict = {"name": "Alice", "age": 25, "city": "Seoul"}
    
    my_dict["name"] = "Beemo"
    print(my_dict["name"])
    
    print(my_dict["age"])
    ```
    
    ```bash
    Beemo
    25
    ```
    

- **`dict[새로운 key] = value`**
    - 새로운 key: value 쌍을 생성한다.
    
    ```python
    my_dict['email'] = 'alice@example.com'
    my_dict['age'] = 26
    print(my_dict)
    ```
    
    ```bash
    {'name': 'Beemo', 'age': 26, 'city': 'Seoul', 'email': 'alice@example.com'}
    ```
    

### (4) 딕셔너리 메서드

- **`dict.keys()`**
    - 모든 key 모음을 반환한다.

- **`dict.values()`**
    - 모든 value 모음을 반환한다.

- **`dict.items()`**
    - 모든 **항목(Item)**을 반환한다.

- **`dict.pop(key)`**
    - key와 연결된 value를 삭제하고, value는 반환한다.

- **`dict.popitme()`**
    - 마지막 key: value 쌍을 제거하고, 튜플로 반환한다.


## [2] 집합(Set)

### (1) 집합이란?

- 집합은 **0개 이상의** **원소들을 중복없이 저장하는** 비시퀀스 자료형

### (2) 집합 생성

- **중괄호 `{}`** 를 사용해서 생성한다.
- **중괄호 `{}`** 내부에서 원소를 쉼표 `,` 로 구분해서 작성한다.
    
    ```python
    my_set = {1, 2, 3, 4, 5}
    print(my_set) 
    ```
    
    ```
    {1, 2, 3, 4, 5} 
    ```
    
- 비어있는 집합을 생성할 때는 **`set()`** 함수를 사용한다.
    
    ```bash
    void_set = set()
    
    # 비어있는 중괄호는 딕셔너리를 의미한다.
    # void_dict = {}
    ```
    

### (3) 집합 메서드

- **`set.add(값)`**
    - 새로운 원소를 추가한다.
    
    ```python
    my_set.add(6)
    print(my_set) 
    ```
    
    ```bash
    {1, 2, 3, 4, 5, 6}
    ```
    
- **`set.remove(원소)`**
    - 원소를 삭제한다. 이때, 존재하지 않는 원소를 삭제하면 오류가 발생한다.

- **`set.discard(원소)`**
    - 원소를 삭제한다. 이때, 존재하지 않는 원소를 삭제해도 오류가 발생하지 않는다.
    
    ```python
    my_set.remove(2)
    print(my_set)
    ```
    
    ```bash
    {1, 3, 4, 5, 6}
    ```
    

### (4) 수학 집합 연산

- 집합 자료형은 수학의 집합을 기반으로 만들어진 자료형이기 때문에 수학 집합 연산자가 있다.
- 합집합: `set1.union(set2)` 또는 `set1 | set2`
- 교집합: `set1.intersection(set2)` 또는 `set1 & set2`
- 차집합: `set1.difference(set2)` 또는 `set1 - set2`

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}

print(set1 | set2)
print(set1 & set2)
print(set1 - set2)
```

```bash
{1, 2, 3, 4, 5}  # 합집합
{3}  # 교집합
{1, 2}  # 차집합
```

## [3] 멤버십 연산자(in, not in)

### (1) 멤버십 연산자란?

- 특정 값이 컨테이너 자료형 원소에 포함되어 있는지 검사하는 연산자이다.

### (2) in

- `값 **in** 컨테이너 자료형`
    - 값이 컨테이너 자료형 **원소에 포함되어 있으면** 참**`True`** 으로 평가한다.
    
    ```python
    numbers = [1, 2, 3, 4, 5]
    
    print(1 in numbers)  # numbers 리스트에 원소 1이 있으므로 True
    print(6 in numbers)  # numbers 리스트에 원소 6이 없으므로 False
    ```
    
    ```
    True
    False
    ```
    

### (3) not in

- **`값 not in** 컨테이너 **자료형**`
    - 값이 컨테이너 자료형 **원소에 포함되어 있지 않으면** 참 **`True`** 으로 평가한다.
    
    ```python
    word = "python"
    
    print("p" not in word)  # word 문자열에 원소 "p"가 있으므로 False
    print("j" not in word)  # word 문자열에 원소 "j"가 없으므로 True
    ```
    
    ```
    False
    True
    ```
    

### (4) 딕셔너리와 멤버십 연산자

- **`값 in 딕셔너리`**
    - 값이 딕셔너리 key 모음에 포함되어 있으면 참 **`True`** 으로 평가한다.
    
    ```python
    colors = {
        "Red": "빨강",
        "Blue": "파랑",
    }
    
    print("Red" in colors)
    print("Blue" not in colors)
    ```
    
    ```python
    True
    False
    ```
    

### (5) 딕셔너리.values()와 멤버십 연산자

- **`값 in 딕셔너리.values()`**
    - 값이 딕셔너리 value 모음에 포함되어 있으면 참 **`True`** 으로 평가한다.
    
    ```python
    colors = {
        "Red": "빨강",
        "Blue": "파랑",
    }
    
    print("파랑" in colors.values())
    print("빨강" not in colors.values())
    ```
    
    ```python
    True
    False
    ```