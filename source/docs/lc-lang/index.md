---
hide:
  - toc
---

## Особенности платформы <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span>

**Контроль цикла выполнения программы**  
Платформа <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> использует модель выполнения, схожую с Arduino, с функцией `loop()`, которая вызывается циклически. В отличие от Arduino, <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> позволяет задавать период вызова функции `loop()` (например, каждые 100 мс). Кроме того, Runtime предоставляет возможность измерять время выполнения `loop()`, что помогает оценить производительность пользовательского скрипта.

**IO-переменные**  
<span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> поддерживает IO-переменные, которые связывают программные переменные с физическими ресурсами устройства.

**Поддержка нативных функций**  
<span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> позволяет вызывать нативные C-функции из пользовательского скрипта, что позволяет реализовать низкоуровневые специфические возможности устройства. Так же как и IO-переменные, нативные функции являются частью Runtime и определяются на этапе его разработки.

**Си-подобный синтаксис**  
LC использует синтаксис, близкий к языку C, что упрощает освоение для разработчиков, знакомых с C, C++ или аналогичными языками.

**Поддерживаемые операторы**  
LC поддерживает стандартные управляющие конструкции:  

- Условные операторы: `if`, `else`  
- Циклы: `for`, `while`, `do-while`  
- Переключатели: `switch-case`
