# Einbindung in Visual Studio Code (Windows)

- Extension "php cs fixer" von junstyle installieren
- PHP und php-cs-fixer herunterladen:
  - <https://cs.symfony.com/download/php-cs-fixer-v2.phar> (Version 2)
  - <https://cs.symfony.com/download/php-cs-fixer-v3.phar> (Version 3)
- In settings.json folgende Einträge hinzufügen (Pfade anpassen):

```text
// Version 2
"php.validate.executablePath": "Path\\To\\php.exe",
"php-cs-fixer.executablePath": "Path\\To\\php-cs-fixer-v2.phar",
"php-cs-fixer.config": ".style/.php_cs",
"php-cs-fixer.allowRisky": true
```

```text
// Version 3
"php.validate.executablePath": "Path\\To\\php.exe",
"php-cs-fixer.executablePath": "Path\\To\\php-cs-fixer-v3.phar",
"php-cs-fixer.config": ".style/.php-cs-fixer.php",
"php-cs-fixer.allowRisky": true
```
