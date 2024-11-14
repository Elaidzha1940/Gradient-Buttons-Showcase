⌨️ Gradient-Buttons-Showcase
=====

### Description
Demonstrates how to create gradient background buttons in SwiftUI and UIKit. Includes examples for creating buttons, setting up their gradient backgrounds, and handling tap actions.

### SwiftUI Example

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
                            Color.green.opacity(0.7),
                            Color.green
                        ]),
                        startPoint: .top,
                        endPoint: .bottom
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

### Example Usage:
```swift
// In your SwiftUI view, call the PromoButtonView to display the button
PromoButtonView()
    .padding(.bottom, 25)
```
-----

### UIKit Example

```swift
private func setupPromoButton(in view: UIView, title: String = "Create Business", bottomOffset: CGFloat = -25) {
    let promoButton = UIButton(type: .system)
    
    promoButton.setTitle(title, for: .normal)
    promoButton.setTitleColor(.white, for: .normal)
    promoButton.titleLabel?.font = UIFont.systemFont(ofSize: 18, weight: .semibold)
    
    promoButton.backgroundColor = .clear
    
    // Setup the gradient layer
    let gradientLayer = CAGradientLayer()
    gradientLayer.colors = [
        UIColor.white.withAlphaComponent(0.7).cgColor, // Light white with reduced saturation
        UIColor.green.withAlphaComponent(0.7).cgColor, // Light green with reduced saturation
        UIColor.systemGreen.cgColor // Full green color
    ]
    gradientLayer.locations = [0.0, 0.5, 1.0] // Smooth transition through the middle
    
    // Apply gradient to cover the entire button
    gradientLayer.frame = CGRect(x: 0, y: 0, width: 300, height: 55)
    gradientLayer.cornerRadius = 28 // Rounded corners
    
    // Insert gradient layer as background
    promoButton.layer.insertSublayer(gradientLayer, at: 0)
    promoButton.layer.cornerRadius = 28
    promoButton.clipsToBounds = true
    
    // Add action for button tap
    promoButton.addTarget(self, action: #selector(didTapPromoButton), for: .touchUpInside)
    
    // Set up constraints for the button
    promoButton.translatesAutoresizingMaskIntoConstraints = false
    view.addSubview(promoButton)
    
    NSLayoutConstraint.activate([
        promoButton.bottomAnchor.constraint(equalTo: view.safeAreaLayoutGuide.bottomAnchor, constant: bottomOffset),
        promoButton.centerXAnchor.constraint(equalTo: view.centerXAnchor),
        promoButton.widthAnchor.constraint(equalToConstant: 300),
        promoButton.heightAnchor.constraint(equalToConstant: 55)
    ])
}
```

### Example Usage:
```swift
// In your view controller, call the function to add the button
setupPromoButton(in: self.view)
```

-----


