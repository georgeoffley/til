# Figuring Out The Weird Return

### Project
Work Project

### Date
11/02/2022

### Technology
- JavaScript
- Vue
- Nuxt

### The Problem

So I was making changes to the API code for a monolith application that has and API and a frontend setup. However, when I launched the app the changes where not reflected.

### The Process
1.  I cloned the repo and tried starting everything reflected in the notes.
2.  I was getting error after error and was blocked.
3.  After reaching out to some people to get my dev environment set up right I was good to try again.
6.  However, whenever I made a change to the API, it was not reflected in the local server.
7.  I tried adding console messages in the code block for adding residents that I was working in, and nothing.
8.  Then I searched for that block elsewhere in the project and found it in the handler function for it.
9.  So I added another console message to see if it came up when I called the API, and nothing.
10.  Then I went into the client directory and noticed the Vue project, which served as the frontend, so I put a console message there to see if it came up. And I was able to see the console message in the browser. So I established that the frontend was updating but not the API.
11.  So I looked at the API endpoints being called in the client and saw them, and they looked OK. However, I noticed the endpoint prefix was being populated by a call to the app config.
	- This project uses [Nuxt](https://nuxtjs.org/), which is a framework for standing up Vue apps quickly. The app config is a setup file we can import into the app.
1.  So I created a new console message to show the config prefix, and it revealed that the API endpoints that the client app was calling were the staging endpoints and not the local endpoints from the local API server.
2.  So, I needed to understand how the start command for the client frontend worked in this app.
3.  I looked into the `package.json` file and noticed that it was running `[nuxi` commands]([https://v3.nuxtjs.org/api/commands/generate/](https://v3.nuxtjs.org/api/commands/generate/)) which is a library for building out Vue apps. It was also running a [dev command](https://v3.nuxtjs.org/api/commands/dev/) which starts a dev server.
    1.  So this command was packaging up the API endpoints for the app and then starting the dev server.
4.  Next, I looked to see where the configuration was set and where you would set configuration options. In this case where the APIs should be pointing.
5.  Eventually, I found it in the `nuxt.config.js` file, where the configuration for Nuxt is. Nuxt apparently works out of the box, but you can override settings with a `nuxt.config.js` file present.
6.  I found that this config file had a setting parameter with the same name as what was being pulled from the Vue app.
7.  I also noticed that this setting was pointing to the APIs for the staging environment and that there was a commented-out line with the APIs pointing to the local host setup. It had a note which detailed the API command, and I inferred that this should be commented out when doing local work.
8.  So, I un-commented the local URL and commented out the staging URL. Suddenly I was able to see my changes in the local environment.
9.  I confirmed console messages were coming up in the server logs to be sure.


### Solution
The issue was that we were setting the API URLs using the `nuxt.config.js` file and importing them into the scripts for the app. The URL was set statically, and the app had no way to tell when I was running everything locally or in a deployed environment. 

I refactored it so that we could easily switch from our staging environment to a local environment. 

#ProblemSolving