# navigationController?.viewControllers[index] as! ViewController

강의를 보던중 이 코드가 무슨말인지 궁금해서 검색해보았다.

검색해보니 자신이 원하는 ViewController로 이동할 수 있는 코드였다.

```swift
@objc func push() {
    //Where you want
    let vc = UIViewController ()
    //print check
    navigationController?.viewControllers.enumerated().forEachf(index,item)in print("count\ (index) \ (item)")}

    // Add vc which is want to move
    navigationController?.viewControllers.insert(vc,at:2)
    // POP to done status view controller
    navigationController?.popToViewController((self.navigationController?.viewControllers[2])!,animated: true)
}

```
