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


### Database Interactions

All interactions with the database will be managed through the backend. The frontend will not have direct access to the database; instead, it will obtain the necessary data by communicating with the backend API.

This design choice is primarily for consistency and security reasons. By restricting database access to the backend, we ensure that we can control and predict the actions performed on the database at any given time. This level of control would not be possible if the client had direct access to the database, as multiple versions of the application could lead to inconsistent interactions with the database. This approach is further justified when considering potential adversarial behavior from the client, where it is crucial to prevent direct database access to maintain security.


### Operation Caching

Some features that Proxima exposes can require substantial computing resources. For example, computing the post heatmap involves reading and processing all posts within a specific area. To improve responsiveness and reduce operating costs, the backend will cache the results of such operations. 

The time-to-live (TTL) for cached data will be determined based on the importance of data freshness. For instance, the heatmap will be cached on a daily basis, as it is not critical for it to be constantly up to date. This approach ensures efficient use of resources while maintaining acceptable performance levels for users.


### Listenable

Some features of Proxima require the client to react to external events. For example, when a user is invited to join a group, the client needs to be notified of this event in real time. This will be accomplished through listenable Firestore documents.

When a listenable logic is required, the cloud function will create a temporary document in a specific collection that the client will listen to. To maintain consistency with our *Database Interaction* policy, the client will only have read access to these documents, and any writes will be performed through backend API calls. This ensures that the client is promptly notified of relevant events while preserving the integrity and security of the backend.


### Framework

The backend for Proxima will utilize the Firebase suite. Specifically, the database will be managed through Firestore. The backend API will be implemented using Firebase Cloud Functions, written in Node.js as required by the framework. These functions will be callable from the client. This setup provides a scalable and efficient infrastructure for managing the application's backend operations, ensuring reliability and performance.


## Data Model

The data for Proxima are stored on Firebase Firestore in a NoSQL, document-oriented database. Additionally, data are cached locally on the client device to allow for offline usage. The data are organized into collections representing the components necessary for the application. Due to the nature of Proxima, the data are tightly tied to the user; therefore, authentication is required to access any of the data. This ensures that user data is secure and accessible only to authorized users.

We now provide the organization of the main data components managed by Proxima.


**Users :** This collection manages user profile data. The users are stored in a root collection, and for each user, we keep track of the following data:

Centauri points (int), Display name (String), Username (String), Join time (Timestamp).

The distinction between the display name and the username is important. The display name is shown throughout the app and can be the same for multiple users, while the username is unique and used for identifying individual users.

**Posts :** This collection manages the location-based posts. The posts are stored in a root collection where for each post the following data is stored: 

Title (String), Description (String), Publication time (Timestamp), Owner Id (String), Post location (GeoPoint), Post location geohash (String), Number of comments (int), Voting score (int).

The owner id is a string corresponding to the document id of the user who posted the post. The post location geohash is used to perform efficient geo-queries that minimize the number of reads and thus the cost.

**Comments :** This collection manages the comments under a post. It is a sub-collection nested under each post, and each comment contains the following data: 

Content (String), Publication time (Timestamp), Voting score (int), Owner Id (String).

**User comments :** This collection manages the comments left by a particular user. It is a sub-collection nested under each user, and each user comment has the following data: 

Content (String), Parent post Id (String), Publication time (Timestamp).

The document id of a user comment is the same as the document id of the comment under the post. This, combined with the Parent post Id, allows retrieval of the original comment. The redundancy of the fields Content and Publication time is intended to enable fast display of user comments on the profile page, avoiding the need to retrieve each comment's data from under each post. This improves responsiveness and reduces reading costs.

**Voters :** This collection manages the users that have voted on a post. It is a sub-collection under each post, and each document contains the following: 

The user vote type—true for upvote, false for downvote—(bool).

The document id corresponds to the id of the user who cast the vote. This setup allows retrieval of the user's vote state and prevents multiple votes from the same user. The exact same collection structure is also present for comments.



- Users
- Posts
- Comments
- Users comments
- Votes
- Challenges
- Past Challenges


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

