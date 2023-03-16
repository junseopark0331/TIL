# self

self는 다른 언어에서도 많이 봤을거에요!
자기 자신을 가리킨다 라고 생각하면 이해하기 쉬워요.
```swift
class PersonA{
    var name: String
    init(name: String){
        self.name = name
    }
}
```
 여기서 self는 ``` 지역번수 -> 매개변수 -> 인스턴스 프로퍼티 순으로  ```무엇을 자칭하는지 찾습니다!
