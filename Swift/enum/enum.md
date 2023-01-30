### Enum

**enum**은 공통된 주제에 대해서 이미 **정해놓은 값** 만 받고 싶을 때 사용해요! 

사용 방법 : 
```swift
enum major{
    case iOS
    case Android
    case Frontend
    case Backend
}

```
위와 같이 열거형을 정의할 수 있어요!
또는
```swift
enum major{
    case iOS, Android, Frontend, Backend
}

```
위와 같이 적어줄 수도 있어요!
(이렇게 적어주면 원시값이 없는 열거형 입니다)

. (점문법)을 이용해 자신이 선언한 case에 대해 접근을 할 수 있어요!
위의 방법을 사용하면 오타의 가능성 ⬇, 코드의 가독성 ⬆

위의 case를 지정할 때, 저희는 아무 값도 대입하지 않았었어요.
이 case에도 원시값을 정해줄 수 있는데 이때의 원시값을 **Raw Value**라고 합니다! 
이때 Raw Value가 될 수 있는 자료형은 
``` Number Type, Character Type, String Type```으로 
총 3가지가 있어요! 

### Number Type
```swift 
enum Major: Int{

    case iOS // 0
    case Android // 1
    case Frontend // 2
    case Backend // 3
}
```
이렇게 아무값을 설정해주지 않으면 0부터 시작되어 그전 case로부터 1씩 추가된 값이 설정됩니다!

인용 : https://babbab2.tistory.com/116