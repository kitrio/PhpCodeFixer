# PhpCodeFixer
[![Composer package](http://xn--e1adiijbgl.xn--p1acf/badge/wapmorgan/php-code-fixer)](https://packagist.org/packages/wapmorgan/php-code-fixer) [![Latest Stable Version](https://poser.pugx.org/wapmorgan/php-code-fixer/v/stable)](https://packagist.org/packages/wapmorgan/php-code-fixer) [![Total Downloads](https://poser.pugx.org/wapmorgan/php-code-fixer/downloads)](https://packagist.org/packages/wapmorgan/php-code-fixer) [![License](https://poser.pugx.org/wapmorgan/php-code-fixer/license)](https://packagist.org/packages/wapmorgan/php-code-fixer)

PhpCodeFixer finds usage of deprecated functions, variables and ini directives in your php code.

# Example of usage
To scan your files or folder launch `phpcf` and pass file or directory names.
```
> php bin\phpcf tests
Max file size set to: 1.000 MiB
Scanning tests ...
[5.3] Function dl is deprecated in file tests/5.3.php[2].
[5.3] Ini setting define_syslog_variables is deprecated in file tests/5.3.php[3].
[5.4] Function mcrypt_generic_end is deprecated in file tests/5.4.php[2]. Consider using mcrypt_generic_deinit instead.
[5.5] Function preg_replace usage is deprecated (@preg_replace_e_modifier) in file tests/5.5.php[2].
[5.6] Ini setting mbstring.http_output is deprecated in file tests/5.6.php[6]. Consider using default_charset instead.
[5.6] Variable $HTTP_RAW_POST_DATA is deprecated in file tests/5.6.php[3]. Consider using php://input instead.
[7.0] Function mssql_connect is deprecated in file tests/7.0.php[8].
[7.0] Ini setting always_populate_raw_post_data is deprecated in file tests/7.0.php[10].
[7.0] Method name "test" in class "test" is deprecated (@php4_constructors) in file tests/7.0.php[3].
[7.1] Function mcrypt_decrypt is deprecated in file tests/7.1.php[2].
[7.1] Ini setting session.hash_function is deprecated in file tests/7.1.php[4].
Peak memory usage: 0.797 MB
```

By providing additional parameter `--target` you can specify version of PHP to perform less checks.

| Option       | Action                                      |
|--------------|---------------------------------------------|
| --target 7.1 | By default. Use all deprecations up to 7.1. |
| --target 7.0 | Use all deprecations from 5.3 to 7.0.       |
| --target 5.6 | Use all deprecations from 5.3 to 5.6.       |
| --target 5.5 | Use all deprecations from 5.3 to 5.5.       |
| --target 5.4 | Use all deprecations from 5.3 to 5.4.       |
| --target 5.3 | Use deprecations from 5.3 only.             |

# Installation
## Composer
The recommended way to install phpcf is via composer.

1. If you do not have composer installed, download the [`composer.phar`](https://getcomposer.org/composer.phar) executable or use the installer.
  ``` sh
  $ curl -sS https://getcomposer.org/installer | php
  ```

2. Run `php composer.phar require wapmorgan/php-code-fixer` or add requirement in composer.json.
  ``` json
  {
    "require": {
      "wapmorgan/php-code-fixer": "*"
    }
  }
  ```

4. Run `php composer.phar update`
