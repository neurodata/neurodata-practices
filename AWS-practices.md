# AWS Practices
This document is a working draft. PRs are welcome.

[AWS](https://aws.amazon.com/what-is-aws/) (Amazon Web Services) is a cloud-computing platform offered by Amazon. It gives us computing infrastructure as well as a set of [services](https://aws.amazon.com/products) to operate on that infrastructure.

## Getting Started
* Ask NeuroData's AWS admin for login information for one of our AWS accounts, or for help setting up a new AWS account.
* Explore AWS's [Getting Started](https://aws.amazon.com/getting-started/tutorials/) tutorial page
* 10-minute training videos for most topics [here](https://www.aws.training/LearningLibrary?filters=language%3A1&search=&tab=view_all)
* Explore AWS services [here](https://aws.amazon.com/products/) for a quick overview of potential uses

## Projects
* Currently, NeuroData uses AWS for:
    * neuroglancer data storage
    * Running registrations
    * ndmg batch processing

## [Security](https://d0.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf) and [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) (Identity and Access Management)
* Never use root accounts unless absolutely necessary. Instead, create one or more IAM users and use them to perform all tasks.
* [One admin account per AWS organization](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#lock-away-credentials)
    * This account should only be used to change IAM permissions on sub-accounts.
    * It should not be the root account - it should be an IAM user with administrative privileges.
* IAM users have only the limited permissions necessary to perform their tasks. Admin accounts add permissions as needed.
    * Use [managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies) and add to users / groups.
* IAM user credentials should be stored securely using `aws configure`. This saves credentials to `~/.aws/credentials`.
* [Never store credentials publicly or embed them in unencrypted code.](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#sharing-credentials)
* Use IAM roles for applications that run on Amazon EC2 instances (e.g., any application that requires credentials).

## Grants
* AWS provides [grants](https://aws.amazon.com/research-credits/faq/) for funding academic research.
* When structuring a grant, briefly address:
    * a short description of the problem
    * Proposed AWS solution
    * Plan for open sharing deliverable (e.g., a neurodata repo)
    * Potential future uses of the AWS project
    * [AWS public datasets](https://registry.opendata.aws/) to be used in the research