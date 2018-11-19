# FriendFinder

## Table of Contents 
1. [Overview](#overview)
2. [Technologies](#technologies)
3. [Local Installation](#installation)
4. [Code Explain](#display)

<a name="overview"></a>
## Overview 
FriendFinder a compatibility-based application -- basically a dating app. This full-stack site will take in results from users' surveys, then compare their answers with those from other users. The app will then display the name and picture of the user with the best overall match. 

Check out the app at: https://pacific-eyrie-13865.herokuapp.com/

<a name="technologies"></a>
## Technologies

* JavaScript/jQuery
* Node.js
* MySQL database
* Node packages: Express, Path

<a name="installation"></a>
## Local Installation

Download the files to your computer from https://github.com/hyxhuynh/FriendFinder


<a name="display"></a>
## Code Explain
* Survey contains 10 personality questions. Each answer is on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.
* `server.js` file sets an initial port and set up Express app to handle data parsing
* `htmlRoutes.js` includes two routes:

    * A GET Route to `/survey` which displays the survey page.
    * A default, catch-all route that leads to `home.html` which displays the home page. 

* `apiRoutes.js` file contains two routes:

    * A GET route with the url `/api/friends`. This will be used to display a JSON of all possible friends.
    * A POST routes `/api/friends`. This will be used to handle incoming survey results. This route will also be used to handle the compatibility logic. 

* Initial friend data-objects are set up in `friends.js`.
* To determine the user's most compatible friend, the absolute diffrence between the user' total scores and each friend's is calculated. This is done using `Math.abs()`. The friend with the smallest absolute difference is the most compatible friend to the user. 
* Once the most compatible friend is found, a model with the name and picture will displayed. 
* Error-checking mechanism is in place if command is invalid or missing.