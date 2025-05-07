
# Basic Usage  

Composer utilizes a configuration defined in a `composer.json` file  

Use the `require` key to tell composer which packages the project requires.

```json
{
    "require": {
        "monolong/monolog": "2.0.*"
    }
}
```

To install dependencies and update packages, use the `composer update` command  

The `composer.lock` file should be added in the code repo to maintain consistency of dependencies among developers. On the other hand the `\vendor` directory should be excluded (added to the `.gitignore` file)  

Running `composer install` reads all dependencies on the `composer.lock` file. Contratry to the `update` command, when a new version for a package is released, it will get the new version.  

To removed unused packages, just simply remove the package on the composer file and run the update command.  

`Packagist.org` is the main composer repository.
