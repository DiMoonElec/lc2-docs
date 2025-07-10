---
hide:
  - toc
---
# Интеграция с VS Code

На текущем этапе язык LC поддерживает базовую интеграцию с редактором Visual Studio Code. Это позволяет упростить работу с проектом за счёт:  

- Подсветки синтаксиса в исходных и проектных файлах
- Запуска компиляции проекта из интерфейса редактора
- Отображения сообщений компилятора в панели проблем

## Настройка
Для настройки интеграции необходимо создать в папке проекта подкаталог `.vscode` и добавить в него два файла: `settings.json` и `tasks.json`.

### Файл `settings.json`
Файл `settings.json` задаёт ассоциации типов файлов:
```json
{
  "files.associations": {
    "*.lcprj": "xml",
    "*.lc": "csharp"
  }
}
```  

- Файлы .lc будут подсвечиваться как C# — это временная мера, пока не будет реализована полноценная поддержка LC-синтаксиса.
- Файл .lcprj будет восприниматься как XML, что упростит его редактирование благодаря автозакрытию тегов и проверке структуры.

### Файл `tasks.json`
Файл `tasks.json` позволяет запускать компиляцию проекта с помощью команды сборки (`Ctrl+Shift+B`), а также отвечает за отображения сообщений компилятора в панели проблем VS Code. Пример конфигурации:
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Compile",
      "type": "shell",
      "command": "lccompiler.exe",
      "args": [
        "project_template.lcprj"
      ],
      "problemMatcher": [
        {
          "owner": "compiler1",
          "fileLocation": [
            "relative",
            "${workspaceFolder}"
          ],
          "pattern": {
            "regexp": "^(.*):(\\d+):(\\d+):(\\d+):(\\d+):(Error|Warning|Info):(.*)$",
            "file": 1,
            "line": 2,
            "column": 3,
            "endLine": 4,
            "endColumn": 5,
            "severity": 6,
            "message": 7
          }
        },
        {
          "owner": "compiler2",
          "fileLocation": [
            "relative",
            "${workspaceFolder}"
          ],
          "pattern": {
            "regexp": "^(.*):(Error|Warning|Info):(.*)$",
            "file": 1,
            "severity": 2,
            "message": 3
          }
        }
      ],
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```

## Примечания  

- Путь к `lccompiler.exe` должен быть либо прописан в переменной окружения `PATH`, либо указан явно в поле `command`.
- В параметре `args` необходимо указать имя проектного файла `.lcprj`.
