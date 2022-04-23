# Solving Why GitHub Issues Were Not Being Pulled In Swyxkit

### Project
Personal Blog/Blog Entry

### Date
04/21/2022

### Technology
- JavaScript
- [Svelte](https://svelte.dev/)
- [Swxykit](https://github.com/sw-yx/swyxkit)
- [Netlify](https://www.netlify.com/)

### The Problem

The swxykit is a an starter kit for Svelte projects. It is conducive for creating blogs as it utilizes GitHub Issues as a CMS. It has some built in logic for running the GitHub API. It is also easy to set this up to deploy using Netlify. I decided to learn this project to spike some Svelte work, and to dip my toes into another blogging solution.

The project has some pretty simple set up steps but there is some clarity lacking in how to take the project, deploy it on Netlify, set up a repo, and begin your blogging. 

The error I was seeing was that despite going through the set up I was not able to see the GH Issues I opened on the newly create repo show up on the deployed site. 

### The Process

- The first part was getting a repo set correctly. I had set up the project locally and created a new repo after deploying to Netlify. However, the local set up was not linked to that repo. So essentially what I had done was to deploy an instance of the swxykit to Netlify, created a new repo, and that repo had the source code in it but I had not set up anything locally. 
    - I was able to solve this by deleting the sites and repos, setting up a new local instant, creating a GH Repo, publishing my local source code to that repo, and then going through Netlify to deploy the repo again. This worked and I had a site I could add code to.
- I still was not seeing any issues I created show up on the site, only the hardcoded ones that already existed in the project
- I confirmed that all the information on the `siteConfig.js` was correct.
- I went into the GitHub actions that the kit comes with to see if there were issues.
    - I saw the jobs were failing all with the same error message `Error: repository not enabled for code scanning`. No idea what this meant.
    - I Googled a bit at first and couldn't figure out what exactly I was looking for.
    - I went back and edited the permissions for the GitHub token I created and used in Netlify to make sure all permissions were correct. No effect, still getting the error in the workflow jobs.
    - I was able to find [this](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/troubleshooting-the-codeql-workflow) in the GitHub docs and right at the top it mentioned that code scanning if available for all public repos.
    - I thought I had set it correctly, but I went back and checked and the repo was set to private. So I changed it to a public repo.
    - I was no longer seeing those errors and the jobs were passing. However, I was still not seeing the issues I created come up in the blog section of the site I set up.
- I also created a couple more test issues to see if anything changed.
- I then redeployed the site in Netlify, after I added some more issues to see if the site needed a redeploy each time.
- I then went to [swyx's](https://github.com/sw-yx) account to check out the repo he uses for his blog.
    - I noticed that the issues (blog posts as this kit pulls in issues and uses them as blog posts) all have a header with what look like tags. Like this:
    ```
    published: true
    description: ...
    slug: temporal-miami
    ```
    - Seeing this I thought that there was a tag that might have been needed to be present in the GH Issue.
- I began looking through the logic which grabs the issues from the GitHub API, which is the `/src/lib/content.js`.
- I did a search for the word "published" and found it at the top as a constant. 
- I then searched for that constant to see where it was used and found it being used in the logic for the API response.
    - The logic was looking for the `Published` tag which is a GitHub object, not a key value pair in the markdown.
    - It used this tag to determine whether or not to collect the issue and display it in the blog entries. If the tag was not present then the issue was not collected into the blog.
    - So I added a `Published` tag to one of the test issues on my blog. However, I was still not seeing anything come up.
- I continued looking at the logic for pulling in blog posts and saw that the conditional also had a section for looking at the `allowedPosters` array. 
    - This was looking at the GH API response object at the user login attribute and checked the `allowedPosters` array to make sure whoever was posting the issue was included as an allowed poster on the site.
    - I did another search for the `allowedPosters` array and found it right at the top above the `publishedTags` array. It was hard coded to `[swxy]`. I updated my source to include my GH username. I refreshed the site, and say the test issue I created come up on the deployed site.

### Solution

In addition to making sure the site is deployed correctly, hooked up to the right GitHub repo, has all the needed site config info, has an access token; You also have to make sure that your issues are created with the `Published` tag and you need to be included in the `allowedPosters` array in the `src/lib/content.js`. 

I submitted a [PR](https://github.com/sw-yx/swyxkit/pull/55) to change it to an imported setting in the `siteConfig.js` so that we don't have to update it in the source.