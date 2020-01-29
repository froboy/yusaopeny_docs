### Welcome to OpenY wiki

## Adherence to standards: 
Open Y Core Team will adhere to the same standards we set for the community for all areas of development and technologies as per Open Y documentation.
Open Y Core Team reserves the right to break these standards only in the following scenario:
* Emergency - a major defect or security risk has been discovered that requires extreme measures to resolve.
* When the standards are broken, it is the responsibility of the Open Y core team to explain why the standards needed to be broken, and what the new standards will be moving forward.
* This communication will be posted to the Open Y message board, Slack, and the documentation on GitHub will be updated to reflect the new standards.

## Requirements for the Pull Request and code.

In order to deliver the best quality of the code and functionality in Open Y down below is a [list of requirements and best practices](https://github.com/ymcatwincities/openy/wiki/Open-Y-Code-of-Conduct-and-Best-Practices) we set for the development community.

* For the PHP code, we follow Drupal code standards https://www.drupal.org/docs/develop/standards
* For the Javascript, we follow couple standards - by AirBnd ( ReactJS ) https://github.com/airbnb/javascript/tree/master/react , and by Vue.js https://vuejs.org/v2/style-guide/

In order to create a good quality Pull Request we prepared a template https://github.com/ymcatwincities/openy/blob/8.x-2.x/.github/PULL_REQUEST_TEMPLATE.md , which automatically added to a new Pull Request in OpenY Github Repository.
List of requirements from the template:
* Provide a link to original issue, which is going to be fixed by PR you are creating.
* All coding styles are fulfilled and there are no issues reported by CodeSniffer. See [Code of Conduct](https://github.com/ymcatwincities/openy/wiki/Open-Y-Code-of-Conduct-and-Best-Practices).
* [Documentation](https://github.com/ymcatwincities/openy/tree/8.x-1.x/docs) has been updated according to PR changes.
* [Steps for review](https://github.com/ymcatwincities/openy/pull/94#issue-204580200) have been provided according to PR changes. <br/><img src="https://raw.githubusercontent.com/ymcatwincities/openy/8.x-1.x/.github/assets/steps-for-review.png" width="200" alt="Steps for review"/>
* Make sure you've provided all necessary hook\_update\_N to [support upgrade path](https://github.com/ymcatwincities/openy/blob/8.x-1.x/docs/Development/Upgrade%20path.md).
* Make sure your git email is associated with an account on drupal.org, otherwise you won't get commits there. <br/><img src="https://raw.githubusercontent.com/ymcatwincities/openy/8.x-1.x/.github/assets/drupalorg-email.png" width="200" alt="drupal.org email"/>
* If you would like to get credits on drupal.org, [check documentation](https://github.com/ymcatwincities/openy/blob/8.x-1.x/docs/Development/Contributing.md#drupalorg-credits).