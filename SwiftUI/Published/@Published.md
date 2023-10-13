# Published 

- 변화가 일어났을때 알려주는 property wrapper
- @Published가 붙은 객체에 변화가 생겼을때 그 객체를 사용하는 모든 뷰는 다시 로딩된다.

```swift
class Bag: ObservableObject {
    var items = [String]()
}
```

여기 보이는 코드 같은 경우 @published가 붙어있지 않기 때문에 상태가 변화된걸 알수는 있지만 Published가 없기 때문에 변경된걸 통지할 수 없다.

하지만,
```swift
class Bag: ObservableObject {
    @Published var items = [String]()
}
```

위와 같이 @Published를 붙여주면 변화가 일어날 때마다 알 수 있다.
