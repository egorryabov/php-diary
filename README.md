# php-diary

## The simplest examples of scripts in PHP Print

The specified PHP section can be used anywhere in the file, an unlimited number of times, interspersed with plain HTML text. In order for the PHP code to be interpreted, the html page (.htm or html extension) must be renamed to .php.

### 1. Simple text output
```php
< ?php echo "Hello world"; ? >
```
Text can be entered in either single or double quotes. Arguments can be passed to functions without parentheses. In addition to echo, you can use the print keyword. The difference between echo and print is that echo can print multiple lines, separated by commas:
```php
< ?php
echo "1", "2", '< br >';
echo '1', " 2", "< br >";
? >
```
Both of these lines will produce the same result. Single quotes differ from double quotes in that single quotes disable scanning of the string for variables, for example, in the following example, only the first echo statement will print the value of the variable:
```php
< ?php
$index = 10;
echo "index==$index< br >";
echo 'index==$index< br >';
? >
```

Single quotes also disable Esc codes (see below). Single quotes improve code performance, so using them is preferable.

Another way to define strings is to use heredoc syntax. In this case, the line must begin with the <<< character, followed by an identifier. The line ends with the same identifier. The closing identifier must begin in the first column of the row. Additionally, the identifier must follow the same naming conventions as all other tags in PHP: contain only alphanumeric characters and underscores, and not begin with a number or underscore.

Heredoc text behaves in the same way as a string in double quotes, without having them. This means that you don't need to escape quotes in heredoc, but you can still use the escape sequences listed above. Variables inside heredoc are also processed.
```php
< ?php
$str = <<<EOD
Example of a string spanning several
lines using
heredoc syntax
EOD;
// Here the identifier is EOD. Below
// EOT identifier
$name = 'Vasya';
echo <<<EOT
My name is "$name".
EOT;
// this will print "My name is "Poul"."
? >
```
