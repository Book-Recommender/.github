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

## Reflction: Jonathan Zhang

## Reflection: Edgardo Gonzalez

## Reflection: Melody Lam
