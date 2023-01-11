### while 문

while 문 같은 경우 C언어와 다르지 않게 조건이 주어지고 조건이 만족하는 동안
while 문 내부의 코드를 계속해서 진행합니다! 
하지만, 다른 점이라면 ```"괄호를 적어주지 않아도 된다"```는 건데요, 한번 알아보자고요! 

```swift
var i: Int = 1
var sum: Int = 0

while i < 10{
sum += i
i += 1
}
print(sum) // 45
```
이런 식으로 i에 대한 조건을 적어주고, sum에 i의 값을 하나하나씩 더해 만들어 줄 수 있습니다.

### repeat - while

C언어에서의 do - while 이라고 생각을 하면 이해하기 쉬울거에요! 

```swift
var i: Int = 1
var sum: Int = 0

repeat {
    sum += i
    i += 1
}while i < 10
        
print(sum) // 45
```
위와 같이 만들어주면 같은 결과값을 볼 수 있습니다!