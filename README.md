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

### Диагональный градиент
```swift
Button(action: {
    print("Диагональный градиент")
}) {
    Text("Диагональный")
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

### UIKit Пример

Создание кнопки с градиентом
```swift
private func setupPromoButton() {
    let promoButton = UIButton(type: .system)
    
    // Настройка текста кнопки
    promoButton.setTitle("Создать бизнес", for: .normal)
    promoButton.setTitleColor(.white, for: .normal)  // Белый цвет текста
    promoButton.titleLabel?.font = UIFont.systemFont(ofSize: 18, weight: .semibold)
    
    // Настройка фона кнопки
    promoButton.backgroundColor = .clear  // Прозрачный фон
    
    // Настройка градиентного слоя
    let gradientLayer = CAGradientLayer()
    gradientLayer.colors = [
        UIColor.white.withAlphaComponent(0.7).cgColor, // Белый с уменьшенной насыщенностью
        UIColor.systemGreen.withAlphaComponent(0.8).cgColor, // Полупрозрачный зелёный
        UIColor.systemGreen.cgColor // Полный зелёный
    ]
    gradientLayer.locations = [0.0, 0.5, 1.0] // Плавный переход по центру
    gradientLayer.startPoint = CGPoint(x: 0.5, y: 0) // Верхняя центральная точка
    gradientLayer.endPoint = CGPoint(x: 0.5, y: 1)   // Нижняя центральная точка
    
    // Убедимся, что градиент полностью покрывает кнопку
    gradientLayer.frame = CGRect(x: 0, y: 0, width: 300, height: 55)
    gradientLayer.cornerRadius = 28 // Мягкие углы

    // Добавляем градиентный слой на кнопку
    promoButton.layer.insertSublayer(gradientLayer, at: 0)
    promoButton.layer.cornerRadius = 28
    promoButton.clipsToBounds = true
    
    // Добавление действия при нажатии
    promoButton.addTarget(self, action: #selector(didTapPromoButton), for: .touchUpInside)
    
    // Установка ограничений для кнопки
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
    guard let url = URL(string: "https://app.finolog.ru/") else {
        print("Некорректный URL")
        return
    }
    UIApplication.shared.open(url, options: [:], completionHandler: nil)
}
```


-----
