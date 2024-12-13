## Book Club Description

### Book Club is a web application that provides the user with book recommendations, allows them to track the books they have already read, and keep track of what books they are currently reading.

## Repositories:

### Frontend: https://github.com/Book-Recommender/frontend

### Backend: https://github.com/Book-Recommender/backend

### Learning Model: https://github.com/Book-Recommender/learning-model

## Reflection: Kamaljeeth Vijay
In order to improve this project, I believe the best course of action would be to consider how exactly the SVD() model is getting its results. We had designed the model so that it utilized a sparse matrix that had a relation of user ID : {book_list, rating_list}. The backend needs quite a bit of work to accomodate the learning model, as the backend does not current have the right input type into the model, as it only inputs a list of books without a user ID and a list of ratings for the books. These ratings are essential to the dot product calculations necessary for a proper SVD model, and the user ID is used to query the sparse matrix, so without these important values, the model is unable to operate on the current backend. Additionally, because the model is currently not connected to the database, these user IDS are only placeholders that get recommendations from user IDs that already exist in the dataset used for getting book data (and training the model). The database could be modified to account for this shortcoming by being able to store book ratings, and have numerical user IDs for each user, as this would make utilizing the model for real, dynamic data more feasible. Additionally, the model does not automatically return the authors of the books, which the database and frontend need. This is a small fix, but would improve compatibility with the rest of the system. Finally, a system could be devised in the frontend and backend to get ratings on books that the user has read, in order to generate legitimate book rating data for the model, rather than examples of hypothetical scores. While there may be more necessary changes to improve the project, these are the essential changes that would improve the project without changing too many aspects of the project.

## Reflection: Matteo Spatola

## Reflection: Anim Ohene

## Reflection: Jonathan Zhang

To improve this project, I would modify the model to not take into account user ratings, or at least not require them. Modern recommender systems typically don't rely on ratings since users usually don't review everything that they consume, as well as there being response bias towards better reviews. Since neither the frontend nor backend supported the user ratings for books they've read, it was difficult to apply the model to our data. The workaround proposed by the ML team was simply to generate random ratings and supply them to the model that way. Ideally, the model should be able to cope with not having ratings, and only take them into account if they are provided. In the absence of ratings, it would simply work by association: people usually read books that are similar, so we can use this as a basis for recommendations. Many recommender systems these days work like this, particularly for movies or TV shows. Additionally, to better mitigate the cold start problem, we could ask the user for additional data when they first sign up, like their favorite genre, in order to have decent first recommendations even when there is no data. 

Another issue that came up was that the code to use the model was specialized to one user at a time, meaning that we needed to retrain the entire model for each user that we wanted recommendations for. In the future, this should be fixed to allow reusing a trained model for many predictions, to avoid doing the work of retraining over and over again.

## Reflection: Edgardo Gonzalez
To improve this project, I propose two methods. The first is to alter the database to meet the requirements of the current model. The first change is storing the user ID as an integer instead of an arbitrary string. The second change is that the model requires user ratings to make recommendations. Currently, the database does not store any user ratings. Adding a column to the UserBook table to store a user's rating of any book and making necessary changes to the front end to get said rating would fix this issue. These changes would make the integration process simpler. Lastly, one would need to update endpoint functions that interact with the database to match the changes to the database model. The second improvement to the project would be the implementation of new features. One feature that could improve the project is a virtual bookmark. Adding columns to the Book table that detail the size of the book via pages and chapters, along with adding columns to the UserBook table to keep track of which chapter and or page the user is on, would mean that users do not need to use an actual physical bookmark, therefore making the application more practical. Another practical new feature would be to add a friends list. This list would store any users that a specific user wants to follow. Friends would have access to each other's reading lists, creating another avenue of book recommendations. Seeing what friends are reading would also promote conversations between users about books on both their lists. To implement this change, add a column to the User table that stores a list of user IDs and update any endpoint functions that involve user information. Ensuring the database model matches the machine learning model's input and output and adding new convenient features would make this project a tool avid readers would always want to use. 

## Reflection: Melody Lam
