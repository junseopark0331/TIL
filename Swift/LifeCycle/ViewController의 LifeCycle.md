### ViewController의 LifeCycle

ViewController는 
``` loadView -> viewDidLoad -> viewWillAppear -> viewDidAppear -> viewWillDisappear -> viewDidUnload```
와 같은 순서로 View가 생성됩니다.

#### 1. viewDidLoad
viewDidLoad 같은 경우 View를 실행시켰을때 가장 처음 실행되는 함수에요!
그렇기에 코드를 실행시켰을 때 제일 먼저 화면에 나타내고 싶은 부분들을 여기에 적어주면 됩니다! 

저희가 평소 사용하는 뷰컨트롤러들은 스택형태 (Last-in First-Out )로 관리가 되기때문에 이미 백버튼을 누르게 되면 현재의 화면이 pop이 되고 그 전의 화면이 스택의 top 이 됩니다. 

pop이 되었다는 말은 메모리에서 사라지기 때문에 사라진 화면을 다시 실행시키기 위해서는 viewDidLoad가 다시 실행이 됩니다! 