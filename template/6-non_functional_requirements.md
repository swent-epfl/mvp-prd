# Non-Functional Requirements

## Security, privacy, and data retention policies

Our app collects the minimal amount of data on our users needed for it to be fully functional. This way, we avoid the collection of "sensitive" data that could be subject to special regulations in certain countries. Most of the data in our app is accessible publicly; the only thing that needs to be protected is the user's email and password. Supabase seems reliable enough to avoid leaking such information, and in any case, the password is stored hashed with a salt. We can easily inform all the users if a data breach happens because we have their email.

From a privacy standpoint, the most sensitive information we have is the participation of the users in the events and the user profile. A user can only access their own user profile in the app, and he cannot see a list of subscribed users to an event. Our app minimizes the data it collects, and we don't sell or give direct access to this data. The analytics aggregations will have to be done on the events, as the users never send their location to the server. We don't ask for other permission than location, and we use intends that return a single item to get data from other apps (i.e. set the profile picture).

We can automatically delete the user accounts after some time of inactivity, and a user can email the support if he wants to have a copy of all the data we have on him. Furthermore, we plan to add a delete account button in the app.

## Adoptions, Scalability and Availability

Obviously, our first focus is the EPFL campus. Then we can promote the app to the whole population, as there is a very low entry barrier. We don't limit the app's usage, so anybody in the world could just use it, but since the app is only available in French or English, it limits its worldwide usage. However, thanks to our modular architecture, it's quite simple to translate the app into any language we want.

We will probably have high traffic during non-working hours. We should make sure with a stress test on the database that it doesn't impact too badly the performance of the app. Since we have caching capabilities in the app, we are able to reduce the load spikes. If some events are very big (i.e. Balelec) we can also plan to scale up our backend for the duration of the event to avoid any issues.
