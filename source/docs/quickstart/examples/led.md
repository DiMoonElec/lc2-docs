---
hide:
  - toc
---
# Пользовательский светодиод

### Пример: мигание пользовательским светодиодом

**Цель:**  
Включать и выключать светодиод `LED.1` каждую секунду.

```cs
bool LED @ "LED.1";

void init()
{
  _CYCLE((ushort)1000); // Обновление каждую секунду
  LED = false;
}

void loop()
{
  LED = !LED; // Инвертируем состояние светодиода
}
```
**Примечание**  

- Используется простое логическое отрицание !LED для смены состояния.
- Светодиод мигает с периодом 2 секунды (1 секунда включён, 1 секунда выключен).
