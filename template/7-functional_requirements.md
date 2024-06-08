# Functional Requirements

## Key Features

#### User Authentication and Profile Management

Sign in through Firebase Authentication (Google Sign-In).
Create and manage user profiles, including personal information and preferences.

#### Groomer Discovery and Detailed Profiles

Find nearby groomers using location data.
View detailed groomer profiles including services offered, reviews, and work portfolio.

#### Appointment Scheduling

Schedule grooming appointments in real-time.
Manage appointment availability and receive reminders.

#### In-App Messaging System

Communicate directly with groomers.
Send and receive messages within the app.

#### Secure Payment System

Process payments securely through integrated payment gateways.
Manage wallet and transaction history.

#### Pet Profiles

Create and manage profiles for multiple pets.
Store pet-specific information and grooming history.

#### Reviews and Ratings

Rate and review groomers after each appointment.
View reviews from other users to make informed decisions.

#### Map Integration

Display groomer locations.
Provide directions and navigation to the grooming location.

## PetPamper's Architectural Diagram

The architectural diagram outlines the main components of the PetPamper application, divided into three layers: UI layer, Data layer, and External services and SDKs.

![image](https://github.com/PetPamper/prd/assets/91835061/48255cb7-36cb-4557-9c41-215aaf00ef21)

## Key Internal Functionality 

#### Authentication and Authorization

Use Firebase Authentication for secure user sign-in and management.
Handle user sessions and maintain authentication state.

#### Data Management

Store user, groomer, pet profiles, and appointment data in Firebase.
Use Firebase Firestore for real-time data synchronization and updates.

#### Groomer Discovery

Utilize geolocation services to find and display nearby groomers.
Query groomer data based on user location and preferences.

#### Appointment Scheduling

Implement a real-time booking system to manage appointments.
Sync appointment data between users and groomers.

#### Messaging System

Integrate Stream IO for real-time messaging between users and groomers.
Handle message storage and retrieval securely.

#### Payment Processing

Integrate payment gateways to handle transactions.
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


