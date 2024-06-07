# Non-Functional Requirements

## Security, privacy, and data retention policies

*Which are the applicable laws and regulations?*

Our applicatin will collect some personal data such as :
    - First and Last name (if the user don't use a nickname)
    - email adresse (necessary for the signIn)
    - pictures 
    - conversations (private or group conversation)
    - locations
    - affilated university (depending on the group name)
    - friend relations (we could link the user to his friends/contact)
    - credential informations (if the user subscrite to some paid functionalities)
Other personal information could also be entered in the application via the messages, or othe features (to do list, calendar,...). 

For **security** purpose, we should assure that none of these informations are leacked or publically availble. Let's remind that the swiss Federal Act on Data Proectection (FADP) ensure the protection of ["the personality and fundamental rights of natural persons whose personal data is processed"](https://www.google.com/search?client=opera-gx&q=FADP&sourceid=opera&ie=UTF-8&oe=UTF-8). To be more precise, the art.8 of this laws states that *"The controller and the processor shall guarantee a level of data security appropriate to the risk by taking suitable technical and organisational measures"*. If we are still developping application in Switerzland we must apply the mentionned law and assure a proper data protection.
We could implement some cryptography strategies to crypt our data and protect user personal informations.
Concerning the app developers, we should also ensure that no API keys or similar sensible data are visible in the code online (for example in git).

The user **privacy** should also be respected

Most data on the app are stored in the database 


- Security:  
ensure no user credentials are saved in local or publically displayed
- Privacy : ensure user privacy in private chats
- Data retention : Only keep tracks of a user's and group's own data

*What are your internal policies?*

- Ensure user can only access its own information and information of groups they belong to
- Democratic policy : groups use a voting system to approuve or disprouve on big decisions

*Which privacy features do you need from the phone?*

- Access to contact list, camera, microphone, location among others

## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*

- Stable traffic usually, maybe more at night

*Are there known periods of bursty traffic that the MVP must be designed to support?*

- Periods of revisions for exams 