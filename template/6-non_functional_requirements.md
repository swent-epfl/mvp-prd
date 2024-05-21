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

1. Upon the initial launch of the app, users should be able to view and post content with minimal steps to reduce conversion costs and facilitate quick engagement.
2. When accessing the challenges page for the first time, users should receive a brief tour explaining how the challenges work and the logic behind Centauri points.
3. Users should be able to view nearby content on a map immediately, highlighting the location-based features of the application.



## Security, privacy, and data retention policies

*Which are the applicable laws and regulations?*
- Regulation from [Google Map API geolocation](https://developers.google.com/maps/documentation/geolocation/policies?hl=en)

*What are your internal policies?*
- Do not store the location of users online

*Which privacy features do you need from the phone?*

- Privacy
- Moderation
- Authentication

## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*

*Are there known periods of bursty traffic that the MVP must be designed to support?*

- High concentration of users in one place, e.g. concerts
