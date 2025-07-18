---
hide:
  - toc
---

# Оператор `continue`
Оператор `continue` используется внутри циклов (`for`, `while`, `do-while`) для немедленного перехода к следующей итерации, пропуская оставшуюся часть тела цикла. Оператор `continue` помогает упростить логику циклов, избегая вложенных условий и улучшая читаемость кода.

### Пример с `for`
```cs
void loop()
{
  for (int i = 0; i < 10; i++)
  {
    if (i % 2 == 0)
      continue; // пропускаем чётные числа

    // Этот код выполняется только для нечётных i
  }
}
```

### Пример с `while`
```cs
void loop()
{
  int i = 0;

  while (i < 10)
  {
    i++;

    if (i == 5)
      continue; // пропускаем значение 5

    // Этот код не выполнится при i == 5
  }
}
```