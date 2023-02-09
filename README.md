# swift_calling_initializers_as_closures

Cool thing about Swift initializers: you can call them using dot syntax and pass them as closures! Perfect for mocking dates in tests.

```swift
import Foundation

class Logger {
    private let dateProvider: () -> Date
    
    init(dateProvider: @escaping () -> Date = Date.init) {
        self.dateProvider = dateProvider
    }
    

}

// Easy to test with this way 
Logger(dateProvider: { Date().addingTimeInterval(3600) } )

```

