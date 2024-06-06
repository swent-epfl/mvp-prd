# Non-Functional Requirements

## Security, privacy, and data retention policies


Given the global reach of our app, we must adhere to local laws concerning data security and privacy. Beginning with Europe, compliance with GDPR is essential. Users in Europe must have access to and the ability to delete their data. We will explicitly request camera access (for QR code scanning, photo-taking) and user location (to suggest local events). Additionally, users must consent to their data being stored by Google.

As our app is designed to foster connections and facilitate new friendships, users have personal profiles within the app to share information with their friends, allowing them to be identified within the community. Users have full control over their privacy settings, determining which information is visible to other users. The user needs also to be able to delete any sent message or event in the history of attended events.
The backend for these private informations should be done in such a way that we cannot extract or infer any personally identifiable informations.

The app keeps personnal data about users such as birthdates used to filter the events the user have accessed to, as well with phone numbers used for country and user verification. Data about chats and attended events needs to be kept for as long as the user is using the app to provide the user an history of the user's activity. 



## Adoptions, Scalability and Availability

Users should be able to add their friends throught QR code scanning at any time they meet with them.
Users can use the app without providing payment information to be able to attend free events.
The UX must be easy and intuitive for the user to choose it's privacy settings.
Metrics should measure the individual usages of the app (chats, browsing events, hosting events) to determine any weak point and make advertising or imporvement accordingly.

The app can scale globaly across the world but it is only useful within a certain locality. People won't travel 100km for just a weekend event.
We should consider having a backend of our own to better address the locality of the app and optimize delay, and information exchange. A user in Switzerland doesn't care about the small events in Japan. As well as the app aim to build new friendship, the local behaviour is even more important.

We can except summer and holiday to be more busy. This is very dependant of the locality of the app. A certain region can have a peaks of traffic when it is holiday or days with good weather forecast.
Weekly peaks will be on the weekend. People will massively use the app to geolocate themselves to attend their events. 
The system must be reactive for anticipated high traffic during popular cultural and sporting event periods.

As the app contains many features with concurrent interaction it must be designed to support all these incoming changes at the same time without big delays and errors.
The app must be able to handle the cases were internet is unstable wihout data loss of data corruption



