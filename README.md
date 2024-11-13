# Gradient-Buttons-Showcase
Gradient Buttons Showcase

## Описание

## Примеры использования

### SwiftUI Пример

#### Горизонтальный градиент
```swift
Button(action: {
    print("Горизонтальный градиент")
}) {
    Text("Горизонтальный")
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

### Вертикальный градиент
```swift
Button(action: {
    print("Вертикальный градиент")
}) {
    Text("Вертикальный")
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

-----
