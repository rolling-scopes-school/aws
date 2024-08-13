## Prerequisites

To successfully complete this course, you'll need an AWS account.

While most of the labs in this course can be completed using the AWS free tier without any charges, 
there is a task that require the creation of paid resource, which is RDS in the task-8. 
Even though RDS is free tier compatible, making it publicly accessible(which is not quite a good practice) 
would cause you to be charged ~3$/month for public IP addres. You may consider deploying this RDS in 
a private subnet and deploying Lambda function in the VPC as well.
Before creating any type of resources, make sure you read and understand the appropriate pricing policy. 
Each AWS resource type has its own pricing page (e.g., [Route53 pricing](https://aws.amazon.com/route53/pricing/)). 

### To avoid unexpected expenses 
- Set up a billing alert to notify you when you've reached a specified threshold in your billing. 
- Use the minimum required resources. Performance will be considered only at the conceptual level.
- Shut down services/instances that you don't use after completing each lab.


## AWS Account

### Task 1 – Create an AWS Account

Follow this [link](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/) to create your account. Note that account activation usually takes a few minutes, but it might take up to 24 hours.

### Task 2 – Secure Your Account

Follow general AWS recommendations, such as:
- Secure your AWS account root user access keys ([reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html)).
- Avoid using the AWS account root user.
- Grant least privilege.
- Use permissions with AWS managed policies.
- Configure a strong password policy for your users.
- Enable MFA.

Read the full best practices article [here](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html).

### Task 3 – Set Budgets/Alerts

To avoid unexpected charges, monitor costs carefully:
- Enable free tier notifications ([link](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/tracking-free-tier-usage.html)).
- Set up budget notifications (e.g., 40%, 80%, 100%) manually via the console. Alerts should be sent to your email.

_* Optional: Set up Budgets using Infrastructure as Code (IaaC)._

### *Task 4 – Optional Task - Set Up Service Control Policies

_* This optional task is not mandatory for completing this module but is highly recommended. If you don't have time to complete it, feel free to skip it._

Service Control Policies (SCPs) help manage permissions in your organization. SCPs offer central control over the maximum available permissions for all accounts in your organization. SCPs can be configured as either:
- A deny list – actions are allowed by default, and you specify prohibited services and actions.
- An allow list – actions are prohibited by default, and you specify allowed services and actions.

We recommend starting with a deny list ([link](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_strategies.html#orgs_policies_denylist)). Create an organization and a new policy. The visual editor will assist you in adding necessary statements. Review the introduction to identify which resources should not be prohibited.
![](SCP.png)

## Key Takeaways

> - After creating an AWS account, set up Multi-factor Authentication.
> - Use your root account only for managing billing tasks
> - Do NOT share your account.
> - Do NOT commit your account credentials to Git.
> - Terminate/remove all created resources/services once you finish the module.
> - Don't forget to delete the NAT Gateway if you used it.
> - Do NOT leave instances running if you're not using them.
> - Carefully monitor billing and active instances to avoid exceeding limits.
> - Setup Budget Alerts
