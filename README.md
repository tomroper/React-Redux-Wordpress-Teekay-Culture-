# **React & Wordpress SPA Microsite** #
## [lifeatteekay.com](http://lifeatteekay.com/)


![Teekay Home Screen](http://i.imgur.com/eOlV9eH.png "Teekay Home Screen")

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

## Challenges
#### Wordpress API 100 post limit
The Wordpress API will only allow 100 posts to be requested in a single API call, this is to avoid large websites with hundreds or thousands of posts to be overburdened with large requests.

We had 2 solutions for this problem, the first was to chain API calls, so that after the initial 100, if there were still posts in the total post count, then run a second API call, until the post count function returned false. 
This was fine until the load time of the app started to slow while waiting for all the API calls to resolve.

Our solution for this problem was to initially load 10 posts, and then when the user clicks 'Load More', run an API call for the next 10, and so on. This made the load time of the app much quicker and enables us to load all posts.

#### Predictive Search & Filtering while not having all posts
This ties into our solution for the first problem. In order for the user to be able to search properly, all post data needs to be available in the Search componenet. As we're only initially loading 10 posts, that doesnt give a lot of content to search. 
The solution for this was to offer the Search component a custom API endpoint that contains just the ID, Post Title, Categories and Tags.
This then allows the predictive search to offer results as well as having the information to make requests for the search results.

#### Routing to single posts
The client wanted users to be able to share single posts, for sharing/social media. This meant that url.com/single-post-name had to resolve to the correct post component and load the correct data.
We used React Router and a function in App.js to determine whether the user had inputted a single post url, and to fetch the data while loading the correct component with the post data.
