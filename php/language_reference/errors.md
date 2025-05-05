
# Errors  

Handling errors can be configured on `php.ini` via `error_reporting` or using `error_reporting()` function at runtime  

Error reporting can be enabled for all by using the `E_ALL`. The display of these errors can be managed via `display_errors` control - this should also be disabled in production  

`log_errors` can also be enabled to store errors in a report file via `error_log` configuration  

`set_error_handler()` function can also be used to set error handlers  


