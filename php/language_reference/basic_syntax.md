
# PHP Tags  

Php executable code are written using this format  

```php
<?php
    ... code to run here
?>
```

Single output lines can also be written as:  

```php
<?= "to print here" ?>
```  

Equivalent to  

```php
<? echo "to print here" ?>
```  

If a file is plainly php code, there is no need to add the closing tag.  


# Escaping from HTML  

Everything outside the php tags are not executed so this can make embedding in html templates very easy.  

```
<p>This is a sample paragraph inside a php file</p>

<?php echo "This is a php output." ?>

<p>This is another paragraph after php output</p>
```

## Advanced escaping using php conditions  

```
<?php if($expression = true): ?>
    This will show if expression is true
<?php else: ?>
    Otherwise this will show
<?php endif; ?>
```  

# Instruction Separation  

Semicolon is required to terminate each statement. For lines part of the closing tag, no need to add semicolon as this is automatically implied.  

```
<?php echo "This is a sample line."; ?>
No new line
<?= "But new line now" ?>
```

Please see another sample below.  

```
<?php echo "This is a test.\n"; ?>

<?php echo "This is another test.\n"; ?>

<?php echo "We omitted the last closing tag"
``` 

*Note: php newlines may not be reflected if using a browser as \\n is not a valid new line HTML syntax. To view the raw php output, set the `Content-Type: text/plain` as header.*  


# Comments  

// => one-line comment in C++ style  

\# => one-line comment in shell-style

/* ... */ => multi-line comment
