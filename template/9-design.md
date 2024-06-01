# Design and Implementation

## Frontend

**Implementation Framework** 

The application has been developed with Flutter, which is based on the Dart programming language. Flutter can natively compile on Android and iOS from the same code base, which allows us to launch the application to more users easily. 
We use the Model View ViewModel (MVVM) architecture to ensure structured management and interactions between the UI and the application logic. We use the Riverpod package, which simplifies the application of the Observer pattern, reducing necessary UI refreshes.

**Firebase communication** 

We use Firebase Authentication to handle user authentication. The Firebase Core, Firebase Auth and Google Sign-In Flutter packages control the user authentication flow through a Google Sign-In intent on the login screen. Additionally, we plan to add additional OAuth providers, like Apple, to allow most of the users to choose one of the available options and easily authenticate.

Storing and fetching the user interactions in the application are handled using the Firebase Core and Cloud Firestone Flutter packages.

**User location processing** 

In order to retrieve the user's surrounding posts and display the map with the current user location, we use the GeoLocator Flutter package. This package simplifies access to the user's current location on every platform. Additionally, we use GeoFlutterFire Plus, which simplifies the storage and fetching of Firebase documents based on their location. 

### Essential screens

**Login page**: First screen that appears when the user is not authenticated. It allows the user to authenticate and access the application.

**Feed**: The feed is the central screen of the application. Shown when starting the application as an authenticated user, it displays the posts that are at less than one hundred meters away from the user. This screen allows him to sort the feed by hottest, top, latest, or even nearest posts. The feed displays, for every post, its title, the first seven lines of its description, its owner, the number of comments, the date of the post along with its upvote score. It also allows the user to upvote or downvote any posts directly from the feed screen.

**Profile page**: The profile screens displays all the information associated to the user, such as his username, display name, number of centauri points, badges, number of followers along with his number of followed users. Moreover, it displays the title and description of all of his posts along with all of his comments. The user is able to delete any post or comment that he created, from anywhere, directly from the profile page.

**Post creation page**: Screen allowing the user to write a new post by setting its title and description. Before posting, the user is able to choose a group of nearby users with whom he wants to post. He can also decide whether to send a notification to his followers.

**Post page**: Page displaying all the information associated to a particular post. This screen is displaying the title, complete description, owner, date, distance, upvote score, and all the comments associated with the post. The user is able to sort the comments by top or latest at his convenience, and he can follow up on any comment, creating a thread of comments to discuss and interact about the original post.

**Challenge page**: The challenge page displays all the current available challenges that the user can complete alone or as a group. A challenge is described by the post title and distance, along with the time left to complete it. By clicking on a challenge, we are redirected to the map, allowing the user to localize it more easily.

**Group page**: The group page allow the user to create or join a group with nearby users. It allow them post and complete challenges together.

**Map page**: The map page enables the user to switch between multiple maps that are of two main types. 
First, we have the maps, allowing the user to see the precise location of his posts and current challenges. Moreover, he is also able to display all the posts that are less than one hundred meter away.
Additionally, the user is also able to access the heatmap, enabling him to see places around the world that are currently attracting a lot of interaction.

## Backend

### Application Logic

All application logic will be managed on the backend. The client will communicate the necessary information to retrieve the appropriate data it needs to display, and the backend will respond accordingly. For instance, the client will send its position to the backend, which will then provide the nearby posts.

This separation allows the logic to remain flexible and reduces the need for frequent app updates to fix bugs, as these can be addressed on the backend without modifying the client side. Additionally, this approach keeps the frontend lightweight and focused on optimizing the user experience.


### Database Interactions

All interactions with the database will be managed through the backend. The frontend will not have direct access to the database; instead, it will obtain the necessary data by communicating with the backend API.

This design choice is primarily for consistency and security reasons. By restricting database access to the backend, we ensure that we can control and predict the actions performed on the database at any given time. This level of control would not be possible if the client had direct access to the database, as multiple versions of the application could lead to inconsistent interactions with the database. This approach is further justified when considering potential adversarial behavior from the client, where it is crucial to prevent direct database access to maintain security.


### Listenable

Some features of Proxima require the client to react to external events. For example, when a user is invited to join a group, the client needs to be notified of this event in real time. This will be accomplished through listenable Firestore documents.

When a listenable logic is required, the cloud function will create a temporary document in a specific collection that the client will listen to. To maintain consistency with our *Database Interaction* policy, the client will only have read access to these documents, and any writes will be performed through backend API calls. This ensures that the client is promptly notified of relevant events while preserving the integrity and security of the backend.


### Framework

The backend for Proxima will utilize the Firebase suite. Specifically, the database will be managed through Firestore and the media storage will be held on Firebase Cloud Storage. The backend API will be implemented using Firebase Cloud Functions, written in Node.js as required by the framework. These functions will be callable from the client. This setup provides a scalable and efficient infrastructure for managing the application's backend operations, ensuring reliability and performance.


## Data Model

