# Business Model

## Expected operating Costs

Most of the backend of the application is managed via services proposed by [*Google's Firebase*](https://firebase.google.com) and various Google Cloud APIs which operates under a "Pay as you go" pricing model. During the developpment period, the free solution was enough to test and developp our features, but will be way too restrictive for hundreds or thousands of active users.

 The app is also using two other APIs for [*weather predictions*](https://openweathermap.org/api) and [*location auto-completion*](https://radar.com/product/api) that offer free plans for small scale business, but might not be enough for a thriving application.

Lasta's operating cost will therefore entirely depend on the number of active users since all these APIs have costs directly linked to the number of requests. Since we do not know the exact number of active users the app is going to get, it is hard to predict the cost per month. It is important to keep in mind that all the services used are extremly scalable and the app will therefore hardly be limited in term of performance.

You will find bellow a table with the expected operating costs according to the number of active users.
| **Number of active users**    | Cost / month |
| ---------------------------- | ----- |
| <=10K (only the weather API would need paiement)                         | 15.-  |
|                              | 0.5$  |


