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

Clean up
--
Let's break a few things and then get them working again.
__Views__ are HTML templates that Express will render on the server side and then pass to the web browser.
We're going to let Angular do that work, Express will only serve raw data in JSON format via an API URL so we can
drop the views, templates, routes and related packages.

This commit has removed most of the templating and page serving. If you `npm start` this application and
visit [http://localhost:3000](http://localhost:3000) you'll get a nice error to debug.
