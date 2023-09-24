# State

```swift
@State var isActivated: Bool = false
```

- 뷰 내부에서 특정 View의 상태를 나타내는 **변수**이다. 그렇기에 var가 아닌 let으로 선언해주면 오류가 난다!!

- private을 붙이지 않으면 View 밖에서도 사용할 수 있지만 예상치 못한 일이 일어날 수 있기 때문에 대부분 **private**을 붙여서 사용한다.

- 변수값이 변경되면 View를 다시 랜더링한다. 그렇기에 항상 최신값을 가진다.

- 내부의 값이 변경되면 View는 사라지게 되고 바뀐 값을 가진 View가 다시 생성된다.

