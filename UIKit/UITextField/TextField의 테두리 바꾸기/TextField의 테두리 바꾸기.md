# TextField의 테두리 바꾸기

```swift
textField.borderStyle = .""
```
 "" 안에 원하는 스타일을 적으면 TextField의 테두리 스타일을 바꿀 수 있다.

 #### line
```swift
textField.borderStyle = .line 
```
<img src="line으로 설정.png" width="400" height="100"/>

와 같이 입력하면 이렇게 선으로 테두리가 되어있는 걸 볼 수 있다.

#### none
```swift
textField.borderStyle = .none
```
<img src="none으로 설정.png" width="400" height="100"/>

와 같이 입력하면 이렇게 테두리가 아무것도 없는걸 볼 수 있다.

#### roundedRect
```swift
textField.borderStyle = .roundedRect
```
<img src="roundRect로 설정.png" width="400" height="100"/>

와 같이 입력하면 이렇게 둥글게 테두리가 되어있는 걸 볼 수 있다.

다른 테두리가 궁금하다면 https://boidevelop.tistory.com/62 이걸 참고해보면 좋을듯하다.
