# Functional Requirements
Here are the functional requirements that we believe are necessary for the MVP to be successful.


1. **User Authentication**: Users must be able to authenticate into their account to user the app. For this, we will use pre-existing infrastructure, such as Google Sign-in or other common OAuth providers.

2. **Post Creation**: Users must be able to create posts containing text. These posts will have embedded location data.

3. **Location-Based Feed**: Users must be able to see in a feed all of the posts that were made inside of a 100m radius around their current position. This feed will have different sorting options. One option will show the most trending post first, wich will use a combination of recency and number of upvotes. Another will simply show the most upvoted posts first. Another wil show the closest posts first. A last option will show the newest posts first. This allows the users to more easily find posts that are interesting to them.

4. **Commenting System**: Users must be able to leave comments on posts. 

5. **Offline Mode**: Users must be able to see as much data as possible even when they are not online. Their user profile, own posts and comments and current challenges should be cached locally and always be accessible.

6. **Voting System**: Users should be able to upvote or downvote posts and comments.

7. **Posts and comments management**: Users should always be able see all of their own posts and comments, and delete them if they want to. Deleting a post automatically deletes all the comments and any information related to it.

8. **Centauri Points**: Users gain Centauri points by completing challenges. These provide cosmetic improvements on their profile. Users can see how much points they have in their profile as well as in a leaderboard, where they can compare themselves to everyone.

9. **Challenges**: Users get 3 challenges everyday. These are randomly picked from posts in their area. To complete these challenges, they have to travel to the post and open it.

10. **Map Integration**: Users should be able to see all the nearby posts, all of their own posts and all their challenges on a map. It should be simple to navigate back and forth from the map to the other pages.
