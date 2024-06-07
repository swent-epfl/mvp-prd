# Design and Implementation

## Frontend

### Implementation framework

The app is developed in Kotlin using Jetpack Compose using an MVVM architecture. The repository architecture is used for having a single interface for all data.

Furthermore the following libraries are used:
- Supabase: interaction with the backend
- Google Auth: for users wishing to sign in using it
- Maplibre: for a modern vector-rendering map; the central element of the app
- Google Play Location Service
- Hilt: depenency injection
- Room: local DB for synchronisation and caching


### Primary screens
- Main screen: map with events, allowing searching and filtering and discovery
- Secondary screen: list mode for events; the same search/filtering is applied
- Other screens:
    - My Events: allows to see created and joined events
    - My Profile: allows to modify the users profile
    - Create Event: screen to create events
    - Associations: shows associations and the relation the user is with them (following, committee member)

## Backend

The backend server hosts all necessary data and enforces access policies. We are using Supabase which combines a series of industry standard tools into a nice consolidated API with its library. Supabase provides authentication of users (additionnaly via Google OAuth), storage of structured data and object storage for files.
Access and modification is restricted based on the type and ownership of the element.

## Data Model

Alll the structured data i stored in the PostgreSQL database integrated into Supabase. 

### Authless Data

#### Tags

Purpose - Contains all the available tags. Tags include categories of type of events/interests as well as specific ones like Sections or Semester for the campus context.

Fields - Tag Id (Primary Key), Name, Parent Id

#### Events

Purpose - Contains information about all events added to the app.

Fields - Event Id (Primary Key), Creator Id, Organizer Id, Title, Description, Start Timestamp, End Timestamp, Location (Name, Long, Lat), Participant Count, Max Particiants

##### Event Tags

Purpose - Records represent tags assigned to an event.

Fields - Tag Id (Foreign Key), Event Id (Foreign Key) (Composite Primary Key)

#### Associations

Purpose - Contains information about the validated associations.

Fields - Association Id (Primary Key), Name, Description, Url

##### Association Tags

Purpose - Records represent tags assigned to an association.

Fields - Tag Id (Foreign Key), Association Id (Foreign Key) (Composite Primary Key)


### Auth UserData

#### User Profiles

Purpose - Contains information about the user 

Fields - User Id (Foreign Key) (Primary Key), Name

##### User Tags

Purpose - Records represent tags assigned to a user.

Fields - User Id (Foreign Key), Tag Id (Foreign Key) (Composite Primary Key)

##### Association Subscribtion

Purpose - Records represent users which follow associations.

Fields - User Id (Foreign Key), Association Id (Foreign Key) (Composite Primary Key)

##### Committee Member

Purpose - Records represent which users are member of a committee of an association and therefore get the right to publish in the name of the association.

Fields - User Id (Foreign Key), Association Id (Foreign Key) (Composite Primary Key)

##### Event Joins

Purpose - Records represent a user having joined (e.g. signed up for) a specific event. 

Fields - User Id (Foreign Key), Event Id (Foreign Key) (Composite Primary Key)


##### User Profile Picture

Profile pictures are stored as objects in the S3 bucket; access is restricted based on the ownership of the object.

## Security Considerations

Storage of user data is limited to the strictly required data for the app to work.
RLS (Row Level Scurity) policies restrict access to resources, preventing unauthorized users to access personal information like which events are joined by a given user. They also prevent modification of data by unauthorized users.
Additionally in accordance to GDPR compliability, the app will allow to completely delete all data of a given user.

## Infrastructure and Deployment

The primary infrastructur is a Supabase instance wich is currently hosted by Supabase themselves on Amazon AWS. The option to selfhost Supabase on whatever infrastructure (included on premise) exists.

## Test Plan

We will write integration tests for all possible user stories. Furthermore also the interaction with the backend service will be tested in a test environment. This helps to catch potential edge-case situations in interaction of multiple users.