The data for Proxima are stored on Firebase Firestore in a NoSQL, document-oriented database. Additionally, data are cached locally on the client device to allow for offline usage. The data are organized into collections representing the components necessary for the application. Due to the nature of Proxima, the data are tightly tied to the user; therefore, authentication is required to access any of the data. This ensures that user data is secure and accessible only to authorized users.

We now provide the organization of the main data components managed by Proxima.


**Users :** This collection manages user profile data. The users are stored in a root collection, and for each user, we keep track of the following data:

Centauri points (int), Display name (String), Username (String), Join time (Timestamp).

The distinction between the display name and the username is important. The display name is shown throughout the app and can be the same for multiple users, while the username is unique and used for identifying individual users.

**Posts :** This collection manages the location-based posts. The posts are stored in a root collection where for each post the following data is stored: 

Title (String), Description (String), Publication time (Timestamp), Owner Id (String), Post location (GeoPoint), Post location geohash (String), Number of comments (int), Voting score (int), Media Link (URL).

The owner id is a string corresponding to the document id of the user who posted the post. The post location geohash is used to perform efficient geo-queries that minimize the number of reads and thus the cost.
The media link is a URL referencing the media displayed in the post, stored in Firebase Storage. It can be null if the post is only textual.

**Comments :** This collection manages the comments under a post. It is a sub-collection nested under each post, and each comment contains the following data: 

Content (String), Publication time (Timestamp), Voting score (int), Owner Id (String).

**User comments :** This collection manages the comments left by a particular user. It is a sub-collection nested under each user, and each user comment has the following data: 

Content (String), Parent post Id (String), Publication time (Timestamp).

The document id of a user comment is the same as the document id of the comment under the post. This, combined with the Parent post Id, allows retrieval of the original comment. The redundancy of the fields Content and Publication time is intended to enable fast display of user comments on the profile page, avoiding the need to retrieve each comment's data from under each post. This improves responsiveness and reduces reading costs.

**Voters :** This collection manages the users that have voted on a post. It is a sub-collection under each post, and each document contains the following: 

The user vote type—true for upvote, false for downvote—(bool).

The document id corresponds to the id of the user who cast the vote. This setup allows retrieval of the user's vote state and prevents multiple votes from the same user. The exact same collection structure is also present for comments.

**Challenges :** This collection manages the active challenges for the user. It is a sub-collection under each user, and each challenge is composed of: 

Expiring time (Timestamp), Must this challenge be completed in a group (bool), Has the challenge been completed (bool), Challenge completion points (int).

The document id of the challenge corresponds to the document id of the post that must be visited to complete the challenge.

**Past challenges :** This collection manages the past challenges proposed to the user (whether completed or missed). It is a sub-collection under each user, and each past challenge has the same structure as an active challenge, with the fields:

Expiring time (Timestamp), Must this challenge be completed in a group (bool), Has the challenge been completed (bool), Challenge completion points (int).

The presence of this collection is justified to ensure that the user is not presented with the same challenge more than once.

**Groups :** This collection manages the various groups formed by users. It is a root collection, and each group document contains the following data: 

Centauri points accumulated by the group (int), Creation time (Timestamp).

**Group members :** This collection manages the members of a group. It is a sub-collection nested under each group document, and each group member stores the following data: 

Joining time (Timestamp).

The document id corresponds to the user id of the member, allowing for retrieval of their data.

## Security Considerations

**Firestore rules :**
To enforce the access policy for our database, we will implement Firestore rules. By default, only the backend will have read/write access to the database. As described in the *Listenable* section above, only certain temporary documents will have read access for the client, allowing it to listen and be notified of events. These documents are temporary and will not contain any sensitive data. For all other documents, the client will not have read or write access. This ensures that sensitive data remains secure and that the backend retains control over database operations.

**App Check:**
To ensure that only our application can use our backend API, we will utilize Firebase App Check. This will prevent unauthorized clients from accessing our backend resources. Specifically, it ensures that API calls originate from our authentic application, thereby protecting our backend from misuse.


## Infrastructure and Deployment

We will maintain two Firestore databases: one for development and one for production. The code will first be developed and tested on the development database. Once validated, it will be deployed to the production database. This approach ensures that user data is not at risk during development and maintains a consistent production database.

The deployment of the backend API is automatically managed by Firebase, which will allocate resources based on demand. This ensures a scalable backend that can handle varying loads efficiently.

## Test Plan

**Continuous Integration :**
The backend will be developed using a continuous integration approach with a minimum code coverage threshold of 90%. This ensures that the implemented code has been thoroughly tested.

**Cost Tests :**
For the implementation of new API functions, read/write cost tests will be performed under various conditions to ensure that the functions scale well in different environments. This will allow for better cost estimations and help avoid potential unexpected bills.

**Crashlytics :**
We will utilize Firebase Crashlytics to monitor potential crashes or errors in the application. This will help us quickly diagnose and address potential bugs, ensuring a more stable and reliable user experience.
