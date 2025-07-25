# "Meme Game"

## React Client Application Routes

- Route `/`: index page with login button and also has a button to play as a guest
- Route `/login`: login page
- Route `/history`: this route is related to display the result of previous games
- Route `/result`: for displaying the summary of the game after finishing it successfully
- Route `/results/:id`: this route is related to display summary of a spcific game which has played before
- Route `/images/:imageId`: for starting the game with a random image which has got from the imageId params for authorized users
- Route `/unauth/:imageId`: for starting the game with a random image which has got from the imageId params for unauthorized users


## Main React Components

- `Login` (in `AuthComponents.jsx`): provide the main form of login page
- `History` (in `History.jsx`): it's related to the page which can provide some links to have access to result of previous games
- `Homepage` (in `Homepage.jsx`): home page of authorized users
- `ImageLayout` (in `ImageComponents.jsx`): the main components for showing images and captions during the game
- `Play` (in `Play.jsx`): home page of the webapp
- `Result` (in `Result.jsx`): showing the summary of the game after finishing it
- `ResultHistory` (in `ResultHistory.jsx`): for showing summary of previous games
- `Timer` (in `Timer.jsx`): calculate and show the reverese timer
- `Unauth` (in `Unauth.jsx`): to play the game for unauthorized users


## API Server

- POST `/api/answers`: storing the information of user from the game that the user played
  - request: an object including points, user, answer, images's url, and correct answers for each image
  - response: a text for informing about the status
  - response status: if saving data is successfully the text which is sent is info saved successfully, otherwise the text is Error saving info
  - if there is any error the response status is 500, otherwise it's 200
- POST `/api/sessions`: posting session info for login user
  - request: user info
  - response: user info
  - response status: if user can login successfully response status is 201, else it's 401
- POST `/api/sessions/currect`: posting session info
  - request: user info
  - response: user info
  - response status: if user logged in response status is 201, else it's 401
- GET `/api/questions`: Get all the captions
  - response: all the captions in json
  - response status: if there is any error the response status is 500, otherwise it's 200
- GET `/api/images`: Get all the images' url
  - response: all the images' url in json
  - response status: if there is any error the response status is 500, otherwise it's 200
- GET `/api/questions/:id`: Get a specific caption which has the id of :id
  - request: id of thte specific caption
  - response: the caption that requested in json
  - response status: if the caption respond successfully the response status is 200, else if it cannot get the caption from database the response status is 404, otherwise it is 500
- GET `/api/images/:id`: Get a specific image's url which has the id of :id
  - request: id of the specific image's url
  - response: the url that requested in json
  - response status: if the caption respond successfully the response status is 200, else if it cannot get the caption from database the response status is 404, otherwise it is 500
- GET `/api/answers/:user`: Get information which the user with id of :user have played so far
  - request: id of user
  - response: all the information for requested user in json
  - response status: if the caption respond successfully the response status is 200, else if it cannot get the caption from database the response status is 404, otherwise it is 500
- DELETE `/api/sessions/currect`: logout user
  - request: logout
  - response: end of the session


## Database Tables

- Table `user` - for storing information of authorized users(id, name, email, password, salt)
- Table `question` - for saving the captions(id, text, imageId, authorId, date)
- Table `image` - for storing images' url(id, url, authorId, date)
- Table `answer` - in order to store the previous games(id, text, userId, urls, canswer, answer)


## Screenshots


![1](https://github.com/MortezaGhoddousi/MEME_GAME/assets/143504966/6559a114-b7e8-451a-8400-ce6b6fbb221f)


![2](https://github.com/MortezaGhoddousi/MEME_GAME/assets/143504966/8fe5be8d-bc92-476e-a941-52208aa59d7f)


![3](https://github.com/MortezaGhoddousi/MEME_GAME/assets/143504966/b37bdf04-6369-43d2-afd1-705c5cb3af3d)


![4](https://github.com/MortezaGhoddousi/MEME_GAME/assets/143504966/c590aa4f-b397-45df-aa59-ddd66a64ad64)

## Users Credentials

- email: admin@gmail.com, password: myadmin
