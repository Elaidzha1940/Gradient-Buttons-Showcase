⌨️ Gradient-Buttons-Showcase
=====

## Description
This project demonstrates how to create buttons with gradient backgrounds in SwiftUI and UIKit. Examples include horizontal, vertical, and diagonal gradients, as well as how to set up a gradient button in UIKit.

Usage Examples
-----

## SwiftUI Example

#### Horizontal Gradient
```swift
Button(action: {
    print("Horizontal Gradient")
}) {
    Text("Horizontal")
        .font(.system(size: 18, weight: .semibold))
        .foregroundColor(.white)
        .frame(width: 300, height: 55)
        .background(
            LinearGradient(
                gradient: Gradient(colors: [Color.red, Color.blue]),
                startPoint: .leading,
                endPoint: .trailing
            )
        )
        .cornerRadius(28)
}

```

### Vertical Gradient
```swift
Button(action: {
    print("Vertical Gradient")
}) {
    Text("Vertical")
        .font(.system(size: 18, weight: .semibold))
        .foregroundColor(.white)
        .frame(width: 300, height: 55)
        .background(
            LinearGradient(
                gradient: Gradient(colors: [Color.green, Color.yellow]),
                startPoint: .top,
                endPoint: .bottom
            )
        )
        .cornerRadius(28)
}
```

### Diagonal Gradient
```swift
Button(action: {
    print("Diagonal Gradient")
}) {
    Text("Diagonal")
        .font(.system(size: 18, weight: .semibold))
        .foregroundColor(.white)
        .frame(width: 300, height: 55)
        .background(
            LinearGradient(
                gradient: Gradient(colors: [Color.purple, Color.orange]),
                startPoint: .topLeading,
                endPoint: .bottomTrailing
            )
        )
        .cornerRadius(28)
}
```
-----


## UIKit Example

### Creating a gradient button
```swift
private func setupPromoButton() {
    let promoButton = UIButton(type: .system)
    
    // Setting the button title
    promoButton.setTitle("Button", for: .normal)
    promoButton.setTitleColor(.white, for: .normal)  // White text color
    promoButton.titleLabel?.font = UIFont.systemFont(ofSize: 18, weight: .semibold)
    
    // Setting the background color
    promoButton.backgroundColor = .clear  // Transparent background
    
    // Setting up the gradient layer
    let gradientLayer = CAGradientLayer()
    gradientLayer.colors = [
        UIColor.white.withAlphaComponent(0.7).cgColor, // White with reduced opacity
        UIColor.systemGreen.withAlphaComponent(0.8).cgColor, // Semi-transparent green
        UIColor.systemGreen.cgColor // Full green
    ]
    gradientLayer.locations = [0.0, 0.5, 1.0] // Smooth transition in the middle
    gradientLayer.startPoint = CGPoint(x: 0.5, y: 0) // Top center point
    gradientLayer.endPoint = CGPoint(x: 0.5, y: 1)   // Bottom center point
    
    // Ensuring the gradient covers the button entirely
    gradientLayer.frame = CGRect(x: 0, y: 0, width: 300, height: 55)
    gradientLayer.cornerRadius = 28 // Soft corners

    // Adding the gradient layer to the button
    promoButton.layer.insertSublayer(gradientLayer, at: 0)
    promoButton.layer.cornerRadius = 28
    promoButton.clipsToBounds = true
    
    // Adding action when the button is tapped
    promoButton.addTarget(self, action: #selector(didTapPromoButton), for: .touchUpInside)
    
    // Setting constraints for the button
    promoButton.translatesAutoresizingMaskIntoConstraints = false
    view.addSubview(promoButton)
    
    NSLayoutConstraint.activate([
        promoButton.bottomAnchor.constraint(equalTo: view.safeAreaLayoutGuide.bottomAnchor, constant: -25),
        promoButton.centerXAnchor.constraint(equalTo: view.centerXAnchor),
        promoButton.widthAnchor.constraint(equalToConstant: 300),
        promoButton.heightAnchor.constraint(equalToConstant: 55)
    ])
}

@objc func didTapPromoButton() {
    guard let url = URL(string: "") else {
        print("Invalid URL")
        return
    }
    UIApplication.shared.open(url, options: [:], completionHandler: nil)
}
```

-----
