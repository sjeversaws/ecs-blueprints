# VPC Endpoints

VPC Endpoints optimize the network path by avoiding traffic to internet gateways and incurring cost associated with NAT gateways, NAT instances, or maintaining firewalls. VPC Endpoints also provide you with much finer control over how users and applications access AWS services. VPC Endpoints prevent sensitive data from traversing the Internet, which helps you maintain compliance with regulations such as HIPAA, EU/US Privacy Shield, and PCI.

This solution blueprint creates VPC Endpoints for S3, ECS, ECR(Private Repositories only), Secrets Manager, and Systems Manager, CloudWatch.

## Deploy the Core Infrastructure

> [!IMPORTANT]
> If you have already deployed the infra then you can skip this step.

Deploy the [core-infrastructure](../core-infra/core-infra.md).

## Deploy the Blueprint

> [!NOTE] 
> You will need to keep `enable_nat_gw = true` in `core-infra` [variables.tf](../../../terraform/fargate-examples/core-infra/variables.tf) if you intend to pull container images from Public ECR repositories. This is not supported and is currently blocked by this [PR](https://github.com/aws/containers-roadmap/issues/1160).

> [!NOTE]
> If you would like to disable the NAT Gateway, change `enable_nat_gw = false` in `core-infra` [variables.tf](../../../terraform/fargate-examples/core-infra/variables.tf). Please ensure that this solution blueprint deploys successfully prior to disabling the NAT Gateway in `core-infra`.
  

- Navigate to the blueprint folder:

```shell
cd ecs-blueprints/terraform/fargate-examples/vpc-endpoints/
```

- Run the following:

```shell
terraform init
terraform plan
terraform apply -auto-approve
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.1 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 4.43 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 4.43 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_vpc_endpoints"></a> [vpc\_endpoints](#module\_vpc\_endpoints) | terraform-aws-modules/vpc/aws//modules/vpc-endpoints | n/a |

## Resources

| Name | Type |
|------|------|
| [aws_security_group.vpc_endpoints](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_route_table.private](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/route_table) | data source |
| [aws_subnet.private_cidr](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/subnet) | data source |
| [aws_subnets.private](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/subnets) | data source |
| [aws_vpc.vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/vpc) | data source |

## Inputs

No inputs.

## Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
