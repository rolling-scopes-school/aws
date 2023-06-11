# Task 5 (Integration with S3)

## Prerequisites

---

- The task is a continuation of Homework 4 and should be done in the same repos
- **(for JS only)** Install the latest version of [AWS SDK](https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/getting-started-nodejs.html)
- **(for JS only)** Install the [CSV parser package](https://www.npmjs.com/package/csv-parser)

## Architecture

Find the entire program architecture: [here](../Architecture.pdf).

<details>
  <summary>Task Focus</summary>

  The following image provides more info about task focus.

  <img src="./module_focus.png" />

</details>

## Tasks

---

### Task 5.1

1. Create a new service called `import-service` at the same level as Product Service with a its own AWS CDK Stack. The backend project structure should look like this:

```
   backend-repository
      product-service
      import-service
```

2. In the AWS Console **create** and **configure** a new S3 bucket with a folder called `uploaded`.

### Task 5.2

1. Create a lambda function called `importProductsFile` under the Import Service which will be triggered by the HTTP GET method.
2. The requested URL should be `/import`.
3. Implement its logic so it will be expecting a request with a name of CSV file with products and creating a new **Signed URL** with the following key: `uploaded/${fileName}`.
4. The name will be passed in a _query string_ as a `name` parameter and should be described in the AWS CDK Stack as a _request parameter_.
5. Update AWS CDK Stack with policies to allow lambda functions to interact with S3.
6. The response from the lambda should be the created **Signed URL**.
7. The lambda endpoint should be integrated with the frontend by updating `import` property of the API paths configuration.

### Task 5.3

1. Create a lambda function called `importFileParser` under he Import Service which will be triggered by an S3 event.
2. The event should be `s3:ObjectCreated:*`
3. Configure the event to be fired only by changes in the `uploaded` folder in S3.
4. The lambda function should use a _readable stream_ to get an object from S3, parse it using `csv-parser` package and log each record to be shown in CloudWatch.

### Task 5.4

1. Commit all your work to separate branch (e.g. `task-5` from the latest `master`) in your own repository.
2. Create a pull request to the `master` branch.
3. Submit link to the pull request to Crosscheck page in [RS App](https://app.rs.school).

## Evaluation criteria (70 points for covering all criteria)

---

Reviewers should verify the lambda functions by invoking them through provided URLs.

- AWS CDK Stack contains configuration for `importProductsFile` function
- The `importProductsFile` lambda function returns a correct response which can be used to upload a file into the S3 bucket
- Frontend application is integrated with `importProductsFile` lambda
- The `importFileParser` lambda function is implemented and AWS CDK Stack contains configuration for the lambda

## Additional (optional) tasks

---

- **+15** **(All languages)** - `importProductsFile` lambda is covered by _unit tests_.
  (for JS only) [aws-sdk-mock](https://www.npmjs.com/package/aws-sdk-mock) can be used to mock S3 methods
- **+15** **(All languages)** - At the end of the stream the lambda function should move the file from the `uploaded` folder into the `parsed` folder (`move the file` means that file should be copied into a new folder in the same bucket called `parsed`, and then deleted from `uploaded` folder)

## Description Template for PRs

---

The following should be present in PR's description field:

1. What was done?

   Example:

```
   Service is done, but FE is not working...

   Additional scope - webpack, swagger, unit tests
```

2. Link to Import Service API - .....
3. Link to FE PR (YOUR OWN REPOSITORY) - ...

4. In case SWAGGER file is not provided - please provide product schema in PR description
