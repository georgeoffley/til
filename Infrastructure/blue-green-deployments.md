# Blue Green Deployments

Have two identical versions of the app, the stable (old) version, and the new version with the latest updates.

One strategy for this is manual deployments where you can create an additional staging set up to QA new features and test the latest build. Once QA is completed you can deploy to production.

Great for CI/CD set ups as much of this can be automated.

Needed updates can be cherry picked into the new build and regressions can be handled by rolling back to the stable version.

Good Resource: [AWS Blue/Green White paper](https://d1.awsstatic.com/whitepapers/AWS_Blue_Green_Deployments.pdf)

#Infrastructure