# Functional Requirements


## Ticket systems


## Motivation

The StudentSphere MVP answer issues related with association life at EPFL:
-Visibility of events and associations
-Recruitment
-Event ticketing
-Event Staffing
-Centralisation of Association information
These activities as an Association at EPFL is typically resolved by an intense and tiresome communication campaign through Instagram and Physical posters. Both not having as sole purpose to reunite students with same goals and interests. The key to our concept is centralisation of information. We want to create a place for each Association can manage their identity and management. In Association life at EPFL association mangers are also users that want to attend events and recurent issue is the physical ticket system that is vunerable to falsification and loss. We aim at changing the way we carry and use our tickets

### Proposed Solution

A wallet system on the application for now, that allows for now users to enter the mail of the user and create a ticket for the user associated with the email. Then the user can scan a NFC tag to verify at the entrance if he has the correct ticket to enter. Staffs have staff tickets created as soon as they are accepted as staffs allowing a smoother gestion of tickets and a faster count how many people have tickets as staff or ass particicipants. The tickets are stored in general collection "tickets" where all tickets are stored with their attibutes. The user on the other hand has the ticket ID he owns in a collection of his own so it is easier to fetch the tickets in firebase read calls. Tickets can now also be created by scanning a QRcode associated with the event.

### User identtification (Scrapping)

#### Motivation

We need at every login know who is the user for the EPFL community and double check information. At EPFL everyone is known with theri sciper and being able to link accounts with it and therefore in a near future automatise admin tasks for registration and statistics on users.

#### Proposed Solution

At every Signup we call a firebase function that scraps with users email its sciper, section, name , surname and possible roles in associations (very hard as EPFL's website does notuse the same acronym as the association list website). The firebase function creates an element User with its arguments and stores it in the collection "users", if the email is not found it creates an empty user and is considered and out of EPFL user however many associations welcome members fro other schools o we don't want to limit accessibility.

### User analytics and acceptance

Before full rollout of the MVP, we must implement and put in place a pipeline to collect relevant information on how users are using our application. This will allow us to identify improvements and fix bugs. Additionally, we will track the following metrics and leverage the following faucets to find PMF.

#### Usage Metrics

1. User Engagement: Frequency of app use, session duration, and navigation paths.
2. Feature Use: Number of accesses to key features (food menus, Moodle, printing services, news and camipro).
3. Conversion Rates: From app download to active usage.
4. User Retention: Rate of returning users over time.
5. Drop-off rate: what UI transitions have high drop off

#### Success Criteria

1. High user engagement and retention rates - more than 70% returning users.
2. Low crash rates and quick resolution of identified issues.

#### User Analytics

1. Implement Google Analytics for behavioral tracking and Firebase Crashlytics for stability monitoring.
2. Anonymize data to comply with privacy standards.

#### A/B Testing Ideas

1. Test different navigation flows to find the most user-friendly layout.
2. Experiment with different formats of displaying food menus and Moodle content.
