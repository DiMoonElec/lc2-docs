---
hide:
  - toc
---
# Если что-то пошло не так

## VS Code не видит LCCompiler
Если в консоль VS Code было выведено что-то подобное:
```bat
Executing task: lccompiler.exe project_template.lcprj -ast 

lccompiler.exe : Имя "lccompiler.exe" не распознано как имя командлета, функции, файла сценария или выполняемой программы. Проверьте прав
ильность написания имени, а также наличие и правильность пути, после чего повторите попытку.
строка:1 знак:1
+ lccompiler.exe project_template.lcprj -ast
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (lccompiler.exe:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```
это означает, что VS Code не смог найти путь к компилятору `lccompiler.exe`. Для начала убедитесь, что компилятор `LCCompiler` действительно установлен, и после установки была произведена перезагрузка ПК.  

После этого, откройте командную строку Winfows, и введите  `lccompiler.exe`. Если все хорошо, то вывод должен быть таким:
```bat
C:\Users\USER>lccompiler.exe
Формат командной строки: lcc PROJ_FILE.lcprj

C:\Users\USER>
```
### Если все равно не получается
- Перекачайте архив шаблона проекта, возможно, конфигурационные файлы шаблона повреждены. После этого попробуйте собрать проект еще раз.
- Если компилятор установлен и откликается из командной строки, файлы проекта корректны, однако, в VS Code все равно не удается собрать проект,  возможно, в VS Code что-то пошло не так.  
Попробуйте сделать это из командной строки. Для этого откройте `cmd`, перейдите в папку с проектом, и выполните компиляцию вручную:
```bat
C:\Users\USER>cd C:\Work\lc2\lccompiler\MISC\project_template

C:\Work\lc2\lccompiler\MISC\project_template>lccompiler.exe project_template.lcprj
main.lc:14:11:14:12:Info:Константное значение '1' преобразовано из типа 'sbyte' в 'int'
main.lc:15:11:15:12:Info:Константное значение '2' преобразовано из типа 'sbyte' в 'int'

Компиляция выполнена успешно
Размер исполняемого кода: 95 байт
Размер исполняемого файла: 130 байт
Выделено ОЗУ в статической области: 0 байт

C:\Work\lc2\lccompiler\MISC\project_template>
```