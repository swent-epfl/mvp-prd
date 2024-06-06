# History

The proof of concept (PoC) built at the end of sprint 10 already contains many of the most important features: user authentication, posts (addition and deletion), comments (addition and deletion), votes, feed, profile picture, challenges, ranking and map.

Doing so, we learnt multiple important things concerning the technologies we used:

- Using **Google Firebase** is a great idea, since it allows to get rid of any trouble concerning the handling of a database, and user authentication. 
- **Flutter** is a great framework that really improved our efficiency. Its hot-reload feature notably allowed to quickly test UI changes. Moreover, its testing framework not requiring an emulator made our CI run very efficiently, even with more than 300 tests. The fact that it is cross-platform also makes it an advantage over Kotlin and Jetpack Compose.
- **Penpot** is not a good enough substitute for Figma. We chose it since it is open-source, but it had many issues, such as crashes, slow downs and non fully backward compatible updates. For the MVP, this should be replaced by Figma.

We already have many of the features we want in the PoC for the MVP. The two main features that lack are groups and media support, which will be described in the section "The MVP".

Moreover, substantial changes to the backend are necessary, for security reasons. Instead of relying on client-side logic - which can be compromised on user devices - we should use cloud functions. This approach ensures that only the necessary data is sent to the user's devices, removing the need to trust the client side to correctly filter the data before displaying it.
