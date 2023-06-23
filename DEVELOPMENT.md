To get started, simply run:
```
ddev start \
  && git clone --branch 10.1.x https://git.drupalcode.org/project/drupal.git repos/drupal \
  && ddev composer install \
  && ddev drush si \
  && ddev drush uli
```

Update 10.1.x with the Drupal version you're working with, or use a merge request per the following.

Example of using a merge request for the Drupal repository:

```
$ cd repos/drupal
$ git remote add drupal-2478663 git@git.drupal.org:issue/drupal-2478663.git
$ git fetch drupal-2478663
$ git checkout 2478663-uniquefieldvaluevalidator-works-only
```

[Example MR](https://git.drupalcode.org/issue/drupal-2478663/-/tree/2478663-uniquefieldvaluevalidator-works-only)

Use the "Clone from SSH" link to get the URL to use for `git remote add` -- the remote name can be arbitrary

The branch name is the last part of the URL.

Example running a PHP unit test:

```
$ ddev drush ssh
# ../vendor/bin/phpunit -c core core/tests/Drupal/KernelTests/Core/Validation
```
