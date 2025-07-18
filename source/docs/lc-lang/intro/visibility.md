---
hide:
  - toc
---
# Области видимости
Программа на языке LC включает две области видимости переменных: **глобальную** и **локальную**.

## Глобальные переменные
**Глобальные переменные**, это переменные, объявленные вне функций. Эти переменные располагаются компилятором во время компиляции в статической области памяти, и их значения сохраняются между вызовами функций. В отличие от C/C++, язык LC позволяет использовать глобальные переменные до их текстового объявления, поскольку поиск выполняется по всей глобальной области, независимо от позиции в коде.
### Пример объявления глобальных переменных
```cs
//Объявление глобальных переменных
byte var1;
short var2;

void loop()
{
  var1 = 1;
  var2 = 2;
  var3 = 3;
}

//Тут тоже можно объявлять глобальные переменные
int var3;
```
## Локальные переменные
**Локальные переменные** объявляются внутри функций, и располагаются на стеке. Значения локальных переменных не сохраняются между вызовами функции. Как и в C/C++, использовать локальную переменную можно только после ее объявления.
### Пример объявления локальных переменных
```cs
void loop()
{
  int a; //Объявляем локальную переменную
  a = 100; //Используем локальную переменную

  //Объявляем и одновременно инициализируем 
  //локальную переменную
  int b = 10; 
}
```
## Имена переменных
В пределах одной области видимости, не допускается объявление переменных с одинаковыми именами.
### Пример правильного и ошибочного именования переменных
```cs
int a; // Объявление переменной `a` в глобальной области 
int a; // !!! ОШИБКА !!!

void loop()
{
  int a; // Объявляем переменную `a` в локальной области
  int a; // !!! ОШИБКА !!!
}
```

## Поиск переменной
При использовании переменной, компилятор выполняет поиск eё объявления по имени, начиная с текущей области видимости и далее вверх по иерархии вложенных областей (лексических областей). Будет использовано первое найденное объявление.  
### Пример работы областей видимости
```cs
int a; //(1)

void loop()
{
  a = 0; //Используется переменная (1)
  
  int a; //(2)

  a = 1; //Используется переменная (2)

  if(a == 1)
  {
    //Блок в фигурных скобках создаёт новую область видимости
    a = 2; //Используется переменная (2)
    
    int a; //(3)
    a = 3; //Используется переменная (3)
  }
}
```