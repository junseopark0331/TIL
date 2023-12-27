# PropertyWrapper

중복된 코드가 있다면 우리는 대부분 함수로 묶어서 코드수를 줄이곤 한다.

하지만 프로퍼티 단위로 중복이 발생한다면 어떻게 해결해야할까...?

바로 그걸 해결하기 위해 나온게 PropertyWrapper이다.

## 특징
- 지역변수에만 사용이 가능하다.
- struct, enum, class에서 사용이 가능하다.
  

```swift
struct House {
  private var width = 0
  var size: Int {
    get { return width }
    set { width = pow(newValue, 2) }
  }
}

struct KoreaHouse {
  private var _apartment = House()
  private var _villa = House()
  
  var apartmentSize: Int {
    get { return _apartment.size }
    set { _apartment.size = newValue }
  }
  var villaSize: Int {
    get { return _villa.size }
    set { _villa.size = newValue }
  }
}
```

이 코드는 집의 평수를 반환해주는 코드이다.

설정할 값이 없다면 width를 return해주고 설정할 값이 있다면 그 값을 제곱해서 return 해주는 함수이다.

KoreaHouse라는 구조체를 보면 _apartment와 _villa를 똑같이 적었다. 
이런 **중복**된 코드들을 방지하기 위해 PropertyWrapper를 쓰면

```swift
@propertyWrapper
struct House {
  private var width = 0
  var size: Int {
    get { return width }
    set { width = pow(newValue, 2) }
  }
}


struct KoreaHouse {
  @House var apartment: Int = 20
  @House var villa: Int = 30
}

var koreaHouse = KoreaHouse()
print(koreaHouse.apartment, koreaHouse.villa)
```

이렇게 코드를 줄일 수 있다 !! (어머 너무 멋있어 🤩🤩)