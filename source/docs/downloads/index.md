---
hide:
  - toc
---

# Актуальные версии

## LCCompiler

**Для работы** требуется [.NET Framework 4.7.2](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net472-offline-installer).

**Версия:** 0.1.1_alpha  
**Дата релиза:** 2025-07-07  
**Скачать:** [lccompiler_0.1.1_alpha_setup.exe](/files/lccompiler/lccompiler_0.1.1_alpha_setup.exe)  

**Описание**  
Проект находится в стадии альфа-тестирования. Ожидается нестабильная работа и возможные изменения в архитектуре.

**Информация о релизе**  
Первая общедоступная alpha-версия компилятора. 

## <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> Monitor
**Для работы** требуется [.NET Framework 4.7.2](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net472-offline-installer).

**Версия:** 1.0.0  
**Дата релиза:** 2025-07-07  
**Скачать:** [LC2Monitor_v1.0.0.zip](/files/lc2monitor/LC2Monitor_v1.0.0.zip)  

**Описание**  
Реализован основной, минимально необходимый, функционал:  

- Загрузка байт-кода программы в память контроллера;
- Управление запуском проекта;
- Сохранение проекта в знергонезависимую память контроллера;
- Отображение и изменение значений переменных проекта;
- Синхронизация RTC контроллера с часами ПК;
- Отображение дампа вируальной машины LCVM.

**Информация о релизе**  
Первая общедоступная версия <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> Monitor. 


## Шаблон проекта

**Версия:** 1.0.0  
**Дата релиза:** 2025-07-07  
**Скачать:** [project_template_v1.0.0.zip](/files/project_template/project_template_v1.0.0.zip)  

**Описание**  
Шаблон проекта <span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> для VS Code под тестовую целевую платформу. Для сборки проекта установите `lccompiler`, перезагрузите ПК (для вступление в силу изменений PATH).  
Далее, откройте проект как папку в VS Code:  
![Изображение](/files/project_template/1.PNG)  
После этого, выберите Run Task -> Compile, или используйте комбинацию `Ctrl+Shift+B`.
