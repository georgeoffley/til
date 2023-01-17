# Figuring Out The Weird Return

### Project
Work Project

### Date
11/02/2022

### Technology
- JavaScript
- Node
- NPM

### The Problem

The build for the project I was working on failed, and it didn’t make sense to me since the changes had been deployed.

I was trying to get dates that were being randomly generated to land on one specific day of the month.

### The Process

- After making my changes, I looked at the GitHub logs and saw that it had one output before failing, which was just `Error: Build status: FAILED`.
-  So I jumped into the app to see if the dates were still random.
    -   They were not; they were all defaulting to the first of the month
    -   So it looked like my change was still deployed despite the fail message
-  I jumped into the tech channel in slack to ask if there were any other logging resources I could look into to get more information.
- I got some information about the [GitHub Action](https://github.com/aws-actions/aws-codebuild-run-build) that we use for triggering deploys. It dumps the logs from AWS Codebuild into the GitHub Actions log output. So what I was seeing was mostly what I was going to get.
- I also learned from chatting with people that AWS Codebuild uses a `buildspec.yml` file to tell Codebuild what to do.
- After this, I tried logging into AWS to see if I could see what was happening.
- So I went to our project and looked at the logs, and was able to see something a little more descriptive and noticed that the build deployed the API correctly but failed at the frontend build.
	- The message was a similar one I had seen when doing the same thing locally before I was set up with NPM and AWS, so it’s possible that is related.

### Solution
Turns out the project had a long outdated `package-lock.json` file that was being used when building the project. The project was a few months old by the time I had gotten to it, and I was able to clear up the issue by generating a new `package-lock.json` file and uploaded that to the repo. Once all the updates were working the project was able to build.


#ProblemSolving