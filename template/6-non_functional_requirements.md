# Non-Functional Requirements

## Security, privacy, and data retention policies

The application's security critical components include the authentication and payment systems. Authentication will be delegated to third party authentication providers, and the payment will also be delegated to third-party payment gateways such as PayPal or Google Pay.

PetPamper stores Personal Identifiable Information, and is therefore subject to privacy and data protection regulation laws. However, there is no further processing of this data, and data subjects can request for their data to be deleted at any time.

The application may store data related to a pet's health, however privacy laws do not apply to animals.

Below, are stated the laws and regulations thus applicable to PetPamper.

### Applicable Laws and Regulations

GDPR (General Data Protection Regulation): Ensures the protection of personal data for users in the European Union.

Swiss Federal Act on Data Protection (FADP): Compliance with Switzerland's data protection laws to safeguard user information.

PCI DSS (Payment Card Industry Data Security Standard): Ensures secure processing of payment information.

### Internal Policies

The internal policies therefore simply include: 

Data Encryption: Sensitive personal information and payment details are encrypted both in transit and at rest using Firebase's built-in security features.

Access Control: Ensure only authorized personnel can access stored data on Firebase.

Data Retention: Regular audits will be conducted within the Firebase environment to ensure data is deleted when no longer needed.

Incident Response: Utilize Firebase's security features to monitor and respond to data breaches.

### Privacy Features 

Privacy features that are needed from the phone are strictly optional, and the user will be asked whether they agree to the use of these features.

Geolocation: Allows users to find groomers near them. Users will be asked for permission to access their location data.

Camera: Allows users to upload pet photos and groomers to update their portfolios. Users will be asked for permission to access the camera.

Push Notifications: Users may allow the application to send them push notifications for appointment reminders, and messaging updates.

## Adoptions, Scalability and Availability

### Driving Adoption

To drive adoption, the application should focus on ease of use for both users and groomers. Early adoption is crucial as one of the main value propositions of the app is to connect pet owners to local groomers. Key strategies include:

User-Friendly Interface: Ensure the app is intuitive and easy to navigate for all users.

Effective Onboarding: Provide clear instructions and support for new users and groomers to get started quickly.

Marketing and Promotions: Utilize targeted marketing campaigns and promotional offers to attract initial users and groomers.

### Traffic Patterns and Bursty Periods

We expect traffic to remain fairly constant, with potential variations during specific periods:

Daily Traffic: Steady flow of user interactions throughout the day, with peaks during morning and evening hours when users typically schedule appointments - say after a 9-5.

Weekly and Monthly Trends: Higher traffic during weekends and at the start of each month when users tend to book grooming sessions.

Seasonal Variations: Increased activity during warmer seasons when pets might require more frequent hair trimming.


Adoptions, Scalability, and Availability
Driving Adoption

To drive adoption, the application should focus on ease of use for both users and groomers. Early adoption is crucial as one of the main value propositions of the app is to connect pet owners to local groomers. Key strategies include:

User-Friendly Interface: Ensure the app is intuitive and easy to navigate for all users.
Effective Onboarding: Provide clear instructions and support for new users and groomers to get started quickly.
Marketing and Promotions: Utilize targeted marketing campaigns and promotional offers to attract initial users and groomers.
Traffic Patterns

We expect traffic to remain fairly constant, with potential variations during specific periods:

Daily Traffic: Steady flow of user interactions throughout the day, with peaks during morning and evening hours when users typically schedule appointments.

Weekly and Monthly Trends: Higher traffic during weekends and at the start of each month when users tend to book grooming sessions.

Seasonal Variations: Increased activity during warmer seasons when pets might require more frequent hair trimming.

The MVP must be designed to support periods of bursty traffic, such as:

Promotional Events: Spikes in traffic during promotional campaigns or special offers.

Holiday Seasons: Increased activity when pet owners prepare for trips or events.

Post-Launch Surge: Initial burst of traffic following the MVP launch as new users sign up and explore the app.

Given that the MVP is primarily targeted at Swiss customers, there is a cap on the number of potential users (for now). 
However, scalability and availability remain critical to ensure a seamless experience. Utilizing Firebase's auto-scaling and load-balancing capabilities while continuously monitoring performance metrics, PetPamper can ensure a secure, reliable, and scalable experience that drives adoption and handles varying traffic patterns effectively.

