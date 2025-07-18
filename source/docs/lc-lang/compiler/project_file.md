---
hide:
  - toc
---
# Формат файла проекта
Файл проекта (.lcprj) — это XML-документ, содержащий описание параметров сборки, включая целевую платформу, исходные файлы и путь для сохранения результата компиляции.

## Структура файла проекта
Пример минимального проекта:
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
**Описание элементов**  

| Элемент           | Обязательность          | Описание |
|-------------------|-------------------------|----------|
| &lt;platform&gt;  | Да                      | Имя целевой платформы. Используется для выбора xml-файла с описанием аппаратных особенностей контроллера. Этот файл должен находиться в подкаталоге platform рядом с lccompiler.exe. |
| &lt;source&gt;    | Да                   | Секция со списком исходных файлов. |
| &lt;file&gt;      | Да (внутри <source>) | Путь к исходному файлу на языке LC. Указывается относительно местоположения lcprj-файла. Пока поддерживается только один файл, поддержка нескольких будет добавлена в будущем. | 
| &lt;outputdir&gt; | Нет (по умолчанию: ./out) | Относительный путь к каталогу, в который будет помещён результат компиляции. Путь задаётся относительно расположения .lcprj-файла. |


## Результат компиляции
После успешной сборки компилятор создаёт в папке outputdir несколько файлов. Все они используют имя проекта (без расширения) в качестве префикса:

| Файл | Назначение                                                                                       |
|-----------------------------|---------------------------------------------------------------------------|
| &lt;имя_проекта&gt;.xml     | Список всех объектов, размещённых в глобальной области памяти.            |
| &lt;имя_проекта&gt;.lcasm   | Ассемблерный листинг проекта.                                             |
| &lt;имя_проекта&gt;.dbginfo | Отладочная информация, необходимая для реализации пошаговой отладки.      |
| &lt;имя_проекта&gt;.lcx     | Скомпилированный бинарный файл, готовый к загрузке в целевое устройство.  |

## Примечания  

- Все пути в файле проекта указываются относительно местоположения самого .lcprj-файла.
- Название платформы (&lt;platform&gt;) должно точно соответствовать имени xml-файла платформы (без расширения), который размещается в папке `platform` рядом с `lccompiler.exe`.