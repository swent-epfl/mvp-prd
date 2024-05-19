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

- LoginScreen, CreateAccount, AccountSettings, GroupSetting, TopicSettings: multiple screens that allow the user to create/edit different data related to themselves or their teammates
- SoloStudyHome : where tabs can lead to FlashCardScreen, TimerScreenContent (solo timer), CalendarScreen and ToDoListScreen
- GroupHomeScreen : lists all the groups a user is in. Eeach item of the list leads to GroupScreen, that then gives access to TopicScreen, CallLobbyScreen into VideoCallScreen, and SharedTimerScreen
- ChatScreen and DirectMessageScreen : ChatScreen where each chat (Group, Topic or Private) display the messages, and DirectMessageScreen where we have the list of each private chats or can start new chat based on the list of friends

## Backend

*Decompose the MVP into functional blocks.*
- User login activity : Google-based authentication through Firestore, creation of an account specific for the app, database managing
- Groups : creation and edition of groups and their members, managing the data in the database, managing topics for each group
- Chat : realtime sending and receiving messages and images, separated into private/group conversations, database managing
- Timer : solo and group timer functionalities, database managing
- Todo : private to-do list, managing data to be stored locally on the user's phone
- Video call : use of specialized API for video call, creation of call lobby
- Permissions : managing the state of all system permissions required of the user for good app functionality (camera, microphone, media access, geo-localisation, notifications, ...)
- Map : use of Google Map API to display map with users locations or not, depending on user data

## Data Model

*What data are you collecting / managing?*

- User : profile username, login email, profile picture, added contacts and localisation if activated
- Groups : name, group profile picture, members, topics, timers
- Topic : name, contents (topic items that contain list of strong users, resources and the parent topic)
- User calendar, todos, solo timer
- Message : sender, timestamp, and text or Uri depending of the type of message

*How is it organised?*
1) Firestore database
   - userData : data private to each user
   - groupData : general data, references to members and topics
   - userMemberships : for each user, references to all groups this user is part of
   - topicData and topicItemData : all topic-relevant data, references between them to represent hierarchy of folders and files
   - userContacts : for each user, references to all their contacts
   - contactData : details of the contact relationship between pairs of users
2) Firestore realtime database
   - direct_messages : all messages between a pair of users
   - groups : all messages accessible to members of a group
3) Firestore storage
   - chat_data : organized by chats, contains resources sent through chats such as images
   - group_data : profile pictures of each group
   - user_data : profile picture of each user
4) Local storage
   - todo lists are stored locally on the user phone for offline access

*Where is it stored?*

- Firebase, local storage on the phone (for the todos)

*How is it shared/copied/cached?*

- on Firebase, rules give read and write access permissions where needed

## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*
Developped on AndroidStudio. Manually tested through emulating and automatically with Kotlin tests. Deployed and user-tested through on Android phones through USB debugging.

*Any special infrastructure requirements.*
Android smartphone or emulator

## Test Plan

*How is the application developed, tested and deployed?*
On AndroidStudio, use of test tags and compose screens to test app through each commit

*Any special infrastructure requirements.*

