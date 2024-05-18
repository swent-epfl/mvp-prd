# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*

- Kotlin
- Google Maps
- Jetpack Compose
- Stream.io
- SonarCloud
- Firebase

*If applicable, describe essential screens.*

- LoginScreen, AccountSettings, GroupSetting
- SoloStudyHome : where tabs can lead to FlashCardScreen, TimerScreenContent (solo timer), CalendarScreen and ToDoListScreen
- GroupHomeScreen : lead to GroupScreen for each group, can then access TopicScreen, CallLobbyScreen into VideoCallScreen and SharedTimerScreen
- ChatScreen and DirectMessageScreen

## Backend

*Decompose the MVP into functional blocks.*

## Data Model

*What data are you collecting / managing?*

- User : profile username, login email, profile picture, added contacts and localisation if activated
- Groups : name, group profile picture, members, topics, timers
- Topic : name, contents (topic items that contain list of strong users, resources and the parent topic)
- User calendar, todos, solo timer

*How is it organised?*

*Where is it stored?*

- Firebase, local storage on the phone (for the todos)

*How is it shared/copied/cached?*

- All on firebase 

## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

