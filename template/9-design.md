# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*

- Dart
- Flutter
- Firebase
- GeoFlutterFirePlus

*If applicable, describe essential screens.*

- Login
- Home
- Profile
- Post Creation
- Post Details
- Challenges
- Map


## Backend

### Application Logic

All application logic will be managed on the backend. The client will communicate the necessary information to retrieve the appropriate data it needs to display, and the backend will respond accordingly. For instance, the client will send its position to the backend, which will then provide the nearby posts.

This separation allows the logic to remain flexible and reduces the need for frequent app updates to fix bugs, as these can be addressed on the backend without modifying the client side. Additionally, this approach keeps the frontend lightweight and focused on optimizing the user experience.



### Application logic
The logic of the app is all managed in the backend and exposed though callable cloud functions to the front end.

### Framework 
Cloud function, node.js


### Database interactions
All database interactions are done on the backend. The db is not accessible from the frontend.

### Common task caching
The backend will cache data that are common to many users. For instance, instead of recomputing the heatmap for each invocation, it will be cached on the backend. This will allow to reduce cost and make the app more responsive

### Listeners for outside interaction
The backend will expose some way to the frontend to listen to some particular actions. That is required to notify the frontend of an outside event. For example, when someone invites the user in a group.


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

