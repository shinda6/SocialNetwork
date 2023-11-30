### README
* / - renders the main page that displays posts submitted by all users, in chronological order.
* /login - renders the login page.
* /logout - renders the logout page.
* /register - renders the registration page.
* profile/<username> - renders the user's profile page. 
* /following - renders the page that displays all of the posts by users that the user follows, in chronological order.

* /isfollowing/<username> - returns json file with the isfollowing item set to True/False if the user follows the requested user.
* /countfollowing/<username> - returns json file with the following_count item set to the number of users that the requested user follows.
* /countfollowers/<username> - returns json file with the followers_count item set to the number of users that follow the requested user.
* /follow/<username> - submits a POST request for the user to follow the requested user (if not already).
* /unfollow/<username> - submits a POST request for the user to unfollow the requested user (if not already).
    
* /countlikes/<post_id> - returns json file with the likes_count item set to the number of likes for the requested post.
* /isliked/<post_id> - returns json file with the liked item set to True/False if the user has liked the requested post.
* /like/<post_id> - submits a POST request for the user to like the requested post (if not already).
* /unlike/<post_id> - submits a POST request for the user to unlike the requested post (if not already).

* /iscreator/<post_id> - returns json file with the iscreator item set to True/False if the user is the creator of the requested post.
* /posts - returns query set with posts. Accepts key value pairs: username (will return all posts by the user, if not provided, all posts by all users), start (first post index) and end (last post index). 
* /posts/following - returns query set with the posts by all users that the user follows. Accepts key value pairs: start (first post index) and end (last post index). 
* /countposts - returns json file with the posts_count item set to the number of posts. Accepts key value pairs: username (will return number of posts by the user, if not provided, number of all posts by all users)
* /countposts/following - returns json file with the posts_count item set to the number of posts by the users that the user follows.
* /newpost - submits a POST request to create a new post, with the post text inside request body. 
* /postedit/<post_id> - submits a POST request to edit the requested post (only if the user is a creator of the post). 

### models.py

* User - contains all user information.
* Post - contain all post information.
* Follower - contains following pairs.
* Like - contains users' likes. 

### static (js)

* API.js - front-end API for AJAX requests to the back-end API.
* createElements.js - framework to generate html elements for posts, liked/unfollow buttons etc.
* edit.js - framework to edit posts. 
* follow.js - framework to follow/unfollow other users.
* following.js - front-end framework for '/following' page, that loads posts, pagination etc.
* getCookies.js - collects csrftoken from the templates for POST requests that require csrf key.
* index.js - front-end framework for the main page, that loads posts, pagination etc.
* likes.js - framework to add/remove likes from the posts.
* posts.js - framework that loads users' posts on to the page.
* profile.js - front-end framework for the user profile page, that loads posts, pagination etc.

### templates

* following.html - template for the page that displays all posts by users that the user follows.
* index.html - template for the main page that displays all posts.
* layout.html - layout template for all pages that includes the navigation bar. 
* login.html - template for login menu.
* profile.hrml - template for user profile page. 
* register.html - template for registration.