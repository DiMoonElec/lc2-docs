---
hide:
  - toc
---
# Изменяем в проекте целевой контроллер
Возвращаемя в VS Code. Здесь:  

- Открываем в текстовом редакторе файл проекта **project_template.lcprj** 
- Находим строку:
```xml
<platform>emu</platform>
```
и заменяем `emu` на `alpha-1208-01`:
```xml
<platform>alpha-1208-01</platform>
```
- В результате XML-файл проекта должен выглядет вот так:
```xml
<?xml version="1.0" encoding="utf-8"?>
<project>
  <platform>alpha-1208-01</platform>
  <source>
    <file>main.lc</file>
  </source>
  <outputdir>out</outputdir>
</project>
```
- После этого сохраняем этот файл, и пробуем скомпилировать проект еще раз. Если все прошло успешно, то платформа измена успешно, теперь этот проект будет компилироваться под **alpha-1208-01**.  


