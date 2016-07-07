Serve a basic API
==
Let's refactor the existing Express routing to serve up an API rather than users, and split the server and client side functionality.

Move the server side to its own folder.
==
Create a `server` folder under `bb`. Move `app.js` and the `routes` folder into `server`.
Fix up the paths so everything still functions.

Create a client folder to serve the client side application.
==
The Angular application will run entirely on the client side. As far as the server is concerned it's just a static resource.
We can rename the redundant `public` folder to `client` and change the static route defined in `app.js`: `app.use(express.static(path.join(__dirname, 'public')));`.

Before we install Angular, we'll introduce TypeScript in [Step 3](https://github.com/wistonia/Angular-notes/blob/master/Step3.md).