---
layout: post
tittle: "questions 2015-12-23"
date:   2015-12-23 17:52:39 +0530
categories: jekyll update
---

1.Caching? (http://www.tutorialspoint.com)

Caching (pronounced “cashing”) is the process of storing data in a cache.
A cache is a temporary storage area. For example, the files you automatically request by looking at a Web page are stored on your hard disk in a cache subdirectory under the directory for your browser. When you return to a page you've recently looked at, the browser can get those files from the cache rather than the original server, saving you time and saving the network the burden of additional traffic.
Caching in rails
Three types of caching techniques: page, action and fragment caching. Rails provides by default fragment caching. Dynamic web applications usually build pages with a variety of components not all of which have the same caching characteristics. In order to address such a dynamically created page where different parts of the page need to be cached and expired differently, Rails provides a mechanism called Fragment Caching.In order to use page and action caching, you will need to add actionpack-page_caching and actionpack-action_caching to your Gemfile.
To start playing with caching you'll want to ensure that config.action_controller.perform_caching is set to true, if you're running in development mode. This flag is normally set in the corresponding config/environments/*.rb and caching is disabled by default for development and test, and enabled for production.
config.action_controller.perform_caching = true



2.What is rack? (http://www.tutorialspoint.com)

A framework, typically with rails, bars, hooks, or pegs, for holding or storing things.Rack provides a minimal interface between webservers that support Ruby and Ruby frameworks. 
To use Rack, provide an "app": an object that responds to the call method, taking the environment hash as a parameter, and returning an Array with three elements: 
The HTTP response code 
A Hash of headers 
The response body, which must respond to each 



3.What is session and cookies in rails? (http://guides.rubyonrails.org/)

Sessions are important as they provide with useful information regarding the customer and different server side information. 
Cookies on the other hand use the store information that are stored on the client side platform or related to the browser. 
Sessions are required to store the information regarding the user’s information and the actions that he will take only. 
The session is given as: session [:user] = “Rohit”. 
The session remains till the browser till the information is getting stored and the browser is getting closed by the user for the same. 



4.How cookies and session handles in rails? (http://guides.rubyonrails.org/)

Rails uses a cookiestore to handle sessions.What it means is that all the informations needed to identify a user's session is sent to the client and nothing is stored on the server. When a user sends a request, the session's cookie is processed and validated so rails, warden, devise, etc. can figure out who you are and instantiate the correct user from the database.
Like I said earlier, cookies are how server can remember who you are from one request to another. Everytime you send a request to a server, you send every cookie you have for that domain. A session cookie is signed and encrypted hen sent to the browser.



5.Types of callbacks in ruby? (http://guides.rubyonrails.org)

Creating an Object
before_validation 
after_validation 
before_save 
around_save 
before_create 
around_create 
after_create 
after_save 
after_commit/after_rollback 
Updating an Object
before_validation 
after_validation 
before_save 
around_save 
before_update 
around_update 
after_update 
after_save 
after_commit/after_rollback 
Destroying an Object
before_destroy 
around_destroy 
after_destroy 
after_commit/after_rollback 




6.What does git push -u mean? (https://git-scm.com)

"Upstream" would refer to the main repo that other people will be pulling from, e.g. your GitHub repo. The -u option automatically sets that upstream , linking the repo to a central one. That way, in the future, Git "knows" where we need to push to and where we  want to pull from, so we can use git pull or git push without arguments.



7.What does git push -f mean? (https://git-scm.com)

To force a push to only one branch, use a + in front of the refspec to push (e.g git push origin +master to force a push to the master branch). See the <refspec>... section above for details. This option is equivalent to the <repository> argument. If both are specified, the command-line argument takes precedence.



8. How to use bitbucket and github at the same time for one project (stackoverflow)

You can use multiple remote repositories with git. 
But you'll have to push separately into 2 of your remotes I believe.
For example, if your project currently points to github, you can rename your current remote repository to github:
$ git remote rename origin github
You can then add another remote repository, say bitbucket:
$ git remote add bitbucket git@bitbucket.org:your_user/your_repo.git
Now in order to push changes to corresponding branch on github or bitbucket you can do this:
$ git push github HEAD
$ git push bitbucket HEAD
Same rule applies to pulling: you need to specify which remote you want to pull from:
$ git pull github your_branch
