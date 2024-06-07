# Design and Implementation

## Frontend

The application uses the following key components:
- Kotlin : language used for coding the application
- Google Maps : Google Map API is used to geo-localize users on the app
- Jetpack Compose : UI framework used for application design
- Stream.io : library and API used for the video call feature
- SonarCloud : used to analyse test coverage, code complexity and other code-specific metrics
- Firebase : console used for Google authentication and database storage

The application's main screens can be separated into social, online features and solo features can be accessed even offline.
In the online features, we will notably a home screen from which all the groups that the user is subscribed to can be accessed. Within each group, the user can access a general chat with the other group members, a list of topics created by the group, a group video call feature, a shared timer to study together and a shared calendar. Within each topic, the users can customize folder and files that constitute a pool of shared resources and an easy way to help each other.
There are also other online features: direct messages with any other friend to privately chat, and a map to view the locations of the user's friends.
For offline features, the user has access to a Todo list that they can use to keep track of their tasks, customizable flashcards, a private timer and a calendar.
All the user's data is locked behind a Google-authentication login, and they can at anytime modify, switch or delete their account.

## Backend

The application is composed of the following functional blocks:
- User login activity : users are managed through a Google-based authentication, and additional account information is stored such as a username, profile picture, ...
- Groups : users can create, modify and delete groups. Each group member has the possibility to modidy their groups' settings. New members can be directly added to the group, or an invite link can be generated that allows anyone to join the group.
- Chat : be it groupchats or direct messages, users can send - in realtime - messages, images, pdf files, links, ... Text messages can also be modified and deleted.
- Video call : there is a video call feature in each group, that all members can join to share and study together, complete with a call lobby. The camera and microphone can be independently turned on and off at any time.
- Topics : within each group, members can create topics. In each topic, they can customize their own hierarchies of files, divided in "Practice" and "Theory" tabs. For each file, the users can share resources such as images, pdf files and links. Each file also has a list of "strong users" that the group members can refer to, to ask for help.
- Timer : there is a solo timer feature that can be used offline, and a shared timer specific to each group that members can use to plan out study sessions together.
- Calendar : as the timer, there are both offline and online calendar features to be used privately or shared within a group.
- Map : using Google Map API, the application can display the locations of a user's friends. Each user can decide whether or not they want their location to be seen by others.
- Todo : a private, offline-accessible Todo list that allows the user to create and edit tasks, mark them as "todo", "started" or "done".
- Flashcards : the user can, privately and offline, create or import their own decks of flashcards to have all of their study materials at the same place.
- Permissions : for every task that requires the system's functionalities, the user is requested the relevant permissions. These include geo-localisation for the map, microphone and camera access for video calls, media access for profile pictures.

## Data Model

Different types of data are stored either on the Firestore Cloud Database and Realtime Database (for shared, online features) or directly on the user's phone (for private data that can be accessed offline).

Below is a list of all the data that the app stores:
- User : profile username, login email, profile picture, added contacts and localisation if activated
- Groups : name, group profile picture, members, topics, shared timers and calendars
- Topics : name, contents (topic items that contain list of strong users, resources and the parent topic)
- Messages : sender, timestamp, and content depending on the message type (text, image Uri, link, ...)
- User's private calendar, Todo list, timer and flashcards

All the aforementioned data is organized as described below:
1) Firestore Cloud Database
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
   - todo lists and flashcards are stored locally on the user phone for offline access

## Security Considerations

All the data stored on Firestore is protected by sets of rules to prevent unwanted read/write accesses.
In general, other users data can only be read but not changed, and groups-related data can be accessed by all group members.

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*
The application is developped on AndroidStudio and written using the Jetpack Compose framework in Kotlin. The app is also deployed and user-tested on Android phones through USB debugging, or via an emulator if no physical Android phone is available.

## Test Plan

The application is tested both manually through emulation, and automatically in Android tests through the use of compose screens and test tags.