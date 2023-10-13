# Dispose

Disposable -> 사용 후 버리는 리소스

dispose() -> 모든 옵저버들과 방출된 리소스들에 대해서 구독을 해제하는 것이다.

Observer는 Observable을 "구독"할 수 있다.
이때 사용하는 메서드는 **subscribe**이다.

계속 구독을 하며 Observable에 대한 정보를 받다가 더 이상 구독을 할 필요가 없으면 어떻게 할까??
이때 사용하는 메서드가 **disposable**이다.

```swift
let sodeulDisposable = sodeulButton.rx.tap
    .subscribe(onNext: {
    print("소들이 버튼 눌림!")
})
 
sodeulDieButton.rx.tap
    .subscribe(onNext: {
    sodeulDisposable.dispose()
    print("소들이 버튼을 구독 해제하자!")
})
```

소들이님의 예시 코드이다.

sodeulDieButton 클릭 후 sodeulButton의 dispose() 메서드를 실행하기 때문에 sodeulButton을 더 클릭하더라도 "소들이 버튼 눌림!" 이 출력되지 않는다.

이렇게 dispose 메서드를 실행하는 가장 큰 이유는 **메모리 관리**를 위해서다.

deinit을 해주지 않으면 메모리 누수가 발생한다.