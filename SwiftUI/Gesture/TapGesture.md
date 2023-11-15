# TapGesture

Tap을 할때마다 사진이 작아지는 화면

```swift
import SwiftUI

struct FirstView: View {
    
    @State private var scale: CGFloat = 1.0
    
    var body: some View {
        Image("Ohtani-Shohei")
            .scaleEffect(scale)
            .gesture(
                TapGesture()
                    .onEnded{ _ in
                        scale -= 0.1
                    })
    }
}


struct FirstView_Previews: PreviewProvider {
    static var previews: some View {
        FirstView()
    }
}

```