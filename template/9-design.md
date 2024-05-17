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

*Decompose the MVP into functional blocks.*

## Data Model

*What data are you collecting / managing?*
- User: id, name, email, password
- Post: id, user_id, content, location, created_at
- Comment: id, user_id, content, created_at
- Vote: id, user_id, post_id, value, created_at
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

