# guard와 if의 차이

### guard
guard구문은 함수나 메서드 혹은 반복문 안에서만 사용할 수 있다는 한계점이 있다. 

또한 
```swift
func solution() {
    if condition1 {
        if condition2 {
            if condition 3 {
                print("come in")
            } else {
                print("bye")
            }
        } else {
            print("bye")
        }
    } else {
        print("bye")
    }
}
```

```swift
func solution() {
    guard condition1 else { return print("bye") }
    guard condition2 else { return print("bye") }
    guard condition3 else { return print("bye") }
    print("come in")
}
```

두 함수 보다 condition3이 true이면 come in을 출력하는 식이다.

이렇게 guard를 사용하면 식이 더 간편해진다는 장점이 있다.