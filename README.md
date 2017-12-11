# CS4320Group Mizzou Meme Maker
#### A Sarah Twomey, David Emily, Landen Eagan, Jason Kayser & Alex Lasley Collaboration

![homepage](https://github.com/davidemily/CS4320Group/blob/master/mizzouMemeHomepage.png)

[MizzouMemeMaker Homepage](https://mizzoumememaker.com)

[Bot Github Repo](https://github.com/jpk2f2/MemeZouBot)

[Website Github Repo](https://github.com/jpk2f2/MemeZouSite)

[Project's Axosoft](https://cs4320groupproj.axosoft.com)

[Project Video](https://www.youtube.com/watch?v=o4sJaqznO0k)

# Project Title

The Mizzou Meme Maker was made by Mizzou students for Mizzou students to fill the need for dank Mizzou memes.

## Getting Started

For this project, we reserved the domain https://mizzoumememaker.com . The website gives an option to choose from a series of meme templates or an option to include your own picture. The website provides a box to enter a title, which will used as the file name if you choose to save it locally or the title of the Reddit post if you choose to post it to Reddit. The prompts for Top Text or Bottom Text will begin to put the text on the image. The buttons at the bottom give you the options for what to do with the photo.

### Prerequisites

This project utilizes Canvas so HTML5 is required to utilize the meme maker. In practical terms this 
means you should use an up to date browser.

### Installing

The Mizzou Meme Maker does not require any installation of software as the site is hosted on our server.

## Built With

* [Javascript](http://www.javascript.com)
* [PHP](https://www.php.net)
* [MariaDB](https://mariadb.org)
* [Domain.com](https://www.domain.com)
* [Bootstrap](https://getbootstrap.com)
* [HTML5](https://www.w3.org/TR/html5/)

## Why We Chose What We Did
#### Javascript
We chose Javascript due to the ease of the language and the information on it. Both IMGUR and Reddit have easy-to-read documentation on utilizing their API with Javascript. We were also able to find code on how to prompt the user to save locally using Javascript by using online resources. 

#### PHP
PHP was chosen for the website in order to interface with the database. All of our members had experience with PHP through the Web Development and Database course, so it made sense to use a language we were familiar with.

#### MariaDB
MariaDB was chosen for several reasons. The first is that it is open source, which is something our team likes to support where possible. We also have experience using MariaDB, which made setting up a database fairly painless.  

#### Domain.com
The reason for using Domain.com as our domain provider is because the company sponsored Tiger Hacks so our members had free trial coupons. As the website is hosted from one of our member's servers, we did not use much of their hosting services.

#### Bootstrap
Bootstrap was used to style our website because of how easy it is to use and to find resources. 

#### HTML5
MizzouMemeMaker relies on HTML5's Canvas. We had originally planned to use the PHP GD library, but Canvas was much easier to work with.

## Problems & Solutions

#### How to put text on the image
The issue of putting text on an image is one that none of us ran into before. The original plan was to use the PHP GD library but the documentation was rough and I've never been a fan of PHP. During the research into the PHP, we found online resources that pointed to using Canvas. We decided to go this route as Javascript is much friendlier than PHP and many browsers today utilize HTML5.

#### How to integrate Reddit
Getting the website to work with Reddit's API was one of the main problems of the site. We had originally planned to use Python but, due to time restraints and ease of testing, switched to Javascript to get a working front end product. Luckily, there existed examples on using the Reddit API with Javascript. We ended up choosing [Snoowrap](https://not-an-aardvark.github.io/snoowrap/snoowrap-v1.js) to ease some of the problems with interfacing with the API. 

Another issue with Reddit is it requries a static link to the image (Meme) in order to make a thread. This issue led us to also using Imgur's API, to host the image, and give us the link we needed for Reddit.

#### Integrating Imgur
We needed Imgur to host the images to give us a static, publicly-accessible link to use with the Reddit API. Imgur's website lists how to use the API with different languages, so we found the one for Javascript. The Imgur API is locked down with an API key so we had to list what our web project did and apply for approval to use the API. After approval, we simply used the Javascript code given to us and input our team's key information.

#### Dynamic website using database
One issue we had was linking the website to the database. Quite a few hours were spent attempting to get it to work, with no success. In the process it also broke other parts of the site. I was able to solve the issue after moving a copy of the site to a linux container on my own server at home, where it worked. This led to the realization that the php package for sql support was not installed on our live server, which was quickly remedied. This is a textbook example of why you should not make assumptions, but should check every step involved in an issue.

#### Placing text on image pulled from server
The original text overlay was created before the addition of the php, and therefore to ease development time it was decided that we would use the same javascript logic for images pulled from the server. In order to do this I setup the javascript to pull the image from the server according to the existing image they selected from the dynamic list. This led to two issues. The first is that it did not properly reformat images that were pulled down. The second issue involved the function and logic that adds the text overlay, as doing so caused odd behaviour that applied the text multiple times and did not erase it when the text was removed. This all occured during our final sprint, and although we spent a fair amount of time troubleshoting it, we were not able to fix it. We were able to gain an approximate understanding of its cause, and believe that to fix it would require an entire remake of the logic for adding text to pictures. We would likely need an additonal sprint, largely dedicated to removing that code and preferably rewriting it in php in order to remove the load from the user. Due to a lack of time, those changes will be outside the scope of this project. 

#### Team collaboration on the server
Development took place on a Fedora 26 server due to ease of development on GNU/Linux platforms and availability of modern features and recent software packages on the Fedora distribution.

We used Apache's userdir module to provide each team member an independent document root for their current development branch.

For deployment from GitHub to the production environment we configured a repo with `git config core.sharedRepository group`, used the `setgid` bit, and gave each user account the same primary group and `umask 002`. The combined effect of these options is to allow any of the team members to perform git operations in the main directory of the web server.

#### Securing the server
We chose to deploy a Let's Encrypt certificate with the [Certbot](https://certbot.eff.org/) utility because it has no monetary cost. We took up-to-date advice from Mozilla's [configuration generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/) on ciphers to use.

## Contributors

Sarah Twomey, David Emily, Landen Eagan, Jason Kayser & Alex Lasley

## License

No license
