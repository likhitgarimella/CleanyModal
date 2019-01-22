# CleanyModal

[![Version](https://img.shields.io/cocoapods/v/CleanyModal.svg?style=flat)](http://cocoapods.org/pods/CleanyModal)
[![License](https://img.shields.io/cocoapods/l/CleanyModal.svg?style=flat)](http://cocoapods.org/pods/CleanyModal)
[![Platform](https://img.shields.io/cocoapods/p/CleanyModal.svg?style=flat)](http://cocoapods.org/pods/CleanyModal)

## Features

- [x] Present some kind of clean alerts (With same API as UIAlertViewController)
- [x] Add easily Textfields or Custom views as an Alert contains content UIStackView
- [x] Dismiss modal/alert from interaction gesture 
- [x] Present full-custom components as modal from a container view

## Demo

Present customizable and clean alert from provided built-in methods

<img src="https://user-images.githubusercontent.com/3198863/38334727-7820f070-385c-11e8-9aa3-d49bf9262a39.png" width="250" height="445" /> <img src="https://user-images.githubusercontent.com/3198863/38334725-77f10d24-385c-11e8-9e94-89d653628748.png" width="250" height="445" /> <img src="https://user-images.githubusercontent.com/3198863/38334726-780677b8-385c-11e8-9d69-ca5950520252.png" width="250" height="445" /> <img src="https://user-images.githubusercontent.com/3198863/44787753-4c670a00-ab98-11e8-869e-a219c82633c0.jpeg" width="250" height="542" />

Use root modal system to present your custom components and use only the navigation/interaction stuff

<img src="https://user-images.githubusercontent.com/3198863/38334728-783ae638-385c-11e8-82bf-b6fa65e528ce.jpeg" width="250" height="445" />

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

### Preview

Present a clean Alert with default style:

```swift
let alertConfig = CleanyAlertConfig(
  title: "Hello world",
  message: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas sed massa a magna semper semper a eget justo")
let alert = MyAlertViewController(config: alertConfig)

alert.addAction(CleanyAlertAction(title: "OK", style: .default))
alert.addAction(CleanyAlertAction(title: "Cancel", style: .cancel))

present(alert, animated: true, completion: nil)
```

Apply your own style/theme easily :

```swift
class MyAlertViewController: CleanyAlertViewController {
  override init(config: CleanyAlertConfig) {
    config.styleSettings[.tintColor] = .yellow
    config.styleSettings[.destructiveColor] = .pink
    super.init(config: config)
  }
}
```
Need to push customization of your Alerts further ? 

Extend styles settings keys :

```swift
public extension CleanyAlertConfig.StyleKeys {
  public static let shadowOffset = CleanyAlertConfig.StyleKey<CGSize>("shadowOffset")
}
```
Then apply these news keys in viewDidLoad() implementation of your custom alert.
If you only want to present a custom component (not an alert) as a modal, inherit directly form *CleanyModalViewController*

See example project to see all abilities to customize, enjoy !

## Requirements

- iOS 9.0+

## Installation

CleanyModal is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'CleanyModal', '~> 0.1.1'
```

## Author

lory huz, lory.huz@gmail.com

## License

CleanyModal is available under the MIT license. See the LICENSE file for more info.
