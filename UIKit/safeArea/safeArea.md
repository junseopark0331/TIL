# safeArea 

safeArea는 콘텐츠가 제대로 보일 수 있는 부분에만 우리가 원하는 뷰를 넣을 수 있게 도와주는 기능이다.

Status bar 와 내비게이션 바, 툴바, Home Indicator 영역을 제외한 부분을 보통 safeArea로 지정한다.

그렇기 때문에 평소에 autoLayout을 할 때 view가 아닌 safeArea를 기준으로 view를 그리면 오류가 덜 생길 것이다.


leading과 trailing에 safeAreaLayoutGuide를 생기면 우리가 생각했던 위치에 놓여있지 않을수도 있기 때문에 보통 top과 bottom을 설정해줄때 safeAreaLayoutGuide를 많이 사용한다.