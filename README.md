# Learn Swift LA & Swift Coders LA Meeting notes  

This repository contains the notes for the monthly meeting for:

RSVP [Learn Swift LA](https://www.meetup.com/LearnSwiftLA/)

RSVP [Swift Coders LA](https://www.meetup.com/SwiftCoders-L-A/)

Please note that the notes for the saturday peer labs are located at [aflockofswifts.org](https://aflockofswifts.org)

## 2021-3-Feb Modular Development with Swift Package Manager

We created a [Prefix Trie](https://github.com/joshuajhomann/PrefixTrie) Swift Package from my old [Boggle project](https://github.com/joshuajhomann/Boggle-SwiftUI).
  * Create a new package in xcode
  * Add the files you want to include in the package
  * Make sure you mark anything that needs to be visible outside of the package as `public`and replace references to `Bundle.main` with `Bundle.module`
  * Edit the package file to:
    1. include the platforms you want to support: ` platforms: [ .iOS(.v14), .macOS(.v11), .tvOS(.v14), .watchOS(.v7)],`
    2. export the binary json: `resources: [.copy("words.json")]`
We then created the [Anagram Project](https://github.com/joshuajhomann/Anagram)
  * Create a multiplatform iOS and WatchOS project
  * Add two local packages `AnagramUI` and `AnagramLogic`
  * Edit both packages to support watchOS and iOS
  * Add `AnagramLogic` and a dependency to `AnagramUI`
  * Add `Algorithms` to `AnagramLogic`.  Note that package manager resolves the depdency for `Numerics` automatically since its specified in `Algorithms`
  * We created the common view logic in `AnagramUI` and imported this into both the watch target and the iOS target
  * We created the `AnagramService` in the `AnagramLogic` package and imported this into the `AnagramLogic` package. 
  
[Additional references](https://developer.apple.com/documentation/swift_packages) 

![image](https://github.com/joshuajhomann/Anagram/preview.gif)
 
## 2021-6-Jan SwiftUI Animation

We covered the following:
* `UIKit` a playground showing an imperative animation in UIKit
* `Implicit` a playground showing an implicit animation that occurs when a view changes for any reason
* `Timing Curves` and `Springs`: visualizations of the various timing curves in SwiftUI
* `Explict` & `Explict2`: demonstrations of explicit animations to independently animate different aspects of a view
* `Transition`: a playground showing the use of `AnyTransition` to animate views in and out of the view hierarchy
* `MatchedGeometryEffect`: a playground showing how to perform a sematic move between different nodes in the view hierarchy by using a `matchedGeometryEffect`
* `AnimatableModifier`: a custom sine wave and color interpolating `AnimatableModifier`
  
[Reversi Sample project](https://github.com/joshuajhomann/Reversi-SwiftUI-Animation)  

![Reversi](https://github.com/joshuajhomann/Reversi-SwiftUI-Animation/blob/master/preview.gif)

