# Text

### 정의
- 글자를 보여줄때 쓴다. 
  (UIKit에서의 UILabel과 비슷한듯..?)

### Modifiers
```swift
Text("abcdefghijklmnopqrstuvwxyz")
  .font(.title) // 텍스트의 글꼴 설정
  .fontWeight(.medium) // 텍스트의 글꼴 두께 설정
  .foregroundStyle(.blue) // 텍스트의 색깔 설정
  .background(Color.red) // 백그라운드 색깔
  .lineLimit(1) // 텍스트의 최대 줄 수 제한
  .truncationMode(.head) // 텍스트가 잘리는 경우의 표시 방식을 설정 (어디서부터 ...으로 할지 정하는 부분)
  .cornerRadius(10) // 얼마나 둥글게 해줄지 설정
  .strikethrough() // 텍스트 가운데에 가로 줄 생성
  .underline() // 텍스트 아래에 줄 생성
```

### Frame
```swift
Text("abcdefghijklmnopqrstuvwxyz")
  .frame(width: 100, height: 100) // width와 height만 설정했을 경우 .center가 기본적으로 할당된다.
 ```

### Alignment

```swift
Text("abcdefghijklmnopqrstuvwxyz")
  .multilineTextAlignment(.center) // 여러줄로 구성된 텍스트의 정렬방식 선택
  .truncationMode(.middle) // 텍스트가 잘리는 경우의 표시 방식을 설정 (어디서부터 ...으로 할지 정하는 부분)
```
