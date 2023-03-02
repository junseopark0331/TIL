### ViewController의 LifeCycle

ViewController는 
``` loadView -> viewDidLoad -> viewWillAppear -> viewDidAppear -> viewWillDisappear -> viewDidUnload```
와 같은 순서로 View가 생성됩니다.

#### 1. viewDidLoad
viewDidLoad 같은 경우 View를 실행시켰을때 가장 처음 실행되는 함수에요!
그렇기에 코드를 실행시켰을 때 제일 먼저 화면에 나타내고 싶은 부분들을 여기에 적어주면 됩니다! 
