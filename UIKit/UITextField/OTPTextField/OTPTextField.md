# OTPTextField

OTP란? One Time Password의 약자로 무작위 번호연속 알고리즘에 따라 매 시간마다 변경되는 추정할 수 없는 비밀번호 생성을 이용하는 보안 시스템

이메일 인증번호, 문자메시지 인증번호를 입력하는 텍스트필드를 구현할때 어떤식으로 검색을 해야될지 고민이 되었었는데 OTPTextField라 검색을 해보니 찾을 수 있었다!

구현을 할때 도움이 되면 좋겠다.

https://github.com/AbdelrhmanKamalEliwa/AEOTPTextField

참고하면 좋을 라이브러리!

```swift
private let certificationNumberTextField = AEOTPTextField().then{
        $0.otpFont = .I_A(size: 32, family: .regular)
        $0.otpTextColor = UIColor(rgb: 0x767676)
        $0.otpCornerRaduis = 5
        $0.configure(with: 4)
    }
```

위와 같이 사용하면 좋을 듯 하다!