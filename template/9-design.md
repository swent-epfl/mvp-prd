# Design and Implementation

## Frontend

*List the key libraries, languages, components used by the MVP.*


*If applicable, describe essential screens.*

Frontend
Implementation Framework:

Language: Kotlin
Framework: Jetpack Compose, optimized for Android
Architecture: Model-View-ViewModel (MVVM)
Dynamic UI Rendering Strategy:

The data layer will fetch UI descriptions in a machine-readable format for each feature, such as groomer profiles, booking forms, and reviews.
These descriptions will contain details about what frontend fragments need to be rendered for each plugin.
The ViewModel will interpret these descriptions to determine the fragments to be displayed in the view of each activity.
This dynamic rendering will allow for flexible UI adjustments in response to changes in service APIs or UX improvements.
Adaptability to Service API Changes:

The flexible UI design will be key in adapting to any future API changes. For example, if new features are added to the groomer profiles, these changes will be incorporated in the backend’s machine-readable UI description and seamlessly integrated into the app without major redevelopment.
Security and Data Management Focus:

The frontend will securely store refresh tokens and cache necessary app data.
This approach will prioritize the security of sensitive information and the efficiency of the app’s performance.

Essential Screens:

Welcome Screen:
Sign in with Google or manual authentication
Brief introduction to the app’s features
Home Screen:

Dashboard displaying available pet groomers
Search functionality to find groomers by location or specialty
Groomer Profile Screen:

Detailed profile of each groomer
Services offered, pricing, reviews, and booking options
Booking Screen:

Calendar for selecting appointment date and time
Booking form with pet details and special requests
User Profile Screen:

User details and preferences
History of past bookings and reviews

Home Screen that show reservation and pet management. 

Chat to discuss with groomers

## Backend

*Decompose the MVP into functional blocks.*

## Data Model

*What data are you collecting / managing?*

*How is it organised?*

*Where is it stored?*

*How is it shared/copied/cached?*

Data Model for PetPamper
What Data Are You Collecting / Managing?
User Data:

Personal details: name, email, contact information
Profile picture
PawPoints
Preferences and settings

Groomer Data:
Professional details: services offered, pricing, availability
Location information
Profile pictures and contact information

Pet Data:
Pet details: name, type (dog, cat, etc.), description, age

Reservation Data:
Booking information: date, experienceYears, groomerEmail, groomerName, hour, price, reservationId, services, userEmail

Review Data:

Ratings and reviews provided by users for groomers
Timestamp of reviews

Chat Data:
Messages exchanged between pet owners and groomers
Timestamps and sender/receiver information
Authentication Data:

Authentication tokens: access and refresh tokens (passwords are not collected or stored)
How Is It Organised?


Where Is It Stored?
All data is stored in Google Firebase Firestore, a NoSQL cloud database.
Firestore collections and documents are used to structure the data, ensuring efficient access and real-time updates.
How Is It Shared / Copied / Cached?

Realtime Updates: Firestore automatically provides real-time updates to all connected clients, ensuring that users see the latest information instantly.
Local Caching: Firebase handles local caching for offline access and faster load times. Data is cached on the client device and synchronized with the server when the device reconnects to the internet.

Data Sharing:

Data is shared between the client app and the backend via Firebase APIs.
The frontend accesses data through ViewModels that interact with Firestore, ensuring a clear separation of concerns and adherence to the MVVM architecture.
Secure Storage: Sensitive data such as authentication tokens are securely stored using Android Keystore, ensuring data protection on client devices.
This clear organization and management of data ensure that PetPamper is robust, scalable, and secure, providing a seamless experience for users.


## Security Considerations

## Infrastructure and Deployment

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*

## Test Plan

*How is the application developed, tested and deployed?*

*Any special infrastructure requirements.*



Development Process:

The application is developed using Android Studio with Kotlin and Jetpack Compose.
The development follows the MVVM architecture to ensure a structured separation of concerns between the UI and business logic.
Testing Process:

Unit Tests: Conducted using JUnit to test individual components and business logic.
UI Tests: Conducted using Espresso to test user interface interactions and flows.
Regular code reviews and continuous integration (CI) are used to ensure code quality and catch issues early.
Deployment Process:

CI/CD Pipeline: Set up using GitHub Actions to automate the build, test, and deployment processes.
Automated tests run on every commit to ensure code quality.
Successful builds are deployed to the Google Play Store.
Special Infrastructure Requirements:

Firebase Integration: Configuration and integration of Firebase services such as Firestore, Authentication, Cloud Messaging, and Cloud Functions.
CI/CD Tools: GitHub Actions for continuous integration and continuous deployment.
Hosting: Backend services are hosted on a scalable cloud infrastructure, ensuring high availability and performance.
Test Plan
Development, Testing, and Deployment:

Development:

Code development in Android Studio using Kotlin and Jetpack Compose.
Use Git for version control and GitHub for repository management.
Testing:

Unit Tests: Use JUnit to test individual components and business logic.
UI Tests: Use Espresso to test the user interface and user interactions.
Conduct integration tests to ensure different parts of the application work together seamlessly.
Perform security testing to identify and fix vulnerabilities.
Deployment:

Use GitHub Actions to automate the build, test, and deployment processes.
Deploy the application to the Google Play Store for distribution.
Monitor application performance and errors using Firebase Crashlytics and Performance Monitoring.
Special Infrastructure Requirements:

Firebase Services: Firestore for database, Authentication for user management, Cloud Messaging for notifications, and Cloud Functions for server-side logic.
CI/CD Pipeline: GitHub Actions for automating the testing and deployment processes.
Staging Environment: A separate environment for final testing before production deployment to ensure stability and reliability.


