# LongPressGesture

1초동안 계속 사진을 누르면 사진이 작아지는 뷰

```swift
import SwiftUI

struct LongPressGestureView: View {
    
    @State private var scale: CGFloat = 1.0
    
    var body: some View {
        Image("Ohtani-Shohei")
            .scaleEffect(scale)
            .gesture(
                LongPressGesture(minimumDuration: 1)
                    .onEnded { _ in
                        scale /= 2
                    }
            )
    }
}


struct LongPressGestureView_Previews: PreviewProvider {
    static var previews: some View {
        LongPressGestureView()
    }
}

```