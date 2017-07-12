# **Teekay Culture Microsite** #
## [lifeatteekay.com](http://lifeatteekay.com/)
## React/Redux SPA with Wordpress CMS ##
- - - - - - - - - - - - - - - - - - - - -

For this project we were tasked with building a SPA, for a quick and immersive user experience, while using Wordpress as a CMS so the client could easily manage posts, and site settings.

We spend time planning data flow in the App, reusable components to use and how to implement Search/Filter functionality.

The first proof of concept iteration was solely React, but after a short while we decided to work with Redux to manage data/functions so components updating more easily with post data.

## Technology used 
* Wordpress CMS
* WP-API
* Axios
* React 
* React Router
* Redux
* Webpack
* npm
* yarn

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).

## Development
In this project, development happens on you local machine, and runs at localhost:3000. 

We decided to separate the frontend app from the Wordpress theme for initial development to breakaway from using our previous structure and utilise a more industry standard practice of feature based branches.

The React App was then included in the theme folder and index.php renders index.html, which is the mount point. The client can still login to /wp-admin and manage posts, settings etc, which is all reflected in the React App
