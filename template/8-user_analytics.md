# User Analytics and Acceptance

*Goal: understand how users are using the app.*

*Which are the key metrics?

Different metrics could be used to assess how and how much is our data used by users. We'll discuss some of these metrics.

- **User Engagement**: It is really relevant to try to assess how much engaging is our app for the user. This could be measured by keeping tack the frequency at which the user is using the app or by counting the number of users over time. Is our app used on daily routine or is it mostly used during exam perdiods ? The duration of these sessions could also be a relevant metric, as it can give us more information about the app importance on the habbits of people.

- **Features relevance**: We also would like to assess for what do people use our app. We could measure the number of time a feature is accessed by the user per session and for how long. This would allow us to determine what are the most used feaures (groups.chats,video calls, timers, calendars) ? What are the features that don't seem to interest people or that need improvements ? All these information could be very usefull to define more precisely what we need to focus on as developer. For example it could indicate us what unused features, we should maybe remove or modify. Knowing the strenghts of our app is also relevant for marketing strategies to highlight what is actually really relevant and interesting for the users.

- **Data usage and flow**: On the same field as the previous point, we could measure how much data are create and because of which functionalities. This could be very useful to handle more efficiently the data by knowing which ones are the most used. It is also a good indication of what feature do people tends to use.

- **Conversion rate**: Another aspect we could look at is the conservation rate, meaning how many user are actully using the app after having downloading.

**User satisfaction and ratings**: Listening to the users is always important to keep them happy and impact the success of the app. Ratings are usually avaible on the downloading platforme and could be very usefull to know what aspects of the app satisfy or not the users.

- **User retention**: This metric is particulary important for the survival of the app and expressed the lifetime value (LVT) of a single customer. This metric could be calculated as :  <br>
LVT = Subscription * Gross Margin * (1/chrun) <br>
Where Churn is the percentage of active customers that exit the subscription each month. Usually to have viable app, it is advise to have a LVT greater than 3 times the customer acquisitin cost. This metrix gloabally indicate us how well doest the app surviving knowing the cost of recruiting new users, the cost of them using the app and then leaving. For our app to be viable we should keep track on the number of user we still keep and knowing how much do it cost to keep them using the app. On another side, it could also be relevant to ask the user why do they leave/uninstall the app.

- **Customer acquisition cost (CAC)** : As mentionned before the CA can be an interesting metrix to use as it regroups the interne cost (marketing, enginers, suppport costs) and the impact of customer acquired. The idea is too look at how much does it cost to acquire new customers. To have a viable app, it is advised to keep this CAC lower the 12 months.

*What is the success criteria?*

There aren't juste one success criteria but multiple componenent of it.

As seen in the course, a successful app should most likely be able to:
- acquire customers
- retain customers
- monetize cusomers via a subscription

By fullfilling this criteria we can ensure that the app keep its activate customers, while still beeing interesting and relevant enough to bring new customers. Plus having the monetization ensure a gain for the developers. With all these criteria meet, the app could probably continue to survive. 

However other critera are technically also relevant to look at such as 
- High user engagement
- User satisfaction
- Low crash rates and quick resolution of identified issues
- High usage of the key features

*What is the analysis plan (link to data collection)?*

- **Implement Google Analytics**: This could help us to track user behaviors, such as app frequency usage, session durations, feature usages and others.
- **Implement Firebase Crashlytics**: This would help us understanding the origin of crashes in our app or potential instabilities.

- **Add the app on a downloading plateform**: A primordial step, we still need to complete is to add our app on a downloading plateform. This will also us to keep easily track of the number of downloads and the ratings.

- **Manage the cost and gain**: We should also implement a system to take account of the gain and cost of our app more easily.

*Include relevant A/B testing ideas.*

A/B testing can be describe as [*"methodology for comparing two versions of a webpage or app against each other to determine which one performs better"*](https://www.optimizely.com/optimization-glossary/ab-testing/#:~:text=A%2FB%20testing%20(also%20known,determine%20which%20one%20performs%20better.)

Here are some ideas of A/B testing we could implement for our app:

- **App UI/UX architecture**: We will mostly focus on the screen adjencement, meaning how the screens are linked to each other and the global UI and UX flows. For example we would like to verify how easily a new user can archieve a goal by only looking at the UI (without any previous explanation).
- **UI elements**: 


- Test different UX user flows, displays and formatting to find the most user-friendly one
