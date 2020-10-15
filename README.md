# quickstart-atlassian-bitbucket
## Bitbucket Data Center on the AWS Cloud

Use this Quick Start to deploy Bitbucket Data Center on the AWS Cloud. Bitbucket Data Center is a Git repository management solution from Atlassian. It provides source code collaboration for enterprises that require high availability and performance at scale.

This Quick Start uses the [Atlassian Standard Infrastructure (ASI)](https://fwd.aws/xYyYy) as a foundation. You can choose to build a new ASI for your deployment or deploy Bitbucket into your existing ASI. You can also deploy Jira and Confluence Data Center within the same ASI.

![Quick Start architecture for Bitbucket on AWS](https://d1.awsstatic.com/partner-network/QuickStart/datasheets/bitbucket-arch-on-aws.ff04565943707be2329083b6ef3f17e7e096d1f9.png)

For architectural details, best practices, step-by-step instructions, and customization options, see the 
[deployment guide](https://fwd.aws/dEX6W).

### Network prerequisites

You need to create the required AWS networking infrastructure
(VPC, subnets) by using the [ASI Quick Start](https://fwd.aws/xYyYy), or by deploying Bitbucket with a new ASI.
For details, see the [deployment guide](https://fwd.aws/dEX6W).

## Deploying for production

For production deployments, avoid launching the Bitbucket Quick Start from the AWS Quick Start interface. If you do, any changes made to the Quick Start templates will propagate directly to your deployment. These updates sometimes introduce unexpected changes that could break your deployment.

Instead, clone the Bitbucket Quick Start templates to a custom Amazon Simple Storage Service (Amazon S3) bucket. Then, launch the templates directly from the S3 bucket. This practice lets you control when to apply the latest changes to your environment. See [Launching from a cloned Quick Start (recommended for production)
](https://confluence.atlassian.com/x/GZUdOg#GettingstartedwithBitbucketDataCenterinAWS-s3bucketcustom) for instructions.

## Development notes

### Pre-commit hook

It is recommended that you install the hooks under `submodules/quickstart-atlassian-services/scripts/hooks/`; this will
ensure that the metadata tags in the templates are automatically updated on
commit. The simplest method of doing this is:

    git config --add core.hooksPath submodules/quickstart-atlassian-services/scripts/hooks/

Alternatively you can invoke
`submodules/quickstart-atlassian-services/scripts/hooks/update-tags.py`
manually.

## Atlassian support

This Quick Start's CloudFormation templates were developed by Atlassian, in collaboration with AWS. To report an issue or request a feature, you can [contact Atlassian directly](https://support.atlassian.com/contact/#/).

For additional Atlassian documentation on how to manage Quick Start deployments, see [Getting started with Bitbucket Data Center in AWS](https://confluence.atlassian.com/x/GZUdOg).
