# Design and Implementation

## Frontend

**Implementation Framework** The application has been developed with Flutter, which is based on the Dart programming language. Flutter can natively compile on Android and iOS from the same code base, which allows us to launch the application to more users easily. 
We use the Model View ViewModel (MVVM) architecture to ensure structured management and interactions between the UI and the application logic. We use the Riverpod plugin, which simplifies the application of the Observer pattern, reducing necessary UI refreshes.

**Firebase communication** We use Firebase Authentication to handle user authentication. The Firebase Core, Firebase Auth and Google Sign-In Flutter plugins control the user authentication flow through a Google Sign-In intent on the Login screen.

Storing and fetching the user interactions in the application are handled using the Firebase Core and Cloud Firestone Flutter plugins.

## Backend

*Decompose the MVP into functional blocks.*

## Data Model

*What data are you collecting / managing?*

- User: id, name, email, password, joined date
  - UserComments: comment_id, content, post_id
- Post: id, user_id, content, location, created_at
  - Vote : id, user_id, vote_type
  - Comment: id, user_id, content, created_at
    - Vote : id, user_id, vote_type
- Challenge: id, title, description, start_date, end_date, reward

*How is it organised?*
Comments are in a subcollection of posts, votes are in a subcollection of posts, challenges are a subcollection of users.

*Where is it stored?*

- Google Firebase

*How is it shared/copied/cached?*

## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

