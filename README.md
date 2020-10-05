# Basic React with Redux App with JWT authentication

This is a barebones implementation of authentication with JWT in a React with Redux App.
Out of the box, it contains the following:

- Profile Page
  * A very dumb and boring profile page which is a protected route
  * sign out button
- Protected Routes
  * redirects any unauthenticated attempts to protected route to the login page
- Sign Up Page
  * lists errors on page if present in API response
  * redirects user to the profile page
- Log In Page
  * lists errors on page if present in API response
  * redirects user to the profile page
- Sign Out Button (component)
  * a very ugly, but useful sign out button.
  * reinitializes Redux state to undefined
  * removes JWT token from localStorage
  * redirects user to login page

The following libaries were used for the following concerns:

- Basic React Project: _create-react-app_
- State Management: _redux_
- Connect Redux to React: _react-redux_
- Client Side Routing: _react-router-dom_
- Async Middleware: _redux-thunk_
- HTTP Requests: _fetch_
- JWT storage: localStorage

NB: Due to security implications (XSS, CSRF, etc.) and costs/benefits of using localStorage, sessionStorage, and Cookies, it is very important that you consider well how to handle your JWT token once the client receives it. This implementation is simply here to help you see how you could have authentication set up on the frontend, but you are responsible for your app's security and the security of your users' data. The current implementation can be attacked by XSS due to the use of localStorage. Depending on your use case (e.g., an app which does not persist highly sensative data / give access to money), this could be acceptable (but I highly doubt it, because hey, what app doesn't have senative data?). Nevertheless, just be forwarned and do NOT use this structure out of the box. You have to modify it to create a secure environment for your users.

My metaprogrammatic implementation of the creation of thunks with redirects could be very helpful for anyone trying to understand how these requests work, expecially when there is a redirect involved.
Also, anyone trying to setup protected routes on the frontend might also benefit from looking at my ProtectedRoute component. Although react-router-dom has great documentation, I believe that this implementation is more elegant and easier to understand.

If this repo helps you out, please star it and follow me on Github!

Thanks,
William

# create-react-app boilerplate:

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `yarn build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
