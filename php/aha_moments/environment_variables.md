### $_ENV showing empty results?  

If $_ENV shows an empty array, but `getenv()` function still returns variables, check for the `php.ini` configuration and look for the `variables_order` configuration and ensure that `E` is part of the string. Restarting `php-fpm` and `httpd` might be required for the changes to reflect  

Using `$_ENV` might have performance impact. Still need to find out which approach is good for production setup  

**Important Note** - When using `php-fpm`, environment variables are configured on the fpm config file. In case of arch setup, config is found on `/etc/php/php-fpm.d/www.conf`. Ensure that `clear_env` variable is set to `no` in order for PHP to read variables from the config. To set a new variable, use the syntax`env[VARIABLE_NAME] = value`.  

Using the `$_ENV` is not ideal for production setup, the recommended way is to use `.env` config
