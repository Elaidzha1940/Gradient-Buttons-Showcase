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

### Vertical Gradient

```swift

```



### Diagonal Gradient

```swift

```
-----
