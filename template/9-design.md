# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*
- Key Libraries/Languages: Kotlin, Hilt, Material3, Jetpack Compose, Firebase, Android Camera Image Analysis.

*If applicable, describe essential screens.*
- Home screen, Event Details, User Profile, Messaging, Event Creation.
## Backend

*Decompose the MVP into functional blocks.*
- User Management: Handles registrations, profiles, and settings.
- Event Management: Creates and updates events, manages tickets.
- Messaging System: Manages communication between users.

## Data Model

*What data are you collecting / managing?*
- User data: Names, email addresses, user's friends, user bios, user profile pictures.
- Event data: Event locations, categories, start and end date, ticket price, tickets purchased, participant lists, organiser lists.

*How is it organised?*
- Using firebase database for user and event data.
- Using firebase storage for QR Code Images, Profile Photos and Event Photos.

*Where is it stored?*
- Firebase Database
- Firestore Storage

*How is it shared/copied/cached?*
- Utilize Firestore’s built-in caching on the client side to reduce latency and enhance the user experience by serving data from cache.

## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*
- Deploy on cloud platforms like AWS or Azure to ensure high availability and scalability.

*Any special infrastructure requirements.*
- Use Firebase Authentication to secure APIs. Ensure that data requests are authenticated and users can only access data relevant to them.
- Use HTTPS for all communications between the app and servers.


## Test Plan

*How is the application developed, tested and deployed?*
- Utilize CI/CD pipelines for efficient testing and deployment.
- UI tests to ensure UI components run smoothly.
- ViewModel tests to ensure that appropriate states are prepared for UI.
- Backend testing using Mocks to ensure backend services like firebase work as expected.
- Integration testing to ensure the app runs smoothly.

*Any special infrastructure requirements.*
- Utilizing hilt for dependency injection in testing.