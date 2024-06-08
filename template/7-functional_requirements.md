# Functional Requirements

Key features of the MVP include:

- User management:
    - Account creation: users can register an account as pet owners looking to find groomers for their pets, or as groomers looking to find customers. This will require an authentication management system which will be delegated to third party providers.
    - User profile management: users can edit their profile information. For pet owners, this will include information about their pets, which will allow the application to find groomers matching their needs more easily. For groomers, this will include public information about the services they provide, which will allow them to reach potential customers more easily. Storing all of this data will be require a database management system.
- Groomer discovery:
    - Using data provided by the groomers and pet owners, the application will display a list of groomers matching certain criteria, making it easy for pet owners to find groomers for their pets. This will notably make use of geographical data, allowing pet owners to find groomers in their area.
- Appointment booking:
    - Groomers will be able to open reservation slots using a built-in booking system. Pet owners will then be able to book appointments with groomers. This will notably allow groomers to easily manage their schedule.
    - Calendar integration: the application will integrate the booking system to the calendar, allowing both groomers and pet owners to 

# Functional Requirements

## Key Features

#### User Authentication and Profile Management

- Account creation: users can register an account as pet owners looking to find groomers for their pets, or as groomers looking to find customers. 
- User profile management: users can edit their profile information. For pet owners, this will include personal information and preferences which will allow the application to find groomers matching their needs more easily. For groomers, this will include public information about the services they provide, which will allow them to reach potential customers more easily.

#### Groomer Discovery and Detailed Profiles

- Using data provided by the groomers and pet owners, the application will display a list of groomers matching certain criteria, making it easy for pet owners to find groomers for their pets. This will notably make use of geographical data, allowing pet owners to find groomers in their area.
- Users will be able to view detailed groomer profiles including offered services, reviews, and work portfolio.

#### Appointment Scheduling

- Groomers will be able to open reservation slots using a built-in booking system. Pet owners will then be able to book appointments with groomers. This will notably allow groomers to easily manage their schedule.
- Calendar integration: the application will integrate the booking system to the calendar, allowing both groomers and pet owners to manage their reservations seamlessly with their other schedule constraints.
- Users will also have the ability to activate reminders and notifications about upcoming appointments

#### In-App Messaging System

- This will allow pet owners to communicate directly with groomers.
- The messages will be sent and received within the app.

#### Secure Payment System

- Pet owners will be able to pay groomers directly through the app
- Users will be able to manage their wallet and view their transaction history.

#### Pet Profiles

- Pet owners can create and manage profiles for multiple pets.
- Pet owners can store pet-specific information and grooming history.

#### Reviews and Ratings

- Pet owners can rate and review groomers after each appointment.
- Pet owners can view reviews from other users to make informed decisions.

#### Map Integration

- The application can display groomer locations.
- It can provide directions and navigation to the grooming location.

## PetPamper's Architectural Diagram

The architectural diagram outlines the main components of the PetPamper application, divided into three layers: UI layer, Data layer, and External services and SDKs.

![image](https://github.com/PetPamper/prd/assets/91835061/48255cb7-36cb-4557-9c41-215aaf00ef21)

## Key Internal Functionality 

#### Authentication and Authorization

Use Firebase Authentication and third-party OAuth2 providers for secure user sign-in and management.
Handle user sessions and maintain authentication state.

#### Data Management

Store user, groomer, pet profiles, and appointment data using Cloud Firestore.
Use Firestore for real-time data synchronization and updates.

#### Groomer Discovery

Utilize geolocation services to find and display nearby groomers.
Query groomer data based on user location and preferences.

#### Appointment Scheduling

Implement a real-time booking system to manage appointments.
Sync appointment data between users and groomers.
Integrate with Google Calendar.

#### Messaging System

Integrate Stream IO for real-time messaging between users and groomers.
Handle message storage and retrieval securely.

#### Payment Processing

Integrate payment gateways to handle transactions, such as Stripe or PayPal.
Securely manage user wallet and transaction history.

#### Review and Rating System

Allow users to leave ratings and reviews for groomers.
Store and display reviews to assist other users in decision-making.

#### Map and Navigation

Use Google Maps SDK for displaying groomer locations and providing navigation.
Implement geocoding to convert addresses into geographic coordinates.

#### Geocoding and Location Services
Integrate Nominatim SDK for converting addresses into geographic coordinates.
Use Nominatim for additional location services, such as reverse geocoding to find addresses based on coordinates

