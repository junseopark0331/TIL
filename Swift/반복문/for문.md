### for문

``` for "변수" in "반복횟수" ```와 같이 표현할 수 있습니다.


``` swift
var sum: Int = 0

for a in 0...10{
    sum += a
}
print(sum) // 55
```
와 같이 만들어줄 수 있습니다. 

반복대상의 값을 사용하지 않는 경우 in 앞에 ```_``` 를 붙여 쓸 수 있습니다.

```swift
var sum: Int = 0

for _ in 0...10{
    sum += a
}
print(sum) // 출력값 : 55
```
