# Non-Functional Requirements

## Security, Privacy, and Data Retention Policies
### Security and Trust

Users on our app will authenticate with Google on Android. Therefore firebase manages authentication and our database contains only minimal information such as e-mail, first and last name. This approach ensures user data security while maintaining the functionality of our services.

### Privacy Considerations

Our app will handle sensitive information, including user positions at given times and private information shared over chat. To maintain user privacy and comply with data protection standards, we must adopt stringent policies to avoid saving, extracting, or inferring any additional personally identifiable information beyond what is necessary. This ensures user privacy is upheld and that sensitive data is handled with the utmost care.

### Data Retention Policies

### Map

Permission to track a user's position is requested the first time the map is opened and can be disabled at any time.

During an active flight, the positions of each crew member and the pilot (used for the flight track) are retrieved and stored. We need to ensure that user positions are only retrieved during the flight in question and that this data is only stored for the duration of the flight. The pilot's position, i.e. the position of the balloon during the flight, must be stored for a longer period to allow access to the flight trace once the flight has ended. Once the flight is over, all positional data, with the exception of the pilot's position, must be deleted immediately.

### Chat

Users associated with the same flight have access to a chat where they can potentially share sensitive information. To protect user privacy and maintain relevance, we will implement a policy to delete chats older than 7 days, as they are only pertinent during the flight.


## Adoptions, Scalability and Availability

### Adoption

* Users should have the option to selectively enable push notifications for specific functionalities within the app, such as when an assigned flight starts.
* The application's user interface must include easily accessible settings for customizing notification preferences, allowing users, such as pilots, to disable notifications to focus on flight safety and avoid distractions from non-essential team messages. 
* The application should primarily function as a practical tool and must not distract or jeopardize the safety of those on board the balloon.
* Adoption metrics must focus on user engagement quality rather than frequency, emphasizing the app's value-add to the users' experience.

### Scalability

The application must be designed to handle varying user loads effectively, particularly during peak periods such as peak tourist seasons, large group bookings, or popular local events. This ensures that balloon company operations remain smooth and efficient even under high demand.

The application integrates automated deployment for new clients, including Firebase provisioning, database setup (rules, index creation...), and monitoring service configuration.


### Availability

Since the application is based on Firebase, it will achieve a high uptime of 99.9%, ensuring the company remains operational and is not hindered by an unavailable tool.

