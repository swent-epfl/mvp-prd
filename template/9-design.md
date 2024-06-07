# Design and Implementation

## Frontend

#### Implementation Framework
The app will be developed in Kotlin, optimized for Android, and will utilize the Model-View-ViewModel (MVVM) architecture. This approach will ensure a structured and efficient management of the app's UI and business logic.

#### Dynamic UI Rendering Strategy
The data layer will fetch machine-readable UI descriptions that provide detailed information about the required components for each feature. The ViewModel will interpret these UI descriptions and manage the state and logic for each feature, ensuring high responsiveness to any data changes.

Additionally, loading indicators or messages will be shown when data is being synced. Robust error handling will inform users of any issues with data retrieval or sync, and options to retry failed operations will be provided.

#### Component Management and Modular Approach
The UI layer will be composed of various components managed by the ViewModel. Each feature, such as Authentication, Map, Discover, Profile, Preferences, Social, and Favorites, will have corresponding ViewModels and components to handle specific tasks. This modular approach will ensure a clean separation of concerns, with the UI layer focusing solely on rendering and user interactions.

For example, the DiscoveryViewModel and WeatherViewModel will work together to fetch the user's position, nearby activities, and weather reports. The ProfileViewModel will manage user activities, preferences, and other profile-related data.

#### Security
The app will follow secure key management practices, using trusted hardware or secure storage solutions like the Android Keystore to protect encryption keys. Rate limiting and throttling will be implemented to prevent abuse and mitigate DoS attacks.

Additionally, the app will encrypt user information. Sensitive data storage will be minimized, and proper data retention policies will be enforced.

Finally, the app will regularly update and patch security vulnerabilities, with a secure update mechanism to prevent tampering.

#### Caching Strategies
To optimize data retrieval and minimize unnecessary network requests, the frontend will implement local storage mechanisms to cache user preferences and activity data.

Additionally, the frontend will incorporate logic to check the cache first before making network requests, reducing redundant fetches and minimizing network usage. Appropriate expiration policies will be set for cached data to ensure it is refreshed periodically.

#### Supporting Offline Mode
The app will provide users with options to download specific activities for offline access. This will be achieved by saving the required data locally on the device. A UI component, such as a button or a toggle, will allow users to choose which data they want to download for offline use.

Furthermore, to ensure smooth functionality in offline mode, the app will retrieve data from the local cache. Background synchronization logic will be implemented to update and sync data with the server when the user comes back online.

Finally, the UI will adjust to indicate when the app is in offline mode, such as displaying an "Offline" banner or disabling certain features that require an active internet connection.

## Authentication 

### Google Authentication
The application user authentication is handled through both Google's Authentication service and traditional email and password login. This dual integration is essential for our MVP as it provides a secure and seamless login experience for users, catering to different user preferences. 

By utilizing Google's Authentication, we can quickly and reliably obtain crucial user information, including email, name, and profile picture. This approach not only simplifies the registration and login process but also enhances the user experience by enabling personalized features and interactions within the app.

The email and password option ensures that users who prefer traditional login methods are also accommodated.  

Furthermore, care must be taken to avoid any potential leak of user's private information, even in the event of a data breach. Robust security measures will be implemented to protect all user data, regardless of the authentication method used.

#### Frontend (Android Application)

- Google authentication: users will be able to log in with a single tap using their Google account. The frontend will display Google's standard login button, which, when clicked, will initiate the OAuth flow to authenticate the user.

- For email and password authentication: users will have the option to create an account or log in using their email address and a secure password. The frontend will feature forms for users to enter their email and password, with additional options for password recovery and account creation. These forms will be designed to ensure ease of use and security, including input validation and feedback messages.



#### Backend (Server Application)

For Google Authentication, the backend will handle the OAuth 2.0 flow, verifying the authentication tokens received from the frontend. This process involves:

1. Token Verification: The backend will verify the integrity and validity of the Google ID token using Google's public keys.
2. Database Management: The backend will check if the user already exists in the database. If not, it will create a new user record with the retrieved information. 
3. User Information Retrieval: Once verified, the backend will extract user information such as email, name, profile picture and others crucial information from the either the token or the database.

For email and password authentication, the backend will handle user registration, login, and password management:

1. User Registration: When a user registers, the backend will:
    - Validate the email format and password strength.
    - Hash the password using a secure hashing algorithm.
    - Store the user details in the database, ensuring the hashed password is saved securely.
2. User Login: When a user logs in, the backend will:
    - Retrieve the user record based on the email from the database.
    - Compare the hashed password with the stored hash.
    - Generate and return a secure session token if authentication is successful.
    - Retrieve all user's necessary information from the database.
3. Password Management: For password recovery and updates, the backend will:
    - Implement secure processes for password reset requests, including email verification and token expiration.
    - Allow users to update their passwords, ensuring the new password is hashed and stored securely.

#### Security Considerations
For Google Authentication, the OAuth tokens will be securely managed, and sensitive user data will be encrypted. For email and password login, passwords will be hashed and stored securely. Input validation and protection against common security threats, such as SQL injection and cross-site scripting (XSS), will be enforced.

## Backend

*Decompose the MVP into functional blocks.*

## Data Model

*What data are you collecting / managing?*

*How is it organised?*

*Where is it stored?*

*How is it shared/copied/cached?*

## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

