# Binding


```swift
@Binding var isActivated: Bool
```

- @State로 어떤 프로퍼티의 값을 지정했다면 다른 값으로 재할당이 불가하지만 **@Binding** 변수를 사용한다면 가능하다.

- binding은 속성에 대한 참조이며 해당 속성을 소유하고 있는 뷰 외부에서 값에 접근하고 변경할 수 있어야한다. 그렇기 때문에 private으로 선언을 해준다면 외부에서 접근이나 변경이 어렵기 때문에 private으로 선언하지 않는걸 추천한다.



