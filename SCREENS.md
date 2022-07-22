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