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

### 2. The simplest example of using a variable

```php
< ?php
$text='Fuck you world!!!';
echo($text);
? >
```

This shows the use of a variable. Variable names (as well as function names) are case sensitive. Variables begin with a `$` symbol (the first character), the second character must be a letter. Variables are visible throughout the file, even if it is declared and assigned in one section < ?php, and used in another section < ?php. Variables are of three types - numeric, string and logical. The type is determined implicitly when a variable is assigned a value. A variable appears at the moment of its assignment. To check whether a variable exists, there is the IsSet function, for example (execute this code 2 times, the second time uncomment the assignment to the $index variable):

```php
< ?php
//$index = 10;
if (IsSet($index))
    echo '$index variable is set';
else
    echo '$index variable is NOT set';
? >
```

If a variable has not been set (assigned), but its value is used, then the variable automatically receives a default value. For example, if the function applied to a variable is mathematical, then the variable will be assigned the number 0. Variables declared outside functions are global, that is, they are visible throughout the file. Variables declared in the body of a function are visible only to that function. PHP operators, unlike functions, constants and variables, are case insensitive.

