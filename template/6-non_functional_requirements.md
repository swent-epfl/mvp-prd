# Non-Functional Requirements

## Security, privacy, and data retention policies

### Location Policy

The primary privacy consideration for Proxima concerns the management of user location data. Recognizing the sensitivity of this information, we have established a strict policy regarding its usage.

Proxima will not store any user location data on the backend. The only location data stored in the backend are the locations of posts. While these locations are initially linked to a user at the time of posting, they quickly become non-relevant as users move to different places. This approach ensures that users' location privacy is maintained while still enabling the core functionalities of the application.







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
