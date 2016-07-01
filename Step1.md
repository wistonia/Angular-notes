Kick Start the project
==

Despite wanting to keep everything simple, it's always good to have a known good starting point.
The [Mini Node Static Server](https://github.com/wistonia/Mini-node-static-page-server) is too simple,
it doesn't have the structures or dependencies of a typical small project.

The purpose of this project is to create an Angular single page application accessing an API served by Express on Node.js.
The express generator takes a slightly different path providing us a server-based front end to our application with some HTML templating facilities.

We'll remove the components we don't need, but before this test the application actually runs.
`cd` into the `bb` folder and at a command prompt type `npm start`
Open a browser on the same computer and check out [http://localhost:3000](http://localhost:3000)
You should see a welcome page for your Express application. If not, then you'll need to get it working before you go any further.

> `npm start` is looked up by npm in the scripts section of the `package.json` file.

Clean up
--
Let's break a few things and then get them working again.
__Views__ are HTML templates that Express will render on the server side and then pass to the web browser.
We're going to let Angular do that work, Express will only serve raw data in JSON format via an API URL so we can
drop the views, templates, routes and related packages.

This commit has removed most of the templating and page serving. If you `npm start` this application from the `bb` folder and visit [http://localhost:3000](http://localhost:3000) you'll get a nice error to debug:
`Error: No default engine was specified and no extension was provided.`
In the stack trace that follows, amongst the references to various express libraries is a mention of our own app.js and the line number where the error can be found. The line in question calls `res.render`.
The [render](http://expressjs.com/en/api.html#res.render) call depends on the view template engine we just removed.

This bug will manifest itself wherever `render` is called in our application. Looking at the Express API documentation, it looks like we can use `res.send` but we'll have to change the parameters a bit. We'll just respond with some JSON for now.

Once you are happy the application is in a functioning state, you can clean up the unused packages in `node_modules` using the `npm prune` command. This will remove the Jade template engine and associated packages.

On to [Step 2](https://github.com/wistonia/Angular-notes/blob/master/Step2.md).
