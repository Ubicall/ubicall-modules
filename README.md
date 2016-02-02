# ubicall-modules
> Details about Ubicall architecture, technologies and subsystems used to deliver ubicall to you

Microservices architecture is a trend this days and we in ubicall are very interesting in integrate it in all component we use. usually we separate front end and back end projects/teams, and every one has his plan of deployment.
build our stack up on technologies like nodejs, angularJs, mongodb, BDD, travis-ci, docker, mysql, php, redis.

Tools which are shared a cross all stack include gruntjs, jshint, jsbeautify, git

We trust nginx as a web server for hosting all our statics content and as load balancer for all our applications nodes.

**how we add a feature :**
 * it all start with github issue (with custom tags)
 * scope of change is determined
 * choose the release date
 * feature/fix branch is created
 * developer open a pull request (if test pass, fast code review will done)
 * beta release date is determined (deploy in test server)
 * merge pull request to stable branch (which will be fetch and deployed with next release date)
 
**components behind this all :**
 * node-red fork
  > we forked [node-red](https://github.com/Ubicall/node-red), A visual tool for wiring the Internet of Things, and tweak it a little bit by build easily configurable components used to simulate UI, call web service and take actions based on a decision.
  
  **built with:**
   * back end : nodejs, mongodb, oauth 2.0, promises, travis-ci, BDD, gruntjs
   * front end: d3.js, jquery, bootstrap

---

 * web service
  > our back end core, which mange and connect all ubicall stack.
  
  **built with:**
   * nodejs, oauth 2.0, promises, mongodb, redis, BDD, travis-ci, docker, gruntjs

---
 
 * ubicall cache
  > ubicall cache layer build with redis (not done yet)
  
  **built with:**
   * nodejs, redis
   
---

 * ubicall oauth
  > OAuth 2.0 layer, on top of all back end components in our stack.
  
  **built with:**
   * nodejs, expressjs, passport, oauth2orize, JWT, mongodb, mysql, gruntjs

---   

 * ubicall conf
  > one place to configure all ubicall stack, contain json style of configuration and secret credentials for our stack, it contain init-ubicall script, which is responsible for initializing any blank linux machine to minimum requirement for running our stack.
  
  **built with:**
   * nodejs, docker, bash
   
---

 * ubicall agent
  > main screen for call center agents, used to find history of their calls and available clients requesting a call, some reports (if you an admin it will be a fully one) and main feature is making calls using rtmp/flash (working integrate WEBRTC)
  
  **built with:**
   * angularJs 1.x, bootstrap, flash, bower, gruntjs
   
---

  * ubicall bower dependencies
   > use bowerjs to help use with our front end libraries, specially ones shared a cross all front end applications, this libraries are hosted in our cdn.
   
   **built with:**
    * bower, gruntjs
    
---  

  * ubicall embedded widget
   > if you a client this is fast and easy way it integrate with us, this is our web widget, that will appear in your site by adding two lines of javscript, changes you made in designer will appear here instantly.
   
   **built with:**
    * nodejs, jquery, cheerio
    
---

  * native mobile applications
  
   > a native application with same content as your widget, available for both ios and android
  
---
 
 
 * ubicall admin
  > an admin interface for adding agents, manging reports and configure most parts of stack
  
  **built with:**
   * php, bootstrap, mysql, mongodb
  