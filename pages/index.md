# Overview

Welcome to the [`Amazon ECS Blueprints`](https://github.com/aws-ia/ecs-blueprints) Quick Start documentation site. This site contains everything you should need to start getting the benefits of container-based modernization in hours rather than months.

# What is ECS Blueprints?

ECS Blueprints are terraform templates that you can deploy into your AWS account that meant to give new users a jumpstart and enable them to learn-by-doing. The blueprints are designed to demonstrate best practices for common, well-defined architectural patterns. The blueprints provide end-to-end solutions for scenarios addressing CI/CD, observability, security, and cost efficiency.

The blueprints are meant to be used as a starting point to gain understanding and proficiency but you should not expect to maintain any conformity with them. Adapt the modules by modifying them and extending them to suit your individual needs.

# Prerequisites

- You can use [AWS Cloud9](https://aws.amazon.com/cloud9/) which has all the prerequisites preinstalled and skip to [Quick Start](#quick-start)
- Mac (tested with OS version 12.+) and AWS Cloud9 Linux machines. We have **not tested** with Windows machines
- IaC Tool
  - [Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli) (tested version v1.3.7 on darwin_amd64)
  - [AWS CDK](https://aws.amazon.com/cdk/) (tested vision 2.70.+)
- [Git](https://github.com/git-guides/install-git) (tested version 2.27.0)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions)
- AWS test account with administrator role access
- Configure the AWS credentials on your machine `~/.aws/credentials`. You need to use the following format:

```shell
[AWS_PROFILE_NAME]
aws_access_key_id = Replace_with_the_correct_access_Key
aws_secret_access_key = Replace_with_the_correct_secret_Key
```

* Export the AWS profile name

```bash
export AWS_PROFILE=your_profile_name
```

- You can also set the default region and output format in `~/.aws/config`. Something like:

```shell
[default]
output = json
region = us-west-2
```

# Getting Started

You can work with and use the blueprints via the documentation here or work through the published [workshop](https://catalog.workshops.aws/ecs-solution-blueprints/en-US) instead.

- Fork this repository
- Clone your forked repository to your laptop/Cloud9 VM

```shell
git clone https://github.com/<your-repo>/ecs-blueprints.git
```

- Navigate to a blueprint in the navigation panel, to the left of this page, and follow the instructions for the blueprint. 

