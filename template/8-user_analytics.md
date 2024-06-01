# User Analytics and Acceptance

The primary goal of this section is to understand how users are engaging with Proxima.
By tracking specific metrics, we can measure user interaction, satisfaction, and the app's overall effectiveness in promoting real-world exploration through location based content sharing.

Before we fully launch the MVP, it is essential to establish a system to gather pertinent data on user interactions within our application.
This infrastructure will enable us to pinpoint areas for enhancement and address any bugs effectively.

## Key Metrics

- **Number of Active Users** - Measures daily and monthly active users to assess the app’s growth.
- **Number of Posts Created** - Tracks the volume of content generated, reflecting user engagement and the app's usage as a platform for sharing location based experiences.
- **Number of Comments** - Indicates the level of interaction between users, which can help evaluate community engagement.
- Number of **Centauri Points** per User - Provides insight into user involvement in challenges and gamified elements, reflecting the motivational aspects of the app.

## Success Criteria

Success will be determined by:

- Effective **user retention** over time. We are aiming for above 60% returning users.
- High levels of **user engagement** as indicated by posts, comments, and Centauri points (see Key Metrics above).
- Positive **user feedback** and high satisfaction scores. We are aiming to achieve a user rating above 4 stars on mobile application stores after the first two months (Google Play Store and Apple Store).
- Great overall **posts location coverage**. We want to see a dense concentration of posts with no dark zones (100 meters circle without posts) in all of the world's largest cities after 3 months.

## Analysis Plan

To effectively analyze these metrics, the following strategies will be implemented:

- **Data Collection** - Utilize Firebase Analytics to track user interactions within the app. This includes taps, posts read, comments made, and locations visited.
- **Segmentation** - Analyze data based on user demographics (age, location, device type) to identify trends and tailor improvements.
- **Performance Benchmarks** - Set specific targets for each metric and compare actual performance against these benchmarks. Include these repetitive performance benchmarks into our regular development pipeline to effectively pinpoint changes that could negatively affect performances.

**Note**: we also need to make sure that our application stays compliant with data protection rules that apply, like GDPR.

## A/B Testing Ideas

- **Post Visibility Proximity Requirements** - Test how varying the radius within which posts can be accessed (e.g., 50 meters vs. 100 meters) affects user engagement and content discovery.
- **Challenges Frequency** - Compare user engagement between different groups exposed to daily versus weekly challenges to determine the optimal frequency for maximizing participation.
- **Notification Styles** - Experiment with different notification styles (e.g., push notifications vs. in-app alerts) when users are near a post location to see which method is more effective in encouraging app interaction.
