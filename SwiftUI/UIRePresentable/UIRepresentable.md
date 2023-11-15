# UIRepresentable

UIKit을 SwiftUI에서 사용할 수 있게끔 만들어주는 프로토콜이다.

**makeUIView(context:) -> UIView**
UIView를 생성하는 메서드로 SwiftUI View의 라이프 사이클동안 한번 호출된다.

**updateUIView(:context:)**
SwiftUI의 View의 state가 바뀔때마다 트리거된다. <br><br><br><br><br><br>




< Activity Indicator >
```swift
struct ActivityIndicator: UIViewRepresentable {
    
    @Binding var isAnimating: Bool
    
    func makeUIView(context: Context) -> UIActivityIndicatorView {
        let view = UIActivityIndicatorView()
        view.style = .large
        
        return view
    }
    
    func updateUIView(_ uiView: UIActivityIndicatorView, context: Context) {
        if isAnimating {
            uiView.startAnimating()
        }
        else {
            uiView.stopAnimating()
        }
    }
}
```


< ContentView >

```swift
struct ContentView: View {
    @State var isAnimating: Bool = false
    
    var body: some View {
        VStack {
            ActivityIndicator(isAnimating: $isAnimating)
            Button(action: { self.isAnimating = !self.isAnimating },
                   label: { Text("show/hide")
                    .foregroundColor(Color.white)
            })
                .background(Color.black)
        }
    }
}
```
