# Passport Authentication with GitHub

This project demonstrates how to implement GitHub authentication using Passport.js in an Express.js application. It sets up a basic web application that allows users to log in with their GitHub credentials and manage sessions.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (>= 14.x)
- [npm](https://www.npmjs.com/) (or [yarn](https://yarnpkg.com/))

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/mabass2110/Passport-Github
   cd Passport-Github
   ```

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Set Up Environment Variables**

   Create a `.env` file in the root directory of the project and add the following variables:

   ```
   GITHUB_CLIENT_ID=your_github_client_id
   GITHUB_CLIENT_SECRET=your_github_client_secret
   ```

   You can obtain the `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` by registering a new OAuth application on GitHub's [Developer Settings](https://github.com/settings/developers).

### Configuration

- **Port**: The application runs on port `3000` by default. You can change this by modifying the `PORT` variable in the source code.

- **Session Secret**: The session secret is set to `'codecademy'`. Change this to a more secure value in a production environment.

### Running the Application

Start the application by running:

```bash
npm start
```

Visit `http://localhost:3000` in your browser to see the application in action.

## Routes

- **`/`**: The home page, displays a welcome message and user information if logged in.
- **`/login`**: The login page. Users are redirected here if they are not authenticated.
- **`/account`**: A protected page that displays user account details. Only accessible if the user is authenticated.
- **`/logout`**: Logs the user out and redirects to the home page.
- **`/auth/github`**: Initiates the GitHub authentication process.
- **`/auth/github/callback`**: The callback URL GitHub redirects to after authentication. It handles login success or failure.

## Passport Configuration

- **Strategy**: The GitHub strategy is configured to use the `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` for authentication.
- **Serialization**: User profile data is serialized and deserialized to manage sessions.

## Code Overview

- **Dependencies**: The application uses `express`, `passport`, `passport-github2`, `express-session`, and `express-partials`.
- **Views**: The application uses `ejs` as the templating engine. Views are located in the `views` directory.
- **Static Files**: Static files are served from the `public` directory.

## Security Considerations

- Ensure that `session.secret` is set to a strong, random value in production.
- Avoid exposing sensitive information in your `.env` file or version control.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to open issues or submit pull requests if you have suggestions or improvements.

---

For more details on how to set up and use Passport.js with GitHub, refer to the [Passport.js documentation](http://www.passportjs.org/docs/github/).
