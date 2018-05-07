magento2-travis
--------------------------------------------------
This is a slightly modified version of the travis build script I created [for pestle](https://github.com/astorm/pestle), my Magento 2 code generate tool/module base PHP command line framework.

This script will get you

1. A working PHP 5.6 and PHP 7.0 build enviornment
2. A php-fpm webserver
3. A MySQL server
4. An installed Magento with configurable install parameters
5. An extra installed composer package of your choice

Assuming your module is [setup in a git repository somewhere as a composer package](http://magento-quickies.alanstorm.com/post/138242522550/magento-2-minimum-composer-file), you should be able to change

    - PULSESTORM_COMPOSER_REPOSITORY_TO_TEST=git@github.com:astorm/pestle.git
    - PULSESTORM_COMPOSER_PACKAGE_TO_TEST=pulsestorm/pestle

to point to your repository.  The travis script will checkout magento's develop branch, add your github repository as a composer repository, require in your named composer package, and then install Magento 2.  At the end of the process you'll have a built out Magento enviornment that's suitable for running integration/acceptance tests against.

If you're hitting GitHub API limits when [importing your own](https://github.com/astorm/magento2-travis/blob/0.0.1/.travis.yml#L85) packages, [you can set a](https://github.com/astorm/magento2-travis/blob/0.0.1/.travis.yml#L83) `GH_TOKEN` [environmental variable in travis](https://blog.wyrihaximus.net/2015/09/github-auth-token-on-travis/)

The rest should be self explanatory via the comments.  If you're confused by something, or something doesn't work, please open a GitHub issue here.
