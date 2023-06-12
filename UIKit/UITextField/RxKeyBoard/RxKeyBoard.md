# RxKeyBoard

텍스트필드를 클릭하면 버튼도 같이 올라오게 하는 기능을 구현하고 싶어서 RxKeyBoard에 대해 알아봤다.

RxKeyBoard를 사용하기 위해서는 RxSwift, RxKeyboard, RxCocoa를 import 해줘야 한다.

```swift
func setUpOutputBinding() {
        
        RxKeyboard.instance.visibleHeight
            .skip(1)    // 초기 값 버리기
            .drive(onNext: { keyboardVisibleHeight in
                
                self.confirmationButton.snp.updateConstraints {
                    $0.bottom.equalTo(self.view.safeAreaLayoutGuide).inset(keyboardVisibleHeight)
                        }
            })
            .disposed(by: disposeBag)
        
    }
```

setUpOutputBinding()을 viewDidLoad에 넣어주면 실행된다.