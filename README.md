# Fullstack Social Media App

This project will use the following tools:

#### Frontend: 
- React, JavaScript, React Router (navigation), Formik & Yup (form validation), redux toolkit (state management), Redux Persist(store in local storage), React dropzone for image uploads

#### Backend: 
- Node.js(runtime), Express.js(backend framework), Mongoose (managing Mongo database), JWT (authentication), Multer (file uploads)
- *Other backend packages:* body-parser(process req body), bcrypt(PW encryption), Cors(cross origin request), dotenv(env variables), gridfs-stream(file upload), multer & multer-gridfs-storage(upload files locally), helmet(req safety), Morgan(login)

## Steps

### Backend:
##### Boiler plate set up for client and server.

##### Hooked up MongoDB to server.

##### Designed database structure.

##### Set up authentication:
- Set up register user API. Register router middleware will be with Multer upload variable in index file. Create controller in separate controllers/auth.js file.
- Set up login API in a seperate folder. Login router middleware may be in its own /routes/auth.js file along with remaining router middlwares to be installed. Controller middlware will be with other controller middleware functions.
##### Set up authorization: Hit API endpoints unauthorized users lack access to
- create verifyToken middleware function in middlware/auth folder.
- create USER routes (grab particular users via ID, getting user friends list, adding and removing friends)
- set up USER controller middleware functions for getting user, getting user friends, and adding/removing friends.
- set up POST route for picture in index file to use Multer upload.
- create postRoutes in /routes/posts.js
- set up Mongoose model for Post and import it into post controllers
- set up POST middleware controllers (createPost, getFeedPosts, getUserPosts, likePost) in /controllers/post.js

*Backend is now complete with necessary routes.*

### Frontend
Frontend folder set up will be organized by scenes(homepage, profile page, login page, global navbar, and widgets), reusable components, and state for redux and toolkit configuration.

##### Set up React boilerplate and above folders and files.

##### set up jsconfig file to simplify file directories by starting from src

##### Set up routes in App file

##### Set up Redux Toolkit for state management. 
- Start by creating slice for mode, login, logout, updating friends, post, and posts. 
- Import this authReducer into root index file, create store, and wrap app with provider passing in store data. 
- Configure React Persist here with your store to store data to local storage.

##### Next create theme file in src directory and customize theme. 
- Configure theme in App.js and pass in theme using Theme Provider. Use Css baseline to reset CSS.

##### Create reusable flexBetween CSS component in components folder.

##### Navbar:
- Set up Navbar to navigate to home when clicking logo; Have light and dark toggle; Search bar; Icons for messages, notifications, and help; Dropdown with user's name and logout button.
- Make navbar responsive for mobile and desktop perfomance. 

##### Login:
- create an index and form folder.
- the form folder will use Yup to create schemas for register and login that ensure data validation. This file will also hold initial state values for register and login. Further, our forms and input types will be validated and managed by Yup and Formik. From this frm file, we can make API calls to our server to launched register and login. Register will create user in DB with Mongoose and navigate back to Login interface. Loggin in will dispatch setLogin reducer from redux toolkit and launch login functions. Mongoose will find email in DB and navigate to home page if token is returned, authenticating the user. This token will also give access to profile page.

### Authentication and Authorization is now complete.

#### Widgets for front end experience
- set up user widgets, widget to post content, wdget to display posted content,


## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).


