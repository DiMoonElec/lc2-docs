---
hide:
  - toc
---

# Актуальные версии

**Для работы** требуется [.NET Framework 4.7.2](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net472-offline-installer).

<div class="app-release" data-json="/files/lccompiler/releases.json" data-path="/files/lccompiler/">
  <h2>LCCompiler</h2>
  <strong>Версия:</strong> <span class="version"></span><br>
  <strong>Дата релиза:</strong> <span class="date"></span><br>
  <strong>Информация о релизе:</strong> <span class="description"></span><br><br>
  <strong>Скачать:</strong> <a class="download" download>Скачать EXE</a>
</div>

<div class="app-release" data-json="/files/lc2monitor/releases.json" data-path="/files/lc2monitor/">
  <h2><span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> Monitor</h2>
  <strong>Версия:</strong> <span class="version"></span><br>
  <strong>Дата релиза:</strong> <span class="date"></span><br>
  <strong>Информация о релизе:</strong> <span class="description"></span><br><br>
  <strong>Скачать:</strong> <a class="download" download>Скачать EXE</a>
</div>

<div class="app-release" data-json="/files/project_template/releases.json" data-path="/files/project_template/">
  <h2>Шаблон проекта</h2>
  <strong>Версия:</strong> <span class="version"></span><br>
  <strong>Дата релиза:</strong> <span class="date"></span><br>
  <strong>Информация о релизе:</strong> <span class="description"></span><br><br>
  <strong>Скачать:</strong> <a class="download" download>Скачать zip</a>
</div>

<script>
document.querySelectorAll('.app-release').forEach(block => {
  const jsonUrl = block.dataset.json;
  const basePath = block.dataset.path;

  fetch(jsonUrl)
    .then(res => res.json())
    .then(data => {
      const latest = data[0];
      block.querySelector('.version').textContent = latest.version;
      block.querySelector('.date').textContent = latest.date;
      block.querySelector('.description').innerHTML = latest.description.replace(/\n/g, "<br>");
      const downloadLink = block.querySelector('.download');
      downloadLink.href = basePath + latest.filename;
      downloadLink.textContent = latest.filename;
    })
    .catch(err => {
      block.innerHTML = "<em>Ошибка загрузки информации о релизе.</em>";
      console.error(err);
    });
});
</script>