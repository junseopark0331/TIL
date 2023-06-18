# naviagationTitle

```swift
self.navigationItem.title = "navigationTitle" 
```

또는

```
self.navigationController?.navigationBar.topItem?.title = "navigationTitle"
```

navigationController?.navigationBar.prefersLargeTitles
이라 적어주면 navigationTitle이 바뀌는걸 볼 수 있다.

또한  
```swift
navigationController?.navigationBar.prefersLargeTitles = True
```
로 설정해주면 화면을 내리면 navigationTitle이 커진다.


tabbarController를 
