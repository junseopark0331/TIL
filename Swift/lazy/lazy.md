# lazy

지연초기화를 한다.
즉, 프로퍼티를 필요할때 초기화 시켜준다는 말이다.


lazy를 사용하게 되면 사용할때만 호출이 되기 때문에 불필요한 성능저하나 공간낭비를 줄일 수 있다.

### lazy 특징
1. lazy는 var와 함께 선언된다.
2. struct와 class 내에서만 사용할 수 있다.
3. thread safe 하지 않는다

### lazy var 예시
```swift
// lazy를 사용하지 않은 경우
struct WithoutLazy {
    var value: Int = {
        print("WithoutLazy 초기화 중")
        return 1
    }()
    
    init() {
        print("WithoutLazy 인스턴스 생성")
    }
}

// lazy를 사용한 경우
struct WithLazy {
    lazy var value: Int = {
        print("WithLazy 초기화 중")
        return 1
    }()
    
    init() {
        print("WithLazy 인스턴스 생성")
    }
}

// 인스턴스 생성
let withoutLazy = WithoutLazy()
// WithoutLazy 초기화 중
// WithoutLazy 인스턴스 생성
var withLazy = WithLazy()
// WithLazy 인스턴스 생성

// 속성 접근
print("\nWithoutLazy의 value 접근")
// WithoutLazy의 value 접근
print(withoutLazy.value)
// 1

print("\nWithLazy의 value 접근")
// WithLazy의 value 접근
// WithLazy 초기화 중
print(withLazy.value)
// 1

```