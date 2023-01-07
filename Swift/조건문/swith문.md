### switch문

switch문 또한 C언어에서의 switch문과 크게 다르지 않습니다.
```swift
switch 평가대상{
    case 1: 
        print("1")
    case 2:
        print("2")
    default
        print("1,2 숫자가 아니에요!")
}
```
다만 C, 자바와 달리 break 문을 적어줄 필요가 없습니다. 
즉 알아서 실행이 중지가 된다는 뜻이겠죠!

그러면, 여러 개의 케이스를 실행시켜주기 위해서는 어떻게 해야 할까요??
```fallthrough```를 적어주면 됩니다!
