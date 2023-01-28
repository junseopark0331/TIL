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

e




인용 : https://babbab2.tistory.com/116