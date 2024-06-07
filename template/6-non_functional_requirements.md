# Non-Functional Requirements

## Security, privacy, and data retention policies

*Which are the applicable laws and regulations?*
- Comply with GDPR for users in Europe regarding data protection and privacy.
- Adhere to any local privacy laws based on the geographical operation.

*What are your internal policies?*
- Regular audits and compliance checks to ensure ongoing adherence to all applicable laws.

*Which privacy features do you need from the phone?*
- Access to camera for QR code scanning.
- Access to current user location to find and suggest local events.

## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*
- Predict regular weekend peaks due to event searches and registrations.
- Anticipate high traffic during popular cultural and sporting event periods.

*Are there known periods of bursty traffic that the MVP must be designed to support?*
- When multiple users join an event concurrently, there should be atomic changes to the database.
