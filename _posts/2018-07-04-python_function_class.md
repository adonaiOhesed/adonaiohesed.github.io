---
title: 파이썬 함수와 클래스
tags: python
key: page-python_function_class
cover: /assets/cover/python.png
---

## 함수

```python
def function_name(parameter):
    return something
```
* return값이 void면 indentation으로 다른 실행문을 계속 쓰면 된다.
함수를 탈출하고 싶으면 return 만 써도 된다.(break같은 느낌으로)

<br>
```python
def name(choice, *args)
```
* choice변수 하나와 multiple 인자를 받을 수 있다는 뜻이다.
* name('mul', 1,2,3,4)로 받을 수 있다.
* args는 전체가 튜플() 로 변환되어 함수 내에서 사용가능하게 된다.
* return값이 ```return sum, mul``` 로 했을 경우 (sum, mul)의 튜플이 return된다.
  * 하지만 원칙상으로 항상 1개의 값만 return 되는 것이다.

<br> 
```python
def self(name, old, gender=True):
```
* parameter에 default값을 설정 할 수 있다.
  * gender를 parameter로 받지 않아도 기본적으로 True로 작동하게 할 수 있다.
* 따라서 default를 컴파일러가 파악하기 위해서는 가장 오른쪽에서부터 배치해야지 오류가 일어나지 않는다.(가운데나 처음에 오면 안됨)
* 함수 내에서 global 선언으로 외부 변수를 사용할 수 있는데 가급적 이건 사용하지 말자.

<br>

## 입출력

```python
a = input()
a = input("prompt")
print("a" "b" "c") # abc
print("a" + "b" + "c") # abc
print("a","b","c") # ('a', 'b', 'c')
```
* input으로 받은 것은 모두 문자열로 처리한다.
* print 안에 " " " " 로 이뤄지면 " " + " " 와 같은 결과이다.
* print 안에 ,가 들어가면 튜플로 보여진다.

<br>

## 파일 입출력

```python
f = open("file.txt",'w') # w : 쓰기 r : 읽기 a : 이어쓰기
f.close() # 이거를 명시하지 않아도 자동으로 처리되기는 한다.
f.write('something') # 파일에 'something'을 쓰기.
line = f.readline() # 파일에서 한 줄씩 읽어오기.
if not line: break # 이 형태로 EOF을 감지할 수 있다.
lines = f.readlines() # 모든 line들을 가져와서 리스트 형태로 반환한다.
data = f.read() # 모든 내용을 하나의 문자열로 return
```
```python
with open("file.txt", "w") as f:
    f.write('something')
```
* open block 안에서 나가는 즉시 자동으로 file close를 시켜준다.

```python
args = sys.argv[1:]
for i in args:
   print(i)
```
* argument로 들어오는 값들을 처리할 수 있다. int main(args[])와 같은 이치.

<br>

## 클래스

* class 내부에서 함수를 정의할 때 항상 맨 앞의 parameter로 self를 넣어줘야 한다.<br>이건 개발 원리와 관계가 있다.
```python
class 이름(<super class name>):
    foo = 0
    def __init__(self, name):
        self.name = name
        self.result = 0
    def skip(self, a,b):
        pass
    def add(self, num):
        self.result += num
        return self.result
```
* init는 constructor이다. self는 계속 붙이는거라 생각하면 된다.
* class이름으로 상속을 받는다.
* 이름.skip(instance_name,a,b)와 같이 className을 이용해서도 쓸 수 있다.
* method overriding도 가능하다.
* 연산자 overloading
```python
def __add__(self, other):
   pass
def __sub__(self, other):
    pass
def __mul__(self, other):
    pass
def __truediv__(self, other):
    pass
```
* 위의 경우 각 연산자(+,-,*,/) 쓸 때마다 위에서 정의한 그대로 작동된다.