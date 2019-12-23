# wordpress-starter-plugins
A collection of starter plugins for wordpress that can be maintained through composer

Copy plugin files into your repository
--------------------------------------

Copy all the plugin's files into your new repository.

Commit your plugin to Git and push your changes to GitHub
---------------------------------------------------------

Run each of the following commands from your repository directory:

Add all of your plugin's files to Git.

```
$ git add .
```

Commit your changes

> **Tip**: include the plugin's version number in your commit message so that you can easily reference it later!

```
$ git commit .
```

Tag the release
---------------

Composer will need a way to know the version of a plugin.
Use [git tags](https://getcomposer.org/doc/articles/versions.md#tags) 
Composer will interpret them correctly if they use [semantic versioning](https://semver.org/).

Example : if pushing SearchWP version 2.9.14. That means you will be creating the 2.9.14 tag. Remember, tags are tied to commits, so be sure to commit all your changes *before* creating the tag.

```
git tag 2.9.14
```

Push your changes, and your tags to GitHub:

```
$ git push --tags
```

> **Tip:** Tags pushed to GitHub will automatically be turned into "Releases," a feature of GitHub. You can also [create releases](https://help.github.com/articles/creating-releases/) manually on the GitHub website.

Edit your `composer.json` file, add your repository and plugin
----------------------------------------------------------------------

In your site's `composer.json`

-   Add a new your GitHub repository to the `repositories` section referencing your GitHub repository:

```
  "repositories": [

  ...

    {
      "type": "vcs",
      "url": "git@github.com:YourGitHubUsername/example-plugin.git"
    }

  ...

  ],
```

-   Add your plugin to the `require` section using the version number you named your `release` after:

```
  "require": {

  ...

    "YourGitHubUsername/example-plugin": "2.9.14",

  ...

  },
```
