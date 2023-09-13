---
title: Pull Requests review standard
aliases:
  - /docs/wiki/open-y-pull-requests-review-standard/
---

Check more [technical guidelines about our best practices for code quality]({{< relref "../Code-Review-Quality-Best-Practices" >}}).

# Adherence to Standards

The YMCA Website Services Core Team will adhere to the same standards we set for the community for all areas of development and technologies as per the YMCA Website Services documentation.

The YMCA Website Services Core Team reserves the right to break these standards only in the following scenarios:

- Emergency - a major defect or security risk has been discovered that requires extreme measures to resolve.
- When the standards are broken, it is the responsibility of the YMCA Website Services Core Team to explain why the standards needed to be broken, and what the new standards will be moving forward.
- This communication will be posted to the YMCA Website Services message board, Slack, and the documentation on GitHub will be updated to reflect the new standards.

## Requirements for Pull Requests

- Code in Pull Requests should follow our established [best practices]({{< relref "../Code-Review-Quality-Best-Practices" >}})
- Submitters' profiles on GitHub or Drupal.org should be up to date and contain at least a name and organization.

## Template for the PR

In order to create a good quality Pull Request, we prepared a [PR template](https://github.com/YCloudYUSA/yusaopeny/blob/8.x-2.x/.github/PULL_REQUEST_TEMPLATE.md) which is automatically added to new Pull Requests on GitHub.

List of requirements from the template:

- Provide a link to the original issue, which is going to be fixed by the PR you are creating.
- All coding styles are fulfilled and there are no issues reported by CodeSniffer. See [Code of Conduct]({{< relref "Open-Y-Code-of-Conduct-and-Best-Practices" >}}).
- [Documentation](https://github.com/YCloudYUSA/yusaopeny/tree/9.x-2.x/docs) have been updated according to PR changes.
- [Steps for review](https://github.com/YCloudYUSA/yusaopeny/pull/94#issue-204580200) have been provided according to PR changes. <br/><img src="https://raw.githubusercontent.com/YCloudYUSA/yusaopeny/8.x-1.x/.github/assets/steps-for-review.png" width="200" alt="Steps for review"/>
- Make sure you've provided all necessary hook\_update\_N to [support upgrade path](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/docs/Development/Upgrade%20path.md).
- Make sure your git email is associated with an account on drupal.org, otherwise you won't get commits there. <br/><img src="https://raw.githubusercontent.com/YCloudYUSA/yusaopeny/8.x-1.x/.github/assets/drupalorg-email.png" width="200" alt="drupal.org email"/>
- If you would like to get credits on drupal.org, [check documentation](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/docs/Development/Contributing.md#drupalorg-credits).
