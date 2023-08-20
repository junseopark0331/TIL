# guard와 if의 차이

## if

### 작성방법

```swift
if 조건문 {
    조건문 만족시 실행
}
```
또는
```swift
if 조건문 {
    조건문 만족시 실행
} else {
    조건문 불만족시 실행
}
```
## guard

### 작성방법

```swift
guard 조건문 else {
    조건문 불만족시 실행
    return
} 
조건 만족시 실행하는 식
```

- guard구문은 함수나 메서드 혹은 반복문 안에서만 사용할 수 있다는 한계점이 있다. 
- guard문을 사용하면 항상 else문을 적어야한다.
- guard의 else문에서는 항상 return, break, throw, continue로 종료시킨다.
- 

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

이렇게 guard를 사용하면 가독성이 더 좋아지는 장점이 있다.