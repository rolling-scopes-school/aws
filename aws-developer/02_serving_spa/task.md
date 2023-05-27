# Task 2 (Serve SPA in AWS S3 and Cloudfront Services)

## Prerequisites

---

- **Install** the latest version of AWS CDK (https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html)
- **Configure** credentials for AWS to make them accessible AWS CLI & CDK
- **Fork** React Shop single page app from https://github.com/rolling-scopes-school/nodejs-aws-shop-react
- **Install** dependencies
- **Check** if everything works for you

## Architecture

Find the entire program architecture: [here](../Architecture.pdf).

<details>
  <summary>Task Focus</summary>

  The following image provides more info about task focus.

  <img src="./module_focus.png" />

</details>

## Tasks

---

### Task 2.1

**Manual Deployment**

1. In the AWS Console **create** and **configure** an S3 bucket where you will host your app (follow instructions in training materials).
2. **Build** and **manually upload** the MyShop! app to the created S3 bucket. **Check** if the app is available through the Internet over `http://{your-bucket-name}.s3-website-{aws-region}.amazonaws.com` .
3. **Create** a CloudFront distribution for your app as it was described in training materials. **Check** your S3 bucket policy changes. **Check** if the app is available through the Internet over given CloudFront URL.
4. **Make** some minor but visible changes in the app, **build** and **upload** them to your bucket, and create CloudFront distribution invalidation.

### Task 2.2

**Automated Deployment**

1. **Add** and **configure** S3 bucket creation and website deployment using AWS CDK. Add necessary npm script(s) to build and deploy your app from your machine in an automated way. **Check** if everything works correctly for you.

_NOTE: After uploading an application's build to the S3 bucket you need to manually create a CloudFront invalidation._

2. **Destroy** the created AWS infrastructure (S3 bucket and CloudFront distribution) from the previous part and steps. **Make sure** nothing is left.
3. **Add** and **configure** CloudFront Distribution and Invalidation using AWS CDK. **Add** necessary npm script(s) to build, upload to your S3 bucket, and invalidate CloudFront cache from your machine in an automated way. **Check** if everything works fine and all changes appear on the Web.

_NOTE: Now that you have this plugin you don’t need to manually create CloudFront invalidations any more._

### Task 2.3

1. Store the links to CloudFront URL and S3-website in README.md file.
2. Commit all your work to separate branch (e.g. `task-2` from the latest `main`) in your own repository.
3. Create a pull request to the `main` branch.
4. Submit link to the pull request to Crosscheck page in [RS App](https://app.rs.school).

## Evaluation criteria (70 points for covering all criteria)

---
- S3 bucket has been created and configured properly. The app has been uploaded to the bucket and is available though the Internet. Nothing else has been done.
  _(Link to S3 bucket/website is provided. There is no Pull Request in the YOUR OWN frontend repository.)_
- In addition to the previous work a CloudFront distribution is created and configured properly and the site is served now with CloudFront and is available through the Internet over CloudFront URL, not S3-website link (due to changes in bucket’s policy...).
  _(Link to CloudFront website is provided. S3-website shows 403 Access Denied error. There is no Pull Request in the YOUR OWN frontend repository.)_

## Additional (optional) tasks

---
- **30** - S3 bucket creation, website deployment, CloudFront Distribution and Invalidation added and configured by using AWS CDK. The app can be built and deployed by running npm script command.
  _(Link to CloudFront website is provided. PR with all changes is submitted in the YOUR OWN frontend repository and its link is provided for review.)_

NOTE: YOU SHOULD WORK IN YOUR OWN FORKED REPOSITORY, NOT IN COMMON

## Description Template for PRs

---

The following should be present in PR's description field:

1. What was done?

   Example:

```
   Service is done, but FE is not working...

   Additional scope - webpack, swagger, unit tests
```

2. Link to FE PR (YOUR OWN REPOSITORY) - ...
