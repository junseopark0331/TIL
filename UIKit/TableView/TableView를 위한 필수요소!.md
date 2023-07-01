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

UITableViewDelegate를 extension으로 연결해준 뒤,

```swift
extension MovieListViewController: UITableViewDelegate {
    
    func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        
        performSegue(withIdentifier: "toDetail", sender: indexPath)
    }
    
    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        if segue.identifier == "toDetail" {
            let detailVC = segue.destination as! DetailViewController
            
            let array = movieDataManager.getMovieData()
            
            let indexPath = sender as! IndexPath
            
            detailVC.movieData = array[indexPath.row]
        }
        
    }
    
}
```

와 같이적어주면 다음에 넘어갈 ViewController를 알려줄 수 있다.
