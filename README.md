# Angular-notes
Working notes for an Angular, Node, Express application

Introduction
--
Single page applications need to be served from somewhere, usually there are some server side resources or processing that must be performed. One option is to combine Angular on the client side with Express.js on the server. The benefit is only needing to program in one language, and make use of common libraries and code structures.

While tutorials for Angular exist, few explain how to set up the server side. On the other hand, there are many complete stack examples which often incorporate a vast number of different frameworks and utilities. Learning the capabilities and interactions of these systems is generally impractical without previous experience.
Many of the samples available on the web represent weeks of set up, they never mention the debugging and refactoring that went into making them work.

The purpose of this repository is to document setting up a full application framework without doing any _magic_. The introduction of each new library and configuration file will come with an explanation. When things don't work the reason why will be documented.

Setup
--
The project with be initialised in the bb (barebones) folder. Rather than start completely from scratch, we can use the [express generator] (http://expressjs.com/en/starter/generator.html)

To set up the project you have to install node.js and learn the basics of the NPM package manager, in particular how to install a global package and how package.json is interpreted by npm.

Install the express generator and create a new project by typing `express bb`

This will generate a basic express application. `cd` into the bb folder and run `npm install`

npm will look for the package.json file in the current folder and retrieve the packages listed within package.json and install them in a node\_modules folder. These are the libraries that allow your application to run. There are many dependencies within these libraries and this results in two issues. Firstly, it's possible for a particular version of a library to break your application. Google 'semver' for information on what package version number mean. Secondly, in Microsoft Windows the large number of deeply nested folders is incompatible with the built-in file commands making it difficult to work with the node\_modules folder.

Despite the issues with package management this is an established way to provide a rich programming environment with minimal effort.
