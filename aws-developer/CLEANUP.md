# Cleaning Up Resources After Passing the Course

After completing the course, it's a good idea to clean up all the resources you have created to avoid unnecessary spendings.

## Table of Contents
1. [Removing CDK Deployments from All Repos](#removing-cdk-deployments-from-all-repos)
2. [Remove RDS via Console](#remove-rds-via-console)
3. [Remove DynamoDB via Console](#remove-dynamodb-via-console)
4. [Clean and Delete S3 Buckets](#clean-and-delete-s3-buckets)
5. [Ensure CloudFormation is Clean](#ensure-cloudformation-is-clean)
6. [Remove All LogGroups from CloudWatch](#remove-all-loggroups-from-cloudwatch)
7. [Check if Lambda, EC2, CloudFront, SNS, SQS, API Gateway, and EBS Pages are Empty](#check-if-lambda-ec2-cloudfront-sns-sqs-api-gateway-and-ebs-pages-are-empty)

## Removing CDK Deployments from All Repos

1. Navigate to the directories of your CDK stacks.
2. Run the following command to destroy the stack:
    ```sh
    cdk destroy --all
    ```
3. Confirm the destruction when prompted.

Repeat these steps for each CDK project repository.

## Remove RDS via Console

1. Open the [Amazon RDS Console](https://console.aws.amazon.com/rds/).
2. In the navigation pane, choose **Databases**.
3. Select the database instance you want to delete.
4. Choose **Actions** and then **Delete**.
5. Remove the checkbox from Final backup creation.
5. Follow the prompts to delete the database instance.

## Remove DynamoDB via Console

1. Open the [Amazon DynamoDB Console](https://console.aws.amazon.com/dynamodb/).
2. In the navigation pane, choose **Tables**.
3. Select the table you want to delete.
4. Choose **Actions** and then **Delete Table**.
5. Confirm the deletion.

## Clean and Delete S3 Buckets

1. Open the [Amazon S3 Console](https://console.aws.amazon.com/s3/).
2. Select the bucket you want to delete.
3. Empty the bucket by deleting all objects and folders within it.
4. Once the bucket is empty, select the bucket again.
5. Choose **Delete bucket** and confirm the deletion.

## Ensure CloudFormation is Clean

1. Open the [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation/).
2. In the navigation pane, choose **Stacks**.
3. Review the list of stacks. If there are any stacks you no longer need, select them.
4. Choose **Delete** and confirm the deletion.

## Remove All LogGroups from CloudWatch

1. Open the [Amazon CloudWatch Console](https://console.aws.amazon.com/cloudwatch/).
2. In the navigation pane, choose **Log groups**.
3. Select the log groups you want to delete.
4. Choose **Actions** and then **Delete log group(s)**.
5. Confirm the deletion.

## Check if Lambda, EC2, CloudFront, SNS, SQS, API Gateway, and EBS Pages are Empty

1. **Lambda**:
    - Open the [AWS Lambda Console](https://console.aws.amazon.com/lambda/).
    - Ensure there are no functions listed. If there are, delete them.

2. **EC2**:
    - Open the [Amazon EC2 Console](https://console.aws.amazon.com/ec2/).
    - Ensure there are no running instances, volumes, or other resources. Terminate any that are still active.

3. **CloudFront**:
    - Open the [Amazon CloudFront Console](https://console.aws.amazon.com/cloudfront/).
    - Ensure there are no distributions. If there are, disable and delete them.

4. **SNS**:
    - Open the [Amazon SNS Console](https://console.aws.amazon.com/sns/).
    - Ensure there are no topics or subscriptions. Delete any that exist.

5. **SQS**:
    - Open the [Amazon SQS Console](https://console.aws.amazon.com/sqs/).
    - Ensure there are no queues. Delete any that exist.

6. **API Gateway**:
    - Open the [Amazon API Gateway Console](https://console.aws.amazon.com/apigateway/).
    - Ensure there are no APIs. Delete any that exist.

7. **EBS**:
    - Open the [Amazon EC2 Console](https://console.aws.amazon.com/ec2/).
    - In the navigation pane, choose **Elastic Block Store** > **Volumes**.
    - Ensure there are no volumes. Delete any that exist.

