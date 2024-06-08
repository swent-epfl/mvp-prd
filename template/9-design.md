# Design and Implementation

## Frontend

The frontend primarily consists of the application's UI. It will be done using the Kotlin programming language and the Jetpack Compose framework. In the future, we may also consider using the Swift programming language to port the application to iOS devices, but that will be further down the roadmap.

The architecture will follow the MVVM pattern which is the norm for mobile applications. This allows for clean separation of concerns between the UI layer and the data layer, which makes replacing backend components easier without disrupting the user interface.
The UI components will therefore be agnostic of the information that they display, making them more reusable.

The information that is displayed by the UI will be abstracted as a "news source", making it easier to test the UI separately from the backend logic.

Coordinating the UI logic and the data layer will be done by the ViewModels and the domain layer of the application. They will be in charge of retrieving data from repositories, which constitute an additional layer of abstraction for the data layer. Their role is to choose from which data source to retrieve information from: for instance, in offline mode, the data source will change from the remote database to a local, cached database.

Essential screens will include:
- A login screen and a registration screen so that users can create an account and authenticate themselves
- For pet owners:
    - A home screen displaying their pets and booked reservations with groomers
    - A groomer discovery screen displaying groomers in your area, information regarding their services and their ratings from other pet owners
    - A more detailed groomer profile containing a description, pictures and more detailed user reviews
    - An appointment booking screen for each groomer
    - A chat to discuss details with groomers
    - A profile screen with the ability to edit information, preferences and settings
    - A screen to edit information concerning pets
- For groomers:
    - A home screen displaying booked reservations
    - A reservation screen to manage reservations and reservation slots
    - A chat to discuss with potential customers
    - A profile screen with the ability to edit information, provided services and settings

## Backend

*Decompose the MVP into functional blocks.*

The backend will deal with several important components:
- Authentication: this will be integrated within the application using Firebase Authentication and third-party OAuth 2 providers such as Google or Facebook
- Database management system: this will primarily use Cloud Firestore.
- A payment system: this will be done by integrating third-party payment gateways such as Stripe, PayPal or Google Pay

## Data Model

### What Data Are You Collecting / Managing?
- User Data:
    - Personal details: name, email, contact information
    - Profile picture
    - PawPoints
    - Preferences and settings

- Groomer Data:
    - Professional details: services offered, pricing, availability
    - Location information
    - Profile pictures and contact information

- Pet Data:
    - Pet details: name, type (dog, cat, etc.), description, age

- Reservation Data:
    - Booking information: date and time, groomer email, groomer name, price, reservation ID, services, user email

- Review Data:
    - Ratings and reviews provided by users for groomers
    - Timestamp of reviews

- Chat Data:
    - Messages exchanged between pet owners and groomers
    - Timestamps and sender/receiver information

- Authentication Data:
    - Authentication tokens: access and refresh tokens (passwords are not collected or stored)

### How Is It Organised? Where Is It Stored?

All data is stored in Google Firebase Firestore, a NoSQL cloud database. Firestore collections and documents are used to structure the data, ensuring efficient access and real-time updates.

### How Is It Shared / Copied / Cached?

- Realtime Updates: Firestore automatically provides real-time updates to all connected clients, ensuring that users see the latest information instantly.
- Local Caching: Firebase handles local caching for offline access and faster load times. Data is cached on the client device and synchronized with the server when the device reconnects to the internet.

### Data Sharing:

Data is shared between the client app and the backend via Firebase APIs. The frontend accesses data through ViewModels that interact with Firestore, ensuring a clear separation of concerns and adherence to the MVVM architecture.

Secure Storage: Sensitive data such as authentication tokens are securely stored using Android Keystore, ensuring data protection on client devices.

This clear organization and management of data ensure that PetPamper is robust, scalable, and secure, providing a seamless experience for users.



## Test Plan and deployment

### Development Process:

The application is developed using Android Studio with Kotlin and Jetpack Compose.
The development follows the MVVM architecture to ensure a structured separation of concerns between the UI and business logic.

- Testing Process:

    - Unit Tests: Conducted using JUnit to test individual components and business logic.
    - UI Tests: Conducted using Espresso to test user interface interactions and flows.
    - Regular code reviews and continuous integration (CI) are used to ensure code quality and catch issues early.

- Deployment Process:

    - CI/CD Pipeline: Set up using GitHub Actions to automate the build, test, and deployment processes.
    - Automated tests run on every commit to ensure code quality.
    - Successful builds are deployed to the Google Play Store.

- Special Infrastructure Requirements:

    - Firebase Integration: Configuration and integration of Firebase services such as Firestore, Authentication, Cloud Messaging, and Cloud Functions.
    - CI/CD Tools: GitHub Actions for continuous integration and continuous deployment.
    - Hosting: Backend services are hosted on a scalable cloud infrastructure, ensuring high availability and performance.

### Test Plan
#### Development, Testing, and Deployment:

- Development:
    - Code development in Android Studio using Kotlin and Jetpack Compose.
    - Use Git for version control and GitHub for repository management.

- Testing:
    - Unit Tests: Use JUnit to test individual components and business logic.
    - UI Tests: Use Espresso to test the user interface and user interactions.
    - Conduct integration tests to ensure different parts of the application work together seamlessly.
    - Perform security testing to identify and fix vulnerabilities.

- Deployment:
    - Use GitHub Actions to automate the build, test, and deployment processes.
    - Deploy the application to the Google Play Store for distribution.
    - Monitor application performance and errors using Firebase Crashlytics and Performance Monitoring.

- Special Infrastructure Requirements:
    - Firebase Services: Firestore for database, Authentication for user management, Cloud Messaging for notifications, and Cloud Functions for server-side logic.
    - CI/CD Pipeline: GitHub Actions for automating the testing and deployment processes.
    - Staging Environment: A separate environment for final testing before production deployment to ensure stability and reliability.