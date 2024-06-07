# User Analytics and Acceptance

To scale our LASTA app, we need different metrics to measure the success of the app. We need to understand how users are interacting with the app, what features they are using, and how we can improve the user experience. To do so, we need a system to collect data. The key metrics are the following, and we will use them to always find a better adequation about the Product-Market Fit.

### What are the key metrics?
- User engagement: How often do users interact with the app, and how long do they spend on the app? 
- Feature use: Number of access to our key features (Clicked on a new activity on the Discover, how many times a favorite hiking trail was tracked after). We can also compute a correlation between texting a friend on the app, and doing an activity together.
- Conversion rate: From app download to a active usage (more than 2 times per month).
- User retention: The rate of returning users over time. 
- Drop-off rate: What UI transition have high drop-off, and if a user rates a lot of trails badly, do they stop using the app?


### What is the success criteria?
- High user engagement and retention rate, with more than 75% of users returning to the app after 1 month. 
- Low crash rate, with less than 1% of users experiencing a crash and a fast resolution of those crashes.
- High conversion rate, with more than 50% of users using the app more than 2 times per month.

### What is the analysis plan (link to data collection)?
- We will use Google Analytics to collect data on user engagement, feature use, and conversion rate.
- Secondly, we will implement Firebase Crashlytics to monitor the crash rate and resolve any issues quickly for enhanced stability.
- The data will be analyzed anonymously to protect user privacy.

### Relevant A/B testing ideas.
- A/B test the UI to see if a different color scheme increases user engagement.
- A/B test the Discover page to see if a different layout increases feature use (shorter cards displayed, maybe two columns instead of one).
- A/B test different navigation flows to find the most user-friendly option.