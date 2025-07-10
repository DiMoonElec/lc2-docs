---
hide:
  - navigation
  - toc
---
<style>
  .md-content__inner ul>li::before {
  content: '';
  position: absolute;
  left: 0;
  font-size: 0em;
  color: #ffb300;
  /* Amber 600 */
}

.md-content__inner h1::before {
  content: '';
}

/* H2 — основной раздел */
.md-content__inner h2::before {
  content: '';
}

/* H3 — подраздел */
.md-content__inner h3::before {
  content: '';
}

/* H4 — подподраздел (опционально) */
.md-content__inner h4::before {
  content: '';
}

</style>
# Добро пожаловать в <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span>

**<span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span>** — это платформа для написания и запуска логики управления на простом, надёжном и понятном языке **LC**.  
Она создана для тех, кто разрабатывает **умные устройства**, **контроллеры**, **IoT-решения** или **промышленную автоматику** — и хочет писать код быстро, без головной боли и сложных IDE.

---

## 🚀 Что делает <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span>:

- 🔸 Позволяет **писать управляющую логику** на языке с C-подобным синтаксисом
- 🔸 **Компилирует** код в байт-код с помощью `LCCompiler`
- 🔸 **Запускает** программы на устройстве под управлением лёгкой виртуальной машины `LCVM`
- 🔸 Обеспечивает простую **загрузку, отладку и мониторинг** через `LC2 Monitor`

---

## 🧩 Компоненты платформы

| Компонент        | Назначение                                       |
|------------------|--------------------------------------------------|
| LCCompiler       | Компилирует код LC в байт-код для микроконтроллера |
| LCVM (Runtime)   | Лёгкая и безопасная виртуальная машина на устройстве |
| LC2 Monitor      | Утилита для загрузки кода, запуска и отладки     |

---

## 📦 Пример на LC

```cs
bool Button1 @ "DI.1";
bool Relay1 @ "DO.1";

void loop() {
  Relay1 = Button1;
}
```

## 👌 Почему это удобно?  
- 📘 Просто как Arduino
- 🛠 Надёжно как ПЛК
- ⚡ Быстро и понятно для инженера и радиолюбителя

## 🔓 Лицензии  
- 🔸 **LCCompiler** — GPL-3
- 🔸 **LCVM Runtime** — BSD

## <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub logo" width="40" height="40" style="vertical-align: middle;"> Исходные коды на GitHub  
Все основные компоненты платформы LC<sup>2</sup> имеют открытые исходные коды и размещены на GitHub:

- 🛠️ [LC Compiler](https://github.com/DiMoonElec/lccompiler) — компилятор исходного кода LC в байт-код.
- ⚙️ [LC2 Monitor](https://github.com/DiMoonElec/lc2-monitor) — утилита для загрузки и отладки программ на устройстве.
- 📚 [Документация (этот сайт)](https://github.com/DiMoonElec/lc2-docs) — исходники этой документации.

---

👉 Начни с [Быстрого старта](/quickstart/) или [Изучи синтаксис языка LC](/lc-lang/)