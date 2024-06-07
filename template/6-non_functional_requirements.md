# Non-Functional Requirements

## Security, privacy, and data retention policies

### Security

In 2023, the New Swiss Data Protection Act went into effect adding new requirements to the previous Federal Act on Data Protection (FADP). This includes strict regulation of personal data processing activities we must comply with. In Student Sphere, the user signs up only with an email address. If this address belongs to EPFL domain then we fetch the public information using the “EPFL People” website (this allows us to display their name, major, association major role and year). We do not fetch any sensitive information about the user (considered sensitive personal data by the FADP). We do not plan on coordinating with EPFL IT to use their “Tequila API” since it will be soon replaced by another service

### Privacy

Along with security, the FADP also governs the protection of personal privacy. It requires data controllers to inform individuals about data collection, processing, and their rights, including access, correction, and deletion of their data. Student Sphere will display a license to accept upon signing up. This license will explain to the user, the information we fetch from “EPFL People”.
As Switzerland is not part of the EU, the General Data Protection Regulation (GDPR) is not directly applicable. However, our app may process personal data of EU citizens (French students, Belgian students etc.), so GDPR compliance is essential. GDPR mandates stringent data protection and privacy measures, like FADP but with broader scope. Our backend should be designed so that we do not infer any personally identifiable information from users’ actions (news creation, following association etc.). 

### Data Retention

The Swiss Code of Obligations requires certain business records, including those involving personal data, to be retained for a specific period, typically 10 years. In Student Sphere, we retain information (name, major, association major role and year) for less than 10 years because 10 years is longer than the maximal possible duration of EPFL studies. Upon graduation, student information is useless in our database, so it is deleted.
Under FADP, personal data should not be retained longer than necessary for the purposes for which it was processed. This principle mandates regular data review and deletion protocols. Student Sphere will implement deletion protocols (upon graduation) and regular data review (database review).

## Adoptions, Scalability and Availability

### Adoption

1. Users must be able to disable every notification from the app to avoid unnecessary distraction
2. The application should, by default, disable all notifications
3. Users should have the possibility to personalize the appearance of their app

### Scalability

1. The application must be able to handle daily traffic (thousands of students, concurrent event creation etc.)
2. Latency, robustness, and performance should be maintained even during events with high attendance (ex : Festival Balélec)
3. Scalable solutions should include local caching and backend load balancing, to ensure a smooth experience to users during high volume traffic 

### Availability

1. The application must be adapted to every screen sizes. Everything should be visible even though the user must scroll to see it
2. The application should not be responsible for its own crash, the system must be robust
3. Offline mode should be automatically triggered when device is not (or poorly) connected to the internet
4. Continuous monitoring system should be deployed to detect and address bursty traffic (allocate more resources to face the high number of requests)
