---
hide:
  - toc
---
# Дискретные входы и релейные выходы

### Пример: управление реле по дискретному входу

**Цель:**  
Включать **реле 1**, когда на дискретном **входе 1** появляется логическая `1`. Выключать — при логическом `0`. Этот пример демонстрирует базовое управление выходом в зависимости от состояния входа.

```cs
bool Input1 @ "DI.1";     // Дискретный вход
bool Relay1 @ "DO.1";     // Релейный выход

void init()
{
  _CYCLE((ushort)100);    // Вызывать loop() каждые 100 мс
}

void loop()
{
  Relay1 = Input1;        // Включаем реле, если вход активен
}
```

**Пояснение**  
`Input1` и `Relay1` — переменные, связанные с физическими входом и выходом.  
В `loop()` каждые 100 мс просто копируем значение входа на выход.  
Это позволяет нажатием кнопки или подачей сигнала на `DI.1` включать или выключать реле `DO.1`.

