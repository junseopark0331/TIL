# MVVM

Model, View, ViewModel로 이루어진 아키텍처 패턴

<img src="숫자 키보드.png" width="400" height="300"/>

### Model
- 데이터, 네트워크 로직, 비즈니스 로직을 담고 있다.
  
### View
- 사용자가 보이는 화면이다.
- Model을 알고 있어서는 안된다.
- 사용자로부터 상호작용을 하고 이에 대한 처리를 ViewModel에게 부탁한다.

### ViewModel
- View로부터 전달받은 요청을 