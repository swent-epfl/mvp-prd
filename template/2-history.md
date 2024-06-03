# History

The proof of concept (PoC) built at the end of sprint 10 contains many of the most important features: user authentication, posts (addition and deletion), comments (addition and deletion), votes, feed, profile picture, challenges, ranking and map.

We already have many of the features we want in the PoC for the MVP. The two features that lack are groups and media support, which will be described in the section "The MVP".

Moreover, the whole backend needs to be changed, for security reasons. The logic should not be done on the phone of the user—which could be malicious—but using cloud functions. That way, we only send the data the user needs, hence putting our trust on the server and not on their device to filter data before reading it.
