# TV Shows - take home assignment

This document contains all the information and instructions needed for completing the assignment so please read carefully every section before you start solving it.

The final product should be functional app that is consisted of the following screens:
 * Splash screen
 * Login
 * Home
 * Details

You can find a description for every screen [here](SCREENS.md).

## About the app

TV Shows is a simple app that helps you keep track of shows you watched. You can login with it, and see every TV show in a list, including their details and their reviews with ratings.

App design is hosted on Figma [here](https://www.figma.com/file/lnQPlX7RTX8Fqr31FOKEde/tv_shows_ios_2021). If you are not familiar with the Figma, there are exported icons, images and screens in the `Design` folder. You don't have to replicate the design in a pixel, but try to make it as similar as possible.

## API

### Documentation

The API is built using the JSON format. API documentation is available [here](https://tv-shows.infinum.academy/api/v1/docs/index.html).

### Authorization

All requests need to include authorization data in the header of the request, except for request for user login. In order for authorization to work correctly you have to include all necessary fields which are received via sign in/register API calls: `access-token`, `client`, `token-type`, `expiry` and `uid`.

## Networking

### Communication

* Use [Alamofire](https://github.com/Alamofire/Alamofire) for networking purposes
* Make use of it’s [RequestInterceptor](https://github.com/Alamofire/Alamofire/blob/master/Documentation/AdvancedUsage.md#adapting-and-retrying-requests-with-requestinterceptor) for [authentication purposes](#api-authorization)

### JSON decoding

* You can use [Codable](https://developer.apple.com/documentation/swift/codable) or any other JSON decoding framework.

For example:

```swift
AF
    .request(
        "https://tv-shows.infinum.academy/shows/\(show.id)/reviews",
        method: .get
    )
    .validate()
    .responseDecodable(of: ReviewsResponse.self) { response in
        ...
    }
```

## Test user

* email: team.ios@infinum.com
* password: _infinum1_

### Useful references

* [raywenderlich.com iOS tutorials](https://www.raywenderlich.com/category/ios)
* [Infinum blog posts](https://infinum.com/the-capsized-eight)
* [objc.io](https://www.objc.io/)

## How to solve this assignment?

* Use a [GitHub](https://github.com) and create private repository for this project
* Use [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow) branching strategy suitable for working in a team
* Track the time spent working on the project
* Once finished, please invite the following user as collaborator: infinum-ios-leads

## How will we grade your project?

We don't have a formal system for grading, but we will be looking at it in the following way:

### Architecture

* How you organize your code is important
* Although MVC is good enough for a project of this scale, we encourage you to use MVVM or VIPER if you have any experience with these architectures (we have some OS VIPER templates [here](https://github.com/infinum/iOS-VIPER-Xcode-Templates))
* Please use [RxSwift](https://github.com/ReactiveX/RxSwift) or [Combine](https://developer.apple.com/documentation/combine)

### Code style

* We expect consistency in code regarding code style, variable naming and whitespace usage
* If you need some pointers, our handbook has a [chapter on code style](https://github.com/infinum/swift-style-guide)
* [Swiftlint](https://github.com/realm/SwiftLint) is your friend

### App performance

* The app should run immediately after checking out the repo
* There should be no obvious performance issues and crashes

### Advanced Swift usage

Although the app is simple, we still expect you to demonstrate how well you use Swift language, e.g. through the following mechanisms:

* higher-order functions
* protocols
* introuducing type-safe mechanisms, e.g. for view controllers
* memory management
* enums
* etc.

You could do without any of the above probably, but this is a place to show off your skills. Just don't go overboard and overengineer stuff.

### Third party library usage

You're free to implement any third-party library that provides value to your project and saves time. We would love to hear your reasoning behind those choices, so shoot an email our way once you're done with the assignment and tell us what you chose and why.

### Testing

Not mandatory, but very welcome. Stick to unit testing, UI tests would probably take away too much time.

## FAQ

In case of any questions feel free to reach out. Send email to ios.leads@infinum.hr and someone will get back to you as soon as possible.