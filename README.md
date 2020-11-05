# terraform-aws-eks-lb-controller

[![Lint Status](https://github.com/DNXLabs/terraform-aws-eks-lb-controller/workflows/Lint/badge.svg)](https://github.com/DNXLabs/terraform-aws-eks-lb-controller/actions)
[![LICENSE](https://img.shields.io/github/license/DNXLabs/terraform-aws-eks-lb-controller)](https://github.com/DNXLabs/terraform-aws-eks-lb-controller/blob/master/LICENSE)

<!--- BEGIN_TF_DOCS --->

## Requirements

| Name | Version |
|------|---------|
| terraform | ~> 0.13 |
| aws | >= 3.13, < 4.0 |
| helm | >= 1.0, < 1.4.0 |
| kubernetes | >= 1.10.0 |
| kubernetes-alpha | ~> 0.2.1 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 3.13, < 4.0 |
| helm | >= 1.0, < 1.4.0 |
| kubernetes | >= 1.10.0 |
| kubernetes-alpha | ~> 0.2.1 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| cluster\_identity\_oidc\_issuer | The OIDC Identity issuer for the cluster. | `string` | n/a | yes |
| cluster\_identity\_oidc\_issuer\_arn | The OIDC Identity issuer ARN for the cluster that can be used to associate IAM roles with a service account. | `string` | n/a | yes |
| cluster\_name | EKS cluster name. | `string` | n/a | yes |
| create\_namespace | Whether to create Kubernetes namespace with name defined by `namespace`. | `bool` | `true` | no |
| enabled | n/a | `bool` | `true` | no |
| helm\_chart\_name | AWS Load Balancer Controller Helm chart name. | `string` | `"aws-load-balancer-controller"` | no |
| helm\_chart\_release\_name | AWS Load Balancer Controller Helm chart release name. | `string` | `"aws-load-balancer-controller"` | no |
| helm\_chart\_repo | AWS Load Balancer Controller Helm repository name. | `string` | `"https://aws.github.io/eks-charts"` | no |
| helm\_chart\_version | AWS Load Balancer Controller Helm chart version. | `string` | `"1.0.3"` | no |
| mod\_dependency | Dependence variable binds all AWS resources allocated by this module, dependent modules reference this variable. | `any` | `null` | no |
| namespace | AWS Load Balancer Controller Helm chart namespace which the service will be created. | `string` | `"kube-system"` | no |
| service\_account\_name | The kubernetes service account name. | `string` | `"aws-alb-ingress-controller"` | no |
| settings | Additional settings which will be passed to the Helm chart values, see https://github.com/aws/eks-charts/tree/master/stable/aws-load-balancer-controller#configuration. | `map(any)` | `{}` | no |

## Outputs

No output.

<!--- END_TF_DOCS --->

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/terraform-aws-eks-lb-controller/blob/master/LICENSE) for full details.
