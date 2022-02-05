# Networking

### Making Requests
```swift
let urlString = "https://httpbin.org/get"
let request = MRequest {
  RMethod(.get)
  RUrl(urlString: urlString)
  /// somthing else
}

let socket = MSocket {
  RUrl(urlString: urlString)
  /// somthing else
}

socket.write(string: "something")
```
### Response Handling

- Combine
```swift
request.sink { response in
  debugPrint(response)
}

socket.sink { response in
  debugPrint(response)
```
- ReactiveSwift
```swift
request.producer.startWithValues { response in
  debugPrint(response)
}

socket.producer.startWithValues { response in
  debugPrint(response)
}
```
- RxSwift
```swift
request.subscribe { response in
  debugPrint(response)
}

socket.subscribe { response in
  debugPrint(response)
}
```
## Installation

### Swift Package Manager

The [Swift Package Manager](https://swift.org/package-manager/) is a tool for automating the distribution of Swift code and is integrated into the `swift` compiler. 

Once you have your Swift package set up, adding Networking as a dependency is as easy as adding it to the `dependencies` value of your `Package.swift`.

```swift
dependencies: [
    .package(url: "https://github.com/FullStack-Swift/Networking", .upToNextMajor(from: "1.0.0"))
]
```

# Example

https://github.com/FullStack-Swift/TodoList
