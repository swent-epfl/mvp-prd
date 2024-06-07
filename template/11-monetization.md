# Business Model

*Expected operating Costs*

Most of the backend of the application is managed by services offered by [*Google's Firebase*](https://firebase.google.com) and various Google Cloud APIs, which operate under a "Pay as you go" pricing model. During the development period, the free tier was enough to test and develop our features.
However, it will be too restrictive as we scale to accommodate hundreds or thousands of active users.

 In addition to Firebase and Google Cloud's APIs, the app utilizes two other APIs for [*weather predictions*](https://openweathermap.org/api) and [*location auto-completion*](https://radar.com/product/api). These APIs offer free plans suitable for small-scale operations, but will not be sufficient for a rapidly growing application.

Lasta's operating cost for external services will mostly depend on the number of active users, as these APIs charge based on the number of requests.

To implement a reliable notification system for users, a dedicated server is required to manage the requests. Until now, this feature has been self-hosted at a developer's home, but this is not a sustainable solution for the future. Renting a Virtual Private Server (VPS) would be a necessary and cost-effective alternative. Additionally, the same server could be utilized to host a website for the application, enhancing its visibility and accessibility for potential users. This would incur some additional expenses, such as acquiring a domain name, hiring a developer for the website, and covering the VPS rental costs. Fortunately, renting a VPS is relatively inexpensive and does not need significant scaling since notifications are not computation-intensive, and the website will mainly deliver static content.

It will also be needed to allocate a budget for marketing expenses to build a sufficiently large user base. This will include internet advertisements, ads in sports shops, and mountain sports stations, as well as promotional offers to attract new users.

Ongoing costs related the app's code will include maintenance and development. Regular maintenance is essential to ensure that the app remains functional, secure, and up-to-date with the latest features. Additionally, developers are needed to continuously improve the app, add new features, and handle user feedback.

*Revenue Streams*

Our app will generate revenue through three primary channels: targeted advertisements, optional subscription fees, and commissions on guided activities.

The targeted advertisement system will display relevant ads based on the activities users are interested in. This ensures that users receive ads that are beneficial and related to their sporting activities, enhancing their overall experience while providing a significant revenue stream for the app. For example, users looking for bicycle trails will see ads for bicycle tires, maintenance services, cycling gear, and local bike shops on the details page of an activity. Similarly, users interested in hiking events will see ads for hiking shoes, fitness trackers, sports apparel, and local alpine / hike clubs. Additionally, the ads will be geo-targeted to show local services and products, enhancing the relevance and increasing the likelihood of user engagement. Performance-based ads will also be incorporated, relating to the user’s performance metrics, such as nutrition products for users seeking to improve their stamina and training programs for those aiming to enhance their performance. Our goal is not to drown the app under an enormous number of ads on every page. They will be centralized only on the screen describing a particular activity to keep them relevant.

To cater to users who prefer an ad-free experience, we will offer a subscription model. Subscribers will enjoy an uninterrupted experience with no advertisements, and advanced performance tracking analytics with personalized insights. They will also benefit from priority support with faster response times and dedicated assistance for any issues or queries. The subscription plans will include a monthly plan at 4.99.-  and an annual plan at 49.99.-, offering a 17% discount compared to the monthly plan. To encourage users to experience the benefits of the premium subscription, we will offer a 7-day free trial. In-app prompts will enable users to upgrade based on their app usage and engagement.

In addition to targeted advertisements and subscription fees, our app will introduce a new system where certain activities, such as complex hikes, will be linked to professional alpine guide services. Users will have the option to book a guide directly through the app, ensuring they receive expert assistance for their adventurous endeavors. This feature not only enhances user safety and experience but also adds a valuable service to our platform. For each booking made through the app, we will take a 5% commission on the amount paid to the guide, providing an additional revenue stream while supporting the professional guide community.

The integration of targeted advertisements, a subscription model, and the new guide booking system not only diversifies our revenue streams but also aligns with the interests and preferences of our user base. By providing value through relevant ads, premium features, and convenient access to professional services, we aim to enhance user satisfaction and drive sustained growth.