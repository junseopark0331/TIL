# if-let 과 guard-let의 차이점

강의를 보면서 if-let 을 쓸 수도 있고 guard-let을 써도 돼요라는 걸 들은 뒤
####if-let과 guard-let의 차이가 무엇일까..?
라는 생각이 들어서 이걸 조사하게 되었다.

### 첫 번째 차이점은 범위이다.
if-let 안에서 선언된 변수는 if 문안에선 밖에 선언된 변수를 사용하지 못한다.
하지만 guard-let 안에서 선언된 변수는 메서드 내에서 지역 상수처럼 사용할 수 있다.

### 두 번째 차이점 else
if-let 은 else 절을 굳이 적어줄 필요가 없다.
하지만 guard-let은 else 절을 꼭 적어줘야 한다.
또한 코드가 종료되었다는 걸 알려주는 continue, break, return, throw가 필요하다.