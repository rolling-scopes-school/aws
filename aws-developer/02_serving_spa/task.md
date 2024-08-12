# Task 2 (Serve SPA in AWS S3 and Cloudfront Services)

## Prerequisites

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

## Manual deployment evaluation criteria (70 points)
_For those, who use AWS website to manually create **S3 Bucket**, place project files from `dist` folder, configure all necessary Policies, and create **CloudFront**_  

Your _PullRequest_ will contain description of the work done:

- **30 points** - _(if this work alone is done)_ `S3 Bucket` was created and configured properly. The `Application` was uploaded to `S3 Bucket` and is available over the Internet, but the rest of the requirements are not done.  
> _(e.g.: only a link to S3 bucket/website is provided and it opens an Application – you should evaluate as 30)_


- **40** - _(In addition to the previous assessment)_ – a `CloudFront` distribution is created and configured properly; the `Application` is now served with `CloudFront` and is available over the Internet via `CloudFront` URL.  

> Due to changes in your `S3 Bucket`:  
> - `CloudFront` URL is provided and opens a static website.  
> - `S3 Bucket` URL shows **403 Access Denied error**.

NOTE: _If this one is done, this means you acquire score points for both.(70 points)_


## AWS CDK deployment evaluation criteria (+30 points) _(optional)_

- **30** - `S3 Bucket` was created, `Application` was deployed, `CloudFront` Distribution and Invalidation created and configured by using `AWS CDK`. The `Application` can be built and deployed by running `npm` script commands.  
> - `PullRequest` contains:
> - `CloudFront` URL is provided and opens a static website 
> - `S3 Bucket` URL shows **403 Access Denied error**
> - description of work has been done

**NOTE**: YOU SHOULD WORK IN YOUR OWN FORKED REPOSITORY, NOT IN COMMON

## Pull Request Description Template

The following should be present in PR's description field:

1. What has been done?  

Example:
```
  - [x] Service is done, but FE is not working...
  - [x] Additional scope - webpack, swagger, unit tests
```
2. All necessary links as per task requirements...
