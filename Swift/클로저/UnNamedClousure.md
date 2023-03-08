### UnNamedClosure란! 보통 저희가 사용하는 클로저를 말해요!

클로저를 표현할때에는 이렇게 실행시켜줄 수 있어요.
```swift
{(Parameter) -> Return Type in
    실행할 구문 

}
```

``` (Parameter) -> Return Type ```이 클로저 헤드부분이고,
``` 실행할 구문``` 이 바디 부분이에요!

이때 어떤게 클로저 헤드부분이고 바디 부분인지 헷갈릴수도 있잖아요, 그래서 붙여주는게 "in" 이에요! 

```swift
let closure = { (name: String) -> () in
    print("My name is \(name)")
}

closure(name: "Junseopark") // error
closure("Junseopark") // My name is Junseopark

```
클로저에서는 ArgumentLabel(인자 이름)을 적어주면 에러가 나기 때문에 ArgumentLabel을 생략해주고 적어야 합니다! 


