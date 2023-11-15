# DragGesture

드래그를 한 뒤 때면 다시 본 위치로 돌아오는 화면
```swift
import SwiftUI

struct DragGestureView: View {
    @State private var dragOffset = CGSize.zero
 
    var body: some View {
        VStack {
            Image("Ohtani-Shohei")
                .resizable()
                .scaledToFit()
                .offset(dragOffset)
                .gesture(
                    DragGesture()
                        .onChanged { gesture in
                            dragOffset = gesture.translation
                        }
                        .onEnded { gesture in
                            dragOffset = .zero
                        }
                )
        }
    }
}

struct DragGestureView_Previews: PreviewProvider {
    static var previews: some View {
        DragGestureView()
    }
}

```