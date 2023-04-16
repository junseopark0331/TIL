# json 데이터를 문자열로 보는 방법

```swift
dump(String(data: data, encoding: .utf8))
```

네트워크 통신 부분에 위와 같은 코드를 적으면 볼 수 있다.

데이터를 더 편하게 보기 위해 dump로 적은거라 print로 하셔도 문제는 없습니다!