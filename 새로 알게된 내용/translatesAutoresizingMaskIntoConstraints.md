# translatesAutoresizingMaskIntoConstraints

클론코딩을 하는데 이게 뭔지 몰라 내용에 정리해본다!

일단 AutoresizingMask가 뭔지 알아보자!

우리가 원하는 것이 폰의 올바를 위치에 나오게끔 하나하나 constraint를 잡아준다.
autosizing을 선택하게 되면 constraint가 없어도 잘 늘어나는걸 볼 수 있다.

translatesAutoresizingMaskIntoConstraints을 true로 해주면 View의 크기와 위치를 완전히 지정하고 추가 constraint를 적을 수 없다. 
즉 View의 크기는 완전히 고정된 상태이기 때문에 우리가 " 이 부분은 바꿔주는게 좋을 것 같은데? " 와 같은 생각이 들어도 전혀 바꿔줄 수 없는 상태가 된다.

그렇기에 평소에 수정할 사항이 많은 경우에는 
```swift
self.translatesAutoresizingMaskIntoConstraints = false
```
와 같이 적어준다!
