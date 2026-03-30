# 🌊 SkeletonFlow
**Zero-Duplication Skeleton Loaders for SwiftUI**

[![Swift 5.10](https://img.shields.io/badge/Swift-5.10-orange.svg)](https://swift.org)
[![Platform](https://img.shields.io/badge/Platform-iOS%2015+-blue.svg)](https://apple.com)

`SkeletonFlow` is a lightweight, high-performance framework that transforms your **existing UI** into beautiful skeleton loaders with just one line of code. No replicas, no layout shifts, just smooth transitions.

## ✨ Features
- **Zero UI Duplication:** Automatically mirrors your existing views (cards, circles, etc.).
- **No-Flicker Guard:** Built-in smart delay prevents skeleton "flashing" for fast network requests.
- **ProMotion Ready:** Optimized for 120Hz displays with ultra-smooth shimmer gradients.
- **Deep Customization:** Change colors, speeds, and shapes effortlessly.

## 🚀 Installation (SPM)
Add `https://github.com/yourusername/SkeletonFlow` to your Xcode Swift Packages.

## 💻 Usage
Simply add `.skeleton(active: isLoading)` to any View!

```swift
VStack {
    Circle().frame(width: 50)
    Text("Hello Dev").bold()
}
.skeleton(active: isLoading)
