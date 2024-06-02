# User Analytics and Acceptance

## Key Metrics
- **Flight Scheduling Efficiency:** Time saved in scheduling flights compared to previous methods.
- **Employee Coordination:** Improvements in coordination metrics, such as reduced communication delays or increased on-time performance.
- **Task Completion Rate:** Percentage of tasks (e.g., scheduling flights, assigning crews) completed through the app compared to total tasks.
- **Error Reduction:** Tracks the decrease in errors (e.g., scheduling conflicts, miscommunication) since implementing the app.
- **Subscription Rates:** Number of companies subscribing to paid plans.

## Success Criteria
- **High Task Completion Rate:** More than 90% of tasks related to employee management and flight scheduling are successfully completed within the app.
- **Improved Flight Scheduling Efficiency:** More than 80% of flights are scheduled at least 20% faster than with previous methods.
- **Strong Subscription Rates:** Convert a majority of registered companies to paid plans within the first three months.

## Analysis Plan
- **Data Collection Methods:**
With the tools of Firebase Analytics and Google Analytics we already collect different times for creation, validation, termination and duration of a flight.
We also collect user interactions metrics with the app with features like daily, weekly and monthly Active users and the sessions lengths and frequency for each users.
We're going also to incorporate direct user feedback mechanisms, such as surveys or interviews, periodically to capture qualitative insights that might not be evident through behavioral data alone.
To maintain data integrity and privacy, we implement rigorous security measures. Data is anonymized and encrypted both in transit and at rest. Access to analytics data is restricted to authorized personnel only, ensuring that user information is handled in compliance with relevant privacy regulations and policies. 

- **Data Analysis Techniques:**
With the help of charts (histograms, box plots, scatter plots), we're going to identify long-term movement in data in our metrics to see how close we are to our success criteria.

## A/B testing ideas
#### In-App Messaging for Coordination:
- **Variation A:** Simple messaging system for crew and pilot coordination.
- **Variation B:** Advanced messaging system with file sharing and group chat capabilities.
    ##### Metrics to Measure : 
    - Frequency of messaging feature usage.
    - Coordination efficiency (measured by on-time task completion).
    - User feedback on messaging system usability.
#### Employee Management Features:
- **Variation A:** Basic employee management with core functionalities (adding/editing profiles, assigning roles).
- **Variation B:** Advanced employee management with additional features (performance tracking, shift scheduling).
    ##### Metrics to Measure : 
    - Admin engagement with employee management features.
    - Admin satisfaction with employee management tools.




