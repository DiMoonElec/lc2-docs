---
hide:
  - toc
---

# Цикл `for`

Оператор `for` используется для организации повторяющегося выполнения блока кода. Его синтаксис аналогичен языку C, с одним отличием: условие (cond) обязательно должно иметь тип `bool`.
```cs
for (initialization; cond; iteration) 
{
  // Тело цикла
}
```
Цикл `for` состоит из трёх частей:  

- **Инициализация** — выполняется один раз перед началом цикла:  
```cs
int i = 0
```
- **Условие продолжения** — проверяется перед каждой итерацией:
```cs
i < 10 (должно быть типа bool)
```
- **Изменение переменной** — выполняется после каждой итерации:
```cs
i++
```

### Пример
В этом примере переменная i принимает значения от 0 до 9. Каждому элементу массива присваивается соответствующее значение:
```cs
int array[10];

void init()
{
  for (int i = 0; i < 10; i++) 
    array[i] = i;
}

```