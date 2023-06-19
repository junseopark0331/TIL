# Generic

과제를 하면서 코드를 배껴썼는데 그 코드를 본 형우형께서 Generic에 대해 알아보라고 하셔서 글을 쓴다!

제너릭 정의를 봐보면 **제네릭이란 타입에 의존하지 않는 범용 코드를 작성할 때 사용한다. 제네릭을 사용하면 중복을 피하고, 코드를 유연하게 작성할 수 있다.** 이렇게 나와있다.

말로만 봐서는 무슨말인지 모르겠으니 바로 실전으로 가보자!!

```swift
func twoParameter(_ a: Int, _ b: Int){
    print("a: \(a)")
    print("b: \(b)")
}

twoParameter(1, 4)
```
twoParameter라는 함수이다.

파라미터 타입은 Int이고 Int가 아닌 다른 타입의 값을 넣게 되면 오류가 난다!

아... 근데 난 Double타입의 값도 받고 싶고, String타입의 값도 받고 싶으면 

```swift
func twoParameter(_ a: Double, _ b: Double){
    print("a: \(a)")
    print("b: \(b)")
}

twoParameter(3.14, 1.23)

func twoParameter(_ a: String, _ b: String){
    print("a: \(a)")
    print("b: \(b)")
}

twoParameter("junseo", "park")
```
이렇게 각 타입마다 함수를 만들어줘야 할까...? 라는 생각이 들수도 있다.

이걸 보완하기 위해 나타난게 바로 **Generic**!

```swift
func generic<T>(_ a: T, _ b:T){
    print("a: \(a)")
    print("b: \(b)")
}
generic(3, 4) // a: 3 b: 4
generic(3.14, 1.23) // a: 3.14 b: 1.23
generic("junseo", "park") // a: junseo b: park
````

이렇게 <> 꺽새를 이용해 타입처럼 사용할 이름을 정해주면 T를 타입처럼 이용할 수 있다!

T라는 새로운 형식이 생성되는게 아니라 실제 함수가 호출될 때 해당 파라미터의 타입으로 대체되는 placeholder이다!

```swift
func generic<T>(_ a: T, _ b:T){
    print("a: \(a)")
    print("b: \(b)")
}
generic("하핳", 4)
````

이렇게 타입은 모두 같은 T로 설정을 하고, String 타입인 "하핳"을 넣고 Int 타입인 4를 넣게되면 문제가 생기지 않을까??

**문제가 생긴다!!**


문제가 생기는 이유는 첫번째 파라미터의 타입인 String으로 T가 설정이 되었는데 갑자기 4가 들어와서 그런겨!!

**음... 그러면 어떻게 해결할 수 있나요??**

```swift
func generic<A, B>(_ a: A, _ b:B){
    print("a: \(a)")
    print("b: \(b)")
}
generic("하핳", 4)
````

이렇게 서로 다른 타입 파라미터로 설정을 해주면 해결된다!! 

다른 부분도 공부하고 올려볼게요..