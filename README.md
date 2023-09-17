# Secrets Web App Documentation

<p>This documentation provides an overview and explanation of the Secrets web application. Secrets is a simple web app that allows users to share their secrets anonymously. It is built using Node.js, Express.js, MongoDB, and Passport.js for authentication. The app also supports Google OAuth 2.0 authentication.</p>

## Table of Contents
- Project Structure
- Getting Started
- Authentication
- Routes
- Dependencies

## Project Structure

<p>The project follows a standard structure for a Node.js web application:</p>
- <b>app.js</b> : The main entry point of the application.
- <b>views</b> : Contains the EJS templates used for rendering pages.
- <b>public</b> : Stores static assets like CSS and client-side JavaScript files.
- <b>models</b> : Defines Mongoose schemas for the User model.
- <b>package.json</b> : Lists project dependencies and provides basic project information.


## Getting Started
1. <b>Clone the Repository</b> : To get started, clone this GitHub repository to your local machine.
2. <b>Install Dependencies</b> : Run the following command in the project root directory to install the necessary dependencies:
   ```
   npm install
   ```
3. Environment Variables: Create a `.env` file in the root directory of the project. Add the following environment variables and replace them with your own values:
   ```
   CLIENT_ID=your_google_client_id
   CLIENT_SECRET=your_google_client_secret
   ```
4. Database Configuration: Ensure you have a MongoDB server running. Update the MongoDB connection URL in `app.js`:
   ```
   mongoose.connect("mongodb://localhost:27017/userDB", { useNewUrlParser: true });
   ```
5. Start the Application: Run the following command to start the server:
   ```
   npm start
   ```
6. Access the App: Open your web browser and navigate to http://localhost:3000 to access the Secrets web application.

## Authentication
The Secrets web app supports both local authentication (using a username and password) and Google OAuth 2.0 for authentication.

- <b>Local Authentication</b>: Users can register with a username and password. Passwords are hashed and stored securely in the database.

- <b>Google OAuth 2.0</b>: Users can sign in using their Google accounts. The app uses Passport.js with the `passport-google-oauth20` strategy for Google authentication.

## Routes
The application defines several routes for different functionalities:

- /home: Displays the home page.
- /login: Displays the login page.
- /register: Displays the registration page.
- /secrets: Displays the secrets page. Only accessible to authenticated users.
- /auth/google: Initiates the Google OAuth 2.0 authentication process.
- /auth/google/secrets: Callback route for Google OAuth 2.0 authentication.
- /submit: Allows authenticated users to submit secrets.
- /logout: Logs out the user.

## Dependencies

<p>The application relies on the following npm packages and dependencies:</p>

- express: A web application framework for Node.js.
- body-parser: Middleware for parsing HTTP request bodies.
- ejs: A templating engine for rendering dynamic content.
- mongoose: An Object Data Modeling (ODM) library for MongoDB.
- express-session: Middleware for session management.
- passport: Authentication middleware for Node.js.
- passport-local: Local authentication strategy for Passport.js.
- passport-local-mongoose: Simplifies Passport.js authentication with Mongoose.
- passport-google-oauth20: Google OAuth 2.0 authentication strategy for Passport.js.
- mongoose-findorcreate: A plugin for Mongoose for simpler model creation.
