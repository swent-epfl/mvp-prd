# Non-Functional Requirements

## Security, privacy, and data retention policies

### Security

User authentication is managed by the third-party Google Authentication system. Consequently, credential data does not pass through our backend, ensuring that none of this highly sensitive information (such as passwords and tokens) is retained or exposed to risk on our side. This approach leverages Google's robust security infrastructure, providing a secure and reliable authentication process for our users.

### Data Retention Policy

Proxima collects only the necessary data required for the proper functioning of the application. This includes the user's representation in the application (such as username, display name, and join date) as well as the content published by the user.

An important consideration is the deletion of accounts as required by law. Our policy in this scenario is to delete all content linked to the user account. Specifically, this includes the user's personal data as well as any content they have published, such as posts and comments. This ensures compliance with legal requirements and respects user privacy.

### Location Policy

The primary privacy consideration for Proxima concerns the management of user location data. Recognizing the sensitivity of this information, we have established a strict policy regarding its usage.

Proxima will not store any user location data on the backend. The only location data stored in the backend are the locations of posts. While these locations are initially linked to a user at the time of posting, they quickly become non-relevant as users move to different places. This approach ensures that users' location privacy is maintained while still enabling the core functionalities of the application.

### Moderation

Moderation is a crucial aspect of any public social media platform, and our application is no exception. Our policy regarding moderation will be based on a reporting system complemented by AI analysis and human judgment.

If content is reported by multiple users, it will first be evaluated by an AI system to determine its appropriateness. If the AI model cannot fully decide on the nature of the content, human moderators will be engaged to make the final decision on whether to remove the content or not. This combined approach ensures that moderation is efficient, accurate, and fair, maintaining a safe and respectful environment for all users.


## Adoptions, Scalability and Availability

### Adoption

1. **Quick Engagement**: Upon the initial launch of the app, users should be able to view and post content with minimal steps to reduce conversion costs and facilitate quick engagement.
2. **Challenge Tour**: When accessing the challenges page for the first time, users should receive a brief tour explaining how the challenges work and the logic behind Centauri points.
3. **Location Awareness**: Users should be able to view nearby content on a map immediately, highlighting the location-based features of the application.

### Scalability

1. **High User Capacity**: The application must scale well to accommodate a high number of users and a large volume of content, ensuring seamless performance as the user base grows.
2. **Content Density Performance**: It must also maintain good performance and responsiveness in high content density areas, such as big towns, monuments, and concerts, to provide a smooth user experience in these environments.
3. **Feature Flexibility**: The backend should be designed to easily support the addition of new features over time, ensuring the application can evolve and adapt to meet changing user needs and technological advancements.

### Availability

1. **High Uptime**: Uptime is crucial for any social media platform. Therefore, our application should maintain an uptime above 99.9% to ensure that users have reliable and continuous access to the service.
2. **GPS Signal Handling**: In cases of poor or low precision GPS signal, the application should remain usable. It should include a manual refresh option to prevent content from appearing or disappearing unexpectedly, providing a more stable user experience.
3. **Update Pipeline**: The application should have a predefined update pipeline that ensures backward compatibility. This approach will guarantee that all users can access the application seamlessly before and after updates, minimizing disruptions.
4. **Performance and Crash Monitoring**: Anonymous performance and crash metrics should be continuously monitored. This data will help detect and resolve potential issues more quickly, ensuring the application remains stable and performs well for all users.
