# History

The proof of concept (PoC) built at the end of sprint 10 contains many of the most important features: user authentication, posts (addition and deletion), comments (addition and deletion), votes, feed, profile picture, challenges, ranking and map.

Doing so, we learnt multiple important things concerning the technologies we used:
- Using **Google Firebase** is a great idea, since it allows to get rid of any trouble concerning the handling of a database, and user authentication. 
- **Flutter** is a great framework that really improved our efficiency. Its hot-reload feature notably allowed to quickly test UI changes. Moreover, its testing technology requiring no emulator rendered our CI very fast, even with more than 300 tests. The fact that it is cross-platform also makes it an advantage over Kotlin and Jetpack Compose.
- **Penpot** is not a good enough substitute for Figma. It caused many issues, such as crashes, slow downs and non fully backward compatbile updates. For the MVP, this should be replaced by Figma.

We already have many of the features we want in the PoC for the MVP. The two features that lack are groups and media support, which will be described in the section "The MVP".

Moreover, the backend needs substantial changes, for security reasons. The logic should not be done on the phone of the user—which could be malicious—but using cloud functions. That way, we only send the data the user needs, hence putting our trust on the server, instead of on their device to filter data before displaying it.
