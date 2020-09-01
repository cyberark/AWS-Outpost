# Contributing

All contributions will be reviewed and merged based on proof of accuracy.  To properly confirm that the changes suggested are accurate, it will need to be shown that Subnets created in CloudFormation are properly attributed to an AWS Outpost by displaying the Outpost ARN in the OutpostID of the Subnet details page.

For general contribution and community guidelines, please see the [community repo](https://github.com/cyberark/community).

## Table of Contents

- [Development](#development)
- [Testing](#testing)
- [Releases](#releases)
- [Contributing](#contributing)

## Development

AWS CloudFormation
AWS Lambda
AWS Outpost

## Testing

- Create a Stack in AWS CoudFormation and successfully deploy Subnets using your modified template
- Ensure that the Subnets that are created have the Outpost ARN listed for their OutpostID
- Ensure that the Stack can be Created and Deleted
- Remove any permissions given by the template during creation. When a successful run of the stack is completed all permissions that were given by the template have been removed when the template is finished
- Ensure the creation of the PAS VPC
- Ensure Route Tables have proper communication between Vault a Components
- Primary and Secondary subnets for:
  * Vault and DR
  * CPM
  * PVWA
  * PSM
  * PSMP
  * PTA
  * NAT GW is a public subnet and in the Region

## Releases

A new release will only be accepted if the use of a Lambda function is removed and uses CloudFormation exclusively

## Contributing

1. [Fork the project](https://help.github.com/en/github/getting-started-with-github/fork-a-repo)
2. [Clone your fork](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)
3. Make local changes to your fork by editing files
3. [Commit your changes](https://help.github.com/en/github/managing-files-in-a-repository/adding-a-file-to-a-repository-using-the-command-line)
4. [Push your local changes to the remote server](https://help.github.com/en/github/using-git/pushing-commits-to-a-remote-repository)
5. [Create new Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)

From here your pull request will be reviewed and once you've responded to all
feedback it will be merged into the project. Congratulations, you're a
contributor!