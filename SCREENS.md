# Screens

## 1. Splash

Simple splash screen which shows _TV Shows_ logo.

![Splash](/Design/Screenshots/00.png "Splash")

## 2. Login

Shows _TV Shows_ logo on top. In middle there are two input fields, one for email, and *secure* one for password. Login and register buttons are enabled only after both fields are entered.

Login button triggers [sign in API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Sessions/paths/~1users~1sign_in/post). If it’s successful, app navigates to home screen. If authentication fails, app needs to show an error alert.

![Login disabled](/Design/Screenshots/01.png "Login disabled")

Register button triggers [create a user API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Registrations/paths/~1users/post). If it’s successful, app navigates to home screen. If authentication fails, app needs to show an error alert. Register call returns same response data and headers as login call so no need for login call after register.

![Login enabled](/Design/Screenshots/02.png "Login enabled")

There is a _remember me_ checkbox which, when checked, should remember credentials for current user.

Show/hide password button should toggle secure entry on password field, and toggle its icon, depending on current state.

![Login show password](/Design/Screenshots/03.png "Login show password")

## 3. Home screen

Displays a list of TV shows you get from [shows API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Tv-Shows/paths/~1shows/get) in a table view. Endpoint supports pagination as described in API docs.

Tapping on a show navigates to its details screen. Top right navigation item opens a profile details screen where user can display and edit its profile and logout.

![Shows](/Design/Screenshots/04.png "Shows")

## 4. Show details

Displays the show title, cover image, description and lists all reviews in a table view. Show details are fetched from [display show API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Tv-Shows/paths/~1shows~1{id}/get), while reviews are fetched from [reviews API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Reviews/paths/~1shows~1{show_id}~1reviews/get)

![Show details](/Design/Screenshots/07.png "Show details")

In case there are reviews it displays total number of reviews and average rating. On bottom of the screen there is a _Write a review_ button which opens write a review screen. This screen should also have a pull to refresh functionality. 

![Show details with reviews](/Design/Screenshots/08.png "Show details with reviews")

## 5. Write a review

Shows a form for creating a new review. It has a rating picker as a star picker, review text input field and submit button. Each star represents rating from 1 to 5.

![Write a review disabled](/Design/Screenshots/09.png "Write a review disabled")

Submit button should be disabled until rating is picked and some text is entered.

![Write a review enabled](/Design/Screenshots/10.png "Write a review enabled")

Tapping on the submit button should trigger [create a review API call](https://tv-shows.infinum.academy/api/v1/docs/index.html#tag/Reviews/paths/~1reviews/post). If it’s successful an app should navigate back to the previous screen and refresh the list. If there’s an error while creating a new review, present it to the user.

## 6. Profile details

![Profile details](/Design/Screenshots/06.png "Profile details")

Displays user email and his profile photo. Change profile photo button triggers an action to add a profile photo via camera or photo library. Image upload API call is explained under `AWS Upload image` section in API docs. API has a 1MB limit on file size.

> NOTE: You can use UI elements of your choice (e.g. UITableView,  UICollectionView, UIStackView, UIScrollView).
