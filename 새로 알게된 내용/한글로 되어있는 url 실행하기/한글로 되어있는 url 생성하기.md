# 한글로 되어있는 url 생성하기

쿼리스트링으로 한글을 포함한 qr 코드를 생성하려고 했는데 생성이 되지 않아 이유가 궁금했다.
이유는 url에 한글이 포함되어있어서 인데 위와 같은 코드를 입력해주면 해결된다!
```swift
guard let encodedStr = connectURL.addingPercentEncoding(withAllowedCharacters: .urlQueryAllowed) else { return }
```
