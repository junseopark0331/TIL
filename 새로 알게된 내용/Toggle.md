# toggle

비밀번호의 텍스트 필드에 값을 입력했을 때, 버튼을 누르면 자신이 입력한 비밀번호를 볼 수 있고 버튼을 다시 누르면 자신이 입력한 값을 볼 수 없게끔 하는 코드를 공부하던 중 toggle에 대해 배웠다.

true와 false 값을 지정해 준 뒤 if 문에 true였을 때의 동작과 false였을 때의 동작을 적기보다 함수를 실행을 한 번씩 실행할 때마다 true/false로 바뀌는 거라 훨씬 하기 편할 것 같다.

버튼을 눌렀을 때 비밀번호의 텍스트를 볼 수 있고 볼 수 없게 하려면

```swift
"비밀번호 텍스트 필드의 이름".isSecureEntry.toggle()
```
위와 같이 코드를 적어주면 된다.