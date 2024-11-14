⌨️ Gradient-Buttons-Showcase
=====

## Description
This project demonstrates how to create buttons with gradient backgrounds in SwiftUI and UIKit. Examples include horizontal, vertical, and diagonal gradients, as well as how to set up a gradient button in UIKit.

Usage Examples
-----

## SwiftUI Example

```swift
import SwiftUI

struct PromoButtonView: View {
    var title: String = "Create Business"
    
    var body: some View {
        Button(action: {
            // Handle button tap action
            didTapPromoButton()
        }) {
            Text(title)
                .font(.system(size: 18, weight: .semibold))
                .foregroundColor(.white)
                .padding()
                .frame(width: 300, height: 55)
                .background(
                    LinearGradient(
                        gradient: Gradient(colors: [
                            Color.white.opacity(0.7),
                            Color.green
                        ]),
                        startPoint: .leading,
                        endPoint: .trailing
                    )
                )
                .cornerRadius(28)
        }
    }
    
    // Example action method for the button
    func didTapPromoButton() {
        // Handle tap event
        print("Promo button tapped!")
    }
}
```
-----

## UIKit Example

```swift

```


-----
