# Стандарты качества кода Алекса Кодера

- [English version](./README.md)

## О стандартах

Стандарты качества кода Алекса Кодера представляют из себя набор из двух конфигурационных XML файлов для [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer); `ruleset.xml` - файл с набором базовых стандартов для PHP кода, а `ruleset-strict.xml` - определяет расширенный набор правил со строгим требованиям к комментированию классов и файлов.

Стандарты качества кода Алекса Кодера — это важный инструмент разработки, который гарантирует, что ваш код останется чистым и непротиворечивым.

## Требования

Стандарты качества кода Алекса Кодера используют в работе [PHP](https://www.php.net) начиная с версии 5.4.0 и [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) начиная с версии 3.6.0 и выше.

## Установка

Самый простой способ начать работу со стандартами качества кода Алекса Кодера — это установить их через [Composer](https://getcomposer.org) с помощью следующей команды:

```bash
composer require "alex-the-coder/coding-standards"
```

Или, в качестве альтернативы, добавить зависимость для `alex-the-coder/coding-standards` в файл `composer.json`. Например:

```json
{
    "require-dev": {
        "alex-the-coder/coding-standards": "^1.0"
    }
}
```

Затем вы можете запустить PHP_CodeSniffer из каталога `./vendor/bin`, чтобы убедиться, что необходимые зависимости и все стандарты качества кода Алекса Кодера установлены правильно:

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

## Начинаем работу

Чтобы проверить `.php` файл на соответствие стандартам качества кода Алекса Кодера, используйте аргумент командной строки `--standard` и укажите путь к файлу:

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset.xml /path/to/code/myfile.php
```

Если нужно проверить все файлы в каталоге, то можно вместо пути к файлу указать путь к каталогу:

```bash
./vendor/bin/phpcs -v --standard=./vendor/alex-the-coder/coding-standards/ruleset.xml /path/to/code-directory
```

Если PHP_CodeSniffer обнаружит какие-либо нарушения стандартов качества кода, то после выполнения этих команд будет показан отчет.

Полная информация об использовании PHP_CodeSniffer и примеры его отчетов о найденных ошибках качества кода доступны на [странице с примерами использования](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Usage).

### Собственный файл конфигурации стандартов качества кода

Что бы упростить команды можно создать собственный файл конфигурации `./.phpcs.xml` в корневом каталоге проекта и заполнить его следующим содержимым:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="PHPCS MyProjectName">
    <rule ref="./vendor/alex-the-coder/coding-standards/ruleset.xml" />
</ruleset>
```

После этого команды можно сократить до:

```bash
./vendor/bin/phpcs -v /path/to/code/myfile.php
```

или

```bash
./vendor/bin/phpcs -v /path/to/code-directory
```

См. больше информации об [использовании файлов конфигурации](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#using-a-default-configuration-file) и [наборах конфигурационных правил](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-Ruleset).

Полный список [настраиваемых сниффов и их свойств можно найти тут](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Customisable-Sniff-Properties).

## Документация

Документация для PHP_CodeSniffer доступна [на вики Github](https://github.com/squizlabs/PHP_CodeSniffer/wiki).

См. список [ключей и параметров запуска PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Configuration-Options) для более профессионального использования инструмента.
