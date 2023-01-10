# Alex Coders's coding standards

- [README на русском](./README_RU.md)

## About

Alex Coders's PHP Coding Standards is a set of two [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) configuration XML files; the main `ruleset.xml` config file that define base PHP coding standard, and a second `ruleset-strict.xml` config file that define strict PHP coding standard.

Alex Coders's PHP Coding Standards is an essential development tool that ensures your code remains clean and consistent.

## Requirements

Alex Coders's PHP Coding Standards requires [PHP](https://www.php.net) version 5.4.0 or greater and [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) version 3.6.0 or greater.

## Installation

The easiest way to get started with Alex Coders's PHP Coding Standards is to install it through [Composer](https://getcomposer.org) with the following command:

```bash
composer require "alex-the-coder/coding-standards"
```

Or alternatively, include a dependency for `alex-the-coder/coding-standards` in your `composer.json` file. For example:

```json
{
    "require-dev": {
        "alex-the-coder/coding-standards": "^1.0"
    }
}
```

You can then run PHP_CodeSniffer from the vendor's bin directory to make sure the necessary dependencies and all Alex Coder's PHP Coding Standards are installed correctly:

```bash
./vendor/bin/phpcs -h
```

```bash
./vendor/bin/phpcbf -h
```

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset.xml ./vendor/autoload.php
```

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset-strict.xml ./vendor/autoload.php
```

## Getting Started

To check a PHP file against the Alex Coders's PHP Coding Standard, use the `--standard` command line argument and specify the file's location:

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset.xml /path/to/code/myfile.php
```

Or if you wish to check an entire directory you can specify the directory location instead of a file:

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset.xml /path/to/code-directory
```

If PHP_CodeSniffer finds any coding standard errors, a report will be shown after running the command.

Full usage information and example reports are available on the [usage page](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Usage).

### Custom configuration file

To simplify usage, you can create an XML configuration file `./.phpcs.xml` in your project root with the content:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="PHPCS MyProjectName">
    <rule ref="./vendor/alex-the-coder/coding-standards/ruleset.xml" />
</ruleset>
```

You can then run simple commands like:

```bash
./vendor/bin/phpcs -v /path/to/code/myfile.php
```

or

```bash
./vendor/bin/phpcs -v /path/to/code-directory
```

See more information about [using a Configuration File](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#using-a-default-configuration-file) and [Annotated Ruleset](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-Ruleset).

Full list of [Customisable Sniff Properties here](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Customisable-Sniff-Properties).

## Documentation

The documentation for PHP_CodeSniffer is available on the [Github wiki](https://github.com/squizlabs/PHP_CodeSniffer/wiki).

See the [Configuration Options manual page](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Configuration-Options).
