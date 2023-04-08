# Info.plist

파일들을 분류하던 도중 아래와 같은 오류가 생겼다.

<img src="infoPlist.png" width="600" height="100"/>

오류의 원인은 infoPlist가 원래 있어야 할 자리에 없었다는것

해결법은 
``` 설정 -> buildSettings -> command + f 단축키를 눌러 Info.plist 검색 -> Packaging에 있는 Info.plist File``` 의 위치를 나의 Info.plist가 있는 위치로 바꿔주면 된다! 


<img src="infoPlist위치.png" width="1000" height="50"/>


