
### Handling installed packages  

When using `composer`, always run the `composer dump-autoload` after each dependency installation or namespace files updates. For consuming files, ensure that the `include` statement is added (`__DIR__ . "/vendor/autoload.php"`)
