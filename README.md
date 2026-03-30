# 🌊 SkeletonFlow

### Zero-Duplication Skeleton Loaders for SwiftUI

![Swift](https://img.shields.io/badge/Swift-5.9%2B-orange)
![Platform](https://img.shields.io/badge/iOS-15%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

---

## ✨ Overview

`SkeletonFlow` is a lightweight and powerful SwiftUI library that transforms your **existing UI** into beautiful, animated skeleton loaders — with **zero duplication**.

No need to create separate placeholder views. Just apply a modifier and your UI becomes a skeleton instantly.

---

## 🚀 Why SkeletonFlow?

Most skeleton libraries require duplicating layouts or building separate placeholder views.

👉 `SkeletonFlow` solves this by:

* Reusing your **actual UI layout**
* Applying a **mask-based shimmer effect**
* Adding a **smart delay** to prevent flickering

---

## 🔥 Features

* 🎭 **Zero UI Duplication**
  Uses your existing SwiftUI views as skeletons

* 🧠 **Smart Delay Engine**
  Prevents flicker for fast-loading APIs

* 🌙 **Dark Mode Adaptive**
  Automatically adjusts colors for light/dark mode

* ⚡ **Performance Optimized**
  Minimal GPU usage, smooth scrolling

* 🎬 **Modern Animations**
  Smooth shimmer using latest SwiftUI animation APIs

* ♿ **Accessibility Friendly**
  Respects Reduce Motion and VoiceOver

---

## 📦 Installation

### Swift Package Manager (Recommended)

In Xcode:

```
File → Add Package Dependencies
```

Enter:

```swift
https://github.com/iosdevarjun/SkeletonFlow
```

---

### CocoaPods

```ruby
pod 'SkeletonFlow'
```

---

## 🛠 Requirements

* iOS 15+
* Swift 5.9+
* Xcode 15+

---

## 💻 Usage

### Basic Example

```swift
import SwiftUI
import SkeletonFlow

struct ContentView: View {
    @State private var isLoading = true

    var body: some View {
        VStack(spacing: 16) {
            Circle()
                .frame(width: 60, height: 60)

            Text("Arjun Dev")
                .font(.headline)
        }
        .skeleton(active: isLoading)
        .onAppear {
            DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
                isLoading = false
            }
        }
    }
}
```

---

## 🎨 Customization

```swift
let config = SkeletonConfig(
    lightBase: .gray.opacity(0.2),
    darkBase: .gray.opacity(0.4),
    lightShimmer: .white.opacity(0.6),
    darkShimmer: .white.opacity(0.2),
    speed: 1.0,
    delay: 0.3
)

yourView.skeleton(active: true, config: config)
```

---

## ⚙️ How It Works

* Applies `.redacted(reason: .placeholder)`
* Overlays a shimmer gradient
* Uses `.mask()` to match your exact UI shape
* Adds delay logic to prevent flickering

---

## 🧪 Testing

Before using in production:

* ✅ Test in Light & Dark mode
* ✅ Verify fast/slow API behavior
* ✅ Check accessibility (Reduce Motion)
* ✅ Validate performance in lists

Run tests:

```
Cmd + U
```

---

## ⚠️ Best Practices

* Avoid using in very large lists without testing performance
* Keep delay small (0.2–0.5s) for best UX
* Disable skeleton as soon as data loads

---

## 🆚 Comparison

| Feature           | SkeletonFlow | Traditional Approach |
| ----------------- | ------------ | -------------------- |
| UI Duplication    | ❌ None       | ✅ Required           |
| Dark Mode Support | ✅            | ⚠️ Manual            |
| Smart Delay       | ✅            | ❌                    |
| Performance       | ⚡ Optimized  | ⚠️ Varies            |

---

## 📈 Roadmap

* [ ] Shimmer direction control (RTL/LTR)
* [ ] macOS support
* [ ] UIKit extension
* [ ] Snapshot testing support
* [ ] Demo showcase app

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a new branch
3. Submit a PR

---

## ⭐ Support

If you like this project:

* ⭐ Star the repo
* 🍴 Fork it
* 📢 Share with the community

---

## 👨‍💻 Author

**Arjun Chudasa**
Senior iOS Developer (Swift | SwiftUI)

---

## 📄 License

This project is licensed under the MIT License.
