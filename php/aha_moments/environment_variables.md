### $_ENV showing empty results?  

If $_ENV shows an empty array, but `getenv()` function still returns variables, check for the `php.ini` configuration and look for the `variables_order` configuration and ensure that `E` is part of the string. Restarting `php-fpm` and `httpd` might be required for the changes to reflect  

Using `$_ENV` might have performance impact. Still need to find out which approach is good for production setup  

**Important Note** - When using `php-fpm`, environment variables are configured on the fpm config file. In case of arch setup, config is found on `/etc/php/php-fpm.d/www.conf`. Ensure that `clear_env` variable is set to `no` in order for PHP to read variables from the config. To set a new variable, use the syntax`env[VARIABLE_NAME] = value`.  

Using the `$_ENV` is not ideal for production setup, the recommended way is to use `.env` config  

### Loading Environment Variables from .env file  

Use `vlucas\phpdotenv` package to load environment variables added on the .env config file.  

**Sample Config File**  

```
USER=test_user
PASSWORD=mypass123
SERVER=mysql:host=localhost
```  

### Using Dotenv in PHP Project  

Once `vlucas\phpdotenv` package has been installed, make sure to run `composer dump-autoload` to update the loaded class files. On the php file where the environment variable is required ensure to add the import statement and load the environment variables using the Dotenv `load()` function. See implementation below:  

```php
<?php
    `include __DIR__ . "/vendor/autoload.php"`

    use Dotenv\Dotenv;

    $dotenv = Dotenv::CreateImmutable(__DIR__); // loads .env file on the project location
    $dotenv->load(); // makes the environment variables available on the $_SERVER and $_ENV global variables

    // To access the variables, see below
    $username = $_SERVER["USER"];
    $password = $_SERVER["PASSWORD"];
?>
```
