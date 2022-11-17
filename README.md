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

- Aufruf über _'Terminal'_ -> _'Aufgabe ausführen...'_
- Edit über _'Terminal'_ -> _'Aufgabe konfigurieren...'_ oder direkt in der _'task.json'_ editieren

```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Run Style Check",
            "type": "shell",
            "command": "php 'php-cs-fixer-v3.phar' fix --config=.style/.php-cs-fixer.php -v --dry-run --allow-risky=yes --path-mode=intersection ."
        },
        {
            "label": "Run Json Check",
            "type": "shell",
            "command": "php .style/.php-json-fixer.php"
        },
        {
            "label": "Run Json Check & Fix",
            "type": "shell",
            "command": "php .style/.php-json-fixer.php fix"
        }
    ]
}
```
