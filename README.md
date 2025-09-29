# Node.js Authentication System

This project contains a complete authentication system using Node.js, Express, and MongoDB. It includes features like sign up, sign in, sign out, password reset, and social authentication (Google). The project is structured to be scalable with separate components for models, controllers, and routes.

## Live Site
[Click here](https://nodejs-authentication-system-l2pu.onrender.com/user/signin) to visit the live site.

## Features Implemented
- **Sign-up with Email**: Create an account using your email and password.
- **Sign-in**: Log into your account securely.
- **Sign Out**: Log out of your session.
- **Reset Password**: You can reset your passwords after signing in.
- **Encrypted Passwords**: Passwords are securely stored using encryption.
- **Google Login/Signup**: Sign in or sign up using your Google account.
- **Forgot Password**: Reset your password via email.
- **Password Strength Validation**: Notifications are displayed for unmatching passwords during sign up and incorrect passwords during sign in.
- **reCAPTCHA Integration**: Protects against bot traffic on sign up and login pages.

## Environment Variables

Before running the application locally, ensure you have set up the following environment variables in a .env file located at the root of your project:

1. **PORT**: Specifies the port number the application listens on.
2. **DB_URL**: MongoDB database connection URL.
3. **CLIENT_ID**: Google OAuth client ID.
4. **CLIENT_SECRET**: Google OAuth client secret (sign in with Google).
5. **CALLBACK_URL**: Google OAuth callback URL after successful authentication.
6. **EMAIL**: Email address for sending emails.
7. **PASSWORD**: App-specific password or regular password for the Gmail account.
8. **RECAPTCHA_SITE_KEY**: Google reCAPTCHA site key (used on the client-side).
9. **RECAPTCHA_SECRET_KEY**: Google reCAPTCHA secret key.
10. **CLIENT_URL**: URL to redirect after signing in with Google, e.g., "http://localhost:3000/auth/login/success".

Ensure that you have the appropriate values for each variable before running the application.

Example `.env` file:

```plaintext
PORT=3000
DB_URL=mongodb://localhost:27017/your-database-name
CLIENT_ID=your-google-client-id
CLIENT_SECRET=your-google-client-secret
CALLBACK_URL=http://localhost:3000/auth/google/callback
EMAIL=your-email@gmail.com
PASSWORD=your-app-specific-password
RECAPTCHA_SITE_KEY=your-recaptcha-site-key
RECAPTCHA_SECRET_KEY=your-recaptcha-secret-key
CLIENT_URL=https://nodejs-authentication-system-l2pu.onrender.com/auth/login/success
```

### Setting up Environment Variables:

1. **Google OAuth Setup**:
   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project or select existing one
   - Enable Google+ API
   - Configure OAuth consent screen
   - Create credentials (OAuth client ID)
   - Copy Client ID and Client Secret to your `.env` file

2. **reCAPTCHA Setup**:
   - Visit [reCAPTCHA Admin](https://www.google.com/recaptcha/admin/create)
   - Register a new site
   - Select reCAPTCHA v2 "I'm not a robot"
   - Add your domain
   - Copy Site Key and Secret Key to your `.env` file

## Folder
  ```text
node-authentication/
├── config/                  # Configuration files
│   └── mongodb.js           # MongoDB configuration
│
├── controllers/             # Controller logic
├── models/                  # Database models
├── routes/                  # Route definitions
├── views/                   # EJS views
├── app.js                   # Express application setup
│
├── public/                  # Static assets
│   └── results/             # Test images used for feature testing   
│
├── package.json             # NPM package configuration
├── README.md                # Project README file
├── .gitignore               # Git ignore configuration
└── .env                     # Environment variables file

```


## Dependencies, Installation and Setup

Follow these steps to run the project locally:

1. Initialize a new Node.js project:
   ```bash
   npm init -y
   ```

2. Install required dependencies:
   ```bash
   npm install express dotenv path mongoose bcrypt express-session express-ejs-layouts ejs passport passport-google-oauth20 nodemailer connect-flash cookie-parser express-validator
   ```

Key dependencies and their purposes:
- `express`: Web application framework
- `dotenv`: Environment variables management
- `mongoose`: MongoDB object modeling
- `bcrypt`: Password hashing
- `express-session`: Session middleware
- `express-ejs-layouts`: Layout support for EJS templates
- `passport`: Authentication middleware
- `passport-google-oauth20`: Google OAuth 2.0 authentication
- `nodemailer`: Email sending functionality
- `connect-flash`: Flash messages
- `cookie-parser`: Cookie handling
- `express-validator`: Input validation

3. Start the server:
   ```bash
   npm start
4. Open your web browser and visit http://localhost:3000 to access the application.

## Testing the Application

After starting the application, you can test the features through the web interface:

1. **Sign Up** (`http://localhost:3000/user/signup`):
   - Fill in the username
   - Enter a valid email address
   - Create a password
   - Confirm the password
   - Complete the reCAPTCHA verification
   - Click "Sign Up"

2. **Sign In** (`http://localhost:3000/user/signin`):
   - Enter your registered email
   - Enter your password
   - Complete the reCAPTCHA verification
   - Click "Sign In"
   - Alternatively, click "Sign In with Google" for OAuth authentication

3. **Forgot Password** (`http://localhost:3000/user/forgot-password`):
   - Enter your registered email
   - Complete the reCAPTCHA verification
   - Click "Forget Password"
   - Check your email for the password reset link

4. **Change Password** (`http://localhost:3000/user/change-password`):
   - Enter your current password
   - Enter your new password
   - Complete the reCAPTCHA verification
   - Click "Change Password"

Note: For all forms requiring reCAPTCHA verification, you must check the "I'm not a robot" box before submitting the form.

## Testing Screenshots (public/results/)

The `public/results/` folder contains screenshots demonstrating key features:

1. `sign-up.png`: Shows the registration page with form validation
2. `sign-in.png`: Displays the login interface with reCAPTCHA integration
3. `after-sign-in.png`: Shows the authenticated user dashboard
4. `change-password.png`: Password change form interface
5. `forget-password.png`: Password recovery request form
6. `login-with-google.png`: Google OAuth login integration
7. `sign-in-with-new-password.png`: Login page after password reset
8. `check-database-mongodb.png`: MongoDB data structure visualization

## Credits

This project was created by [Ravikant Singh](https://github.com/ravikantsingh12). Contributions via issues or pull requests are welcome!

