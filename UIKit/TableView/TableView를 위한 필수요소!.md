# TableView를 그리기 위한 필수 요소!

TableView를 그리기 위해 필수로 구성해야 되는 메서드가 있다.

일단 extension을 사용해 해당하는 ViewController에 UITableViewDataSource을 상속받고, 

```swift 
func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
    return Int
}
````
와 
```swift
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
    return cell
}
```
메서드를 적어줘야 한다!
