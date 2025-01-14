# 추상자료형
[파이썬으로 쉽게 배우는 자료구조](https://www.booksr.co.kr/product/%ED%8C%8C%EC%9D%B4%EC%8D%AC%EC%9C%BC%EB%A1%9C-%EC%89%BD%EA%B2%8C-%EB%B0%B0%EC%9A%B0%EB%8A%94-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/)를 보고 정리한 내용입니다.

## 추상 자료형(ADT)이란
프로그래머가 추상적으로 정의한 자료형이다.
* 어떤 자료를 다루고 이들에 대해 어떤 연산이 제공되는지를 기술해 주어 사용자가 필요한 기능을 선택하기만 하면 자동으로 그 기능이 실행이 되게 해주는 기능이다.
  * 데이터나 연산이 무엇인가를 정의 해야한다.
  * 데이터나 연산을 어떻게 구연할 것인지는 정의하지 않는다.
## 예) 가방(Bag)의 추상 자료형
추상자료에 대해 쉽게 이해하기 위해 가방의 예시로 파이썬의 함수를 이용하여 추상자료형을 만들었다. 가방에 물건을 넣거나 빼거나 수를 세는 기능을 실행 할 수 있다.

### 데이터
* 중복된 항목들을 허용하는 자료의 모임이다.
* 항목들 사이에 순서는 없지만 서로 비교할 수는 있어야한다.

### 연산
가방의 기능을 실행하기 위해 코드에 사용될 연산들이다.

* insert(e) : 가방에 항목 e를 넣는다.
* remove(e) : 가방에 e가 있는지 검사하여 있으면 이 항목을 꺼낸다.
* contains(e) : e가 들어있으면 True 없으면 False를 반환한다.
* count() : 가방에 들어있는 항목의 수를 반환한다.

# Sample Code
[파이썬으로 쉽게 배우는 자료구조](https://www.booksr.co.kr/product/%ED%8C%8C%EC%9D%B4%EC%8D%AC%EC%9C%BC%EB%A1%9C-%EC%89%BD%EA%B2%8C-%EB%B0%B0%EC%9A%B0%EB%8A%94-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/)서적을 참고하여 구현하였다.

## Bag의 추상 자료형 구현
파이썬 함수를 이용하여 Bag의 추상자료를 구현할 수 있다.
```python
def contains(bag, e) :
    return e in bag

def insert(bag, e) :
    bag.append(e)

def remove(bag, e) :
    bag.remove(e)

def count(bag):
    return len(bag)
```
## Bag의 활용
위의 함수의 코드를 구현해 놓고 구현한 함수를 불러오기만을 통해 Bag의 기능을 이용할 수 있다.
```python
myBag = [ ]
insert(myBag, '휴대폰')
insert(myBag, '지갑')
insert(myBag, '손수건')
insert(myBag, '빗')
print("내 가방속의 물건: ", myBag)

print("가방속의 물건 수: ",count(myBag))

insert(myBag, '빗')
remove(myBag, '손수건')
print("내 가방속의 물건: ", myBag)

print(contains(myBag, '손수건'))
```
* 이 코드에서의 함수들은 위에 구현코드에서 지정해 놓은 방식으로 작동을 한다.
* `insert(myBag,'e')`를 통해 myBag에 e를 삽입을 한다.
* 위에서 구현한 `count(myBag)` 함수를 통해 bag 리스트의 길이를 계산한다.
* `remove(myBag, '손수건')`을 통해 손수건이 있는지 찾은 후에 손수건을 꺼낸다.
* `contains(myBag, '손수건')`은 손수건이 있는지 확인한다.
## 출력 결과
![20250114_174323](https://github.com/user-attachments/assets/8cd6fc26-cb34-4937-a66a-96a910fc9332)
* 입력한 코드의 순서대로 물건이 들어간 것을 확일할 수 있다.
* 가방의 물건의 수를 계산하여 출력
* 손수건을 찾아 제거를 하고 손수건이 있는지 탐색을 하여 False가 출력되었다.

## 결론
추상자료(ADT)는 위와 같이 함수들이 어떤 연산이 제공되는지 기술을 해놓고 어떻게 구현되어있는지는 정의 해놓지 않는 것이다. 이를 통해 프로그램이 출시 되었을때 사용자들이 어떠한 기능들이 제공되는지를 확인하고 복잡한 내용을 알지 못해도 제공되는 기능을 가져와서 간단히 프로그램을 작동시킬 수 있게 해준다.  
   
예를 들어, 전자레인지가 따뜻해지는 방식과 돌아가게 하기 위해 모터를 사용하는 것, 전선이 어떻게 구성되어야 하는지에 관한 것을 몰라도 오로지 시작 버튼과 타이머 버튼만 눌러도 전자레인지를 사용할 수 있는 것과 같다.
