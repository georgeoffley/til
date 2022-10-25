# Setting Up Swyxkit For A New Blog

[Source](https://github.com/sw-yx/swyxkit)

When creating a new blog using swyxkit there are some steps needed when deploying to a Netlify site and a GH repo.

1. You can run all the setup steps as documented.
2. To get this up to a functioning site you need to create a GitHub repo and upload the local site you created in the initial setup steps.
3. Update all the values in the `siteConfig.js` for your stuff.
4. Set up the Netlify site, and choose the repo you just created.
5. Also make sure to create a personal GitHub Access Token and add it to the Netlify site under the `GH_TOKEN` evironment variable.
6. Until I update the code, you also want to make sure that you update the `allowedPosters` variable in the `content.js` file so the site will pick up the issues you create.

#GeneralTools 
	#Swyxkit 