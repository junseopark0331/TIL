# makeKeyAndVisible()

```swift
window = UIWindow(frame: UIScreen.main.bounds)
window.rootViewController = myVC
window?.makeKeyAndVisible()
````

위와 같은 코드를 자주보게 될텐데  
```swift
window?.makeKeyAndVisible()
````

의 의미는 여러개의 window가 존재할때 가장 앞에 배치한다는 뜻이다!