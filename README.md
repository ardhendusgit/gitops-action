# GitOps-Setting up the Application

Here, we set up the application end of the GitOps project. The infrastructure workflow-associated code can be found [here](https://github.com/ardhendusgit/IAC-AWS).

## Setting Up SonarCloud

We'll go to SonarCloud to create our organization, project, and token. We'll then store this token securely in GitHub Secrets.

## Application Deployment

Our deployment file includes the image name and tag. While we can't directly add variables here, we'll use Helm charts, which support variables that can be passed at runtime.

## GitHub Workflow Configuration

In our GitHub workflow, we need to define some environment variables such as `AWS_REGION` and `ECR_REPOSITORY` all of which can be found in the workflow file.

## Important note on Quality Gates
One might encounter a quality gate not setup error while executing the workflow which can be resolved by following:

### Quality Gates Setup

Within our SonarCloud organization, we can create custom quality gates. Follow these steps:

1. Navigate to SonarCloud and go to your organization.
2. Access the quality gates section.
3. Create a new quality gate, such as `sample-quality-gate`.
4. Save the settings and add relevant rules.
