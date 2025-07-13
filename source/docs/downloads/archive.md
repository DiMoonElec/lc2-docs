---
hide:
  - toc
---
<!--
<style>
.release-table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 2em;
}

.release-table th, .release-table td {
  border: 1px solid var(--md-default-fg-color--lightest, #ccc);
  padding: 0.5em;
  vertical-align: top;
}

.release-table th {
  background-color: var(--md-default-bg-color--lighter, #eee);
  color: var(--md-default-fg-color, #000);
  text-align: left;
  font-weight: bold;
}

@media (prefers-color-scheme: dark) {
  .release-table th {
    background-color: #1f1f1f;
    color: #eee;
  }

  .release-table td {
    border-color: #444;
  }
}
</style>
-->
<style>
.release-table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 2em;
  table-layout: auto;
}

.release-table th, .release-table td {
  border: 1px solid var(--md-default-fg-color--lightest, #ccc);
  padding: 0.5em;
  padding-left: 0.7em;
  padding-right: 0.9em;
  vertical-align: top;
  text-align: left;
}

.release-table th:nth-child(1),
.release-table td:nth-child(1) {
  white-space: nowrap;
}

.release-table th:nth-child(2),
.release-table td:nth-child(2) {
  white-space: nowrap;
}


.release-table th:nth-child(3),
.release-table td:nth-child(3) {
  width: 100%; /* занимает всё оставшееся */
}

.release-table th:nth-child(4),
.release-table td:nth-child(4) {
  white-space: nowrap;
}

@media (prefers-color-scheme: dark) {
  .release-table th {
    background-color: #1f1f1f;
    color: #eee;
  }

  .release-table td {
    border-color: #444;
  }
}
</style>


<div class="app-archive" data-json="/files/lccompiler/releases.json" data-path="/files/lccompiler/">
  <h3>LC Compiler</h3>
  <table class="release-table">
    <thead>
      <tr>
        <th>Версия</th>
        <th>Дата</th>
        <th>Изменения</th>
        <th>Скачать</th>
      </tr>
    </thead>
    <tbody></tbody>
  </table>
</div>

<div class="app-archive" data-json="/files/lc2monitor/releases.json" data-path="/files/lc2monitor/">
  <h3><span style="display: inline-block; position: relative;">LC<span style="position: relative; top: -0.25em;">2</span></span> Monitor</h3>
  <table class="release-table">
    <thead>
      <tr>
        <th>Версия</th>
        <th>Дата</th>
        <th>Изменения</th>
        <th>Скачать</th>
      </tr>
    </thead>
    <tbody></tbody>
  </table>
</div>

<div class="app-archive" data-json="/files/project_template/releases.json" data-path="/files/project_template/">
  <h3>Шаблон проекта</h3>
  <table class="release-table">
    <thead>
      <tr>
        <th>Версия</th>
        <th>Дата</th>
        <th>Изменения</th>
        <th>Скачать</th>
      </tr>
    </thead>
    <tbody></tbody>
  </table>
</div>

<script>
document.querySelectorAll('.app-archive').forEach(block => {
  const jsonUrl = block.dataset.json;
  const basePath = block.dataset.path;
  const tbody = block.querySelector('tbody');

  fetch(jsonUrl)
    .then(res => res.json())
    .then(data => {
      data.forEach(entry => {
        const tr = document.createElement('tr');

        const version = document.createElement('td');
        version.textContent = entry.version;

        const date = document.createElement('td');
        date.textContent = entry.date;

        const desc = document.createElement('td');
        desc.innerHTML = entry.description.replace(/\n/g, '<br>');

        const link = document.createElement('td');
        const a = document.createElement('a');
        a.href = basePath + entry.filename;
        a.download = '';
        a.textContent = 'Скачать';
        link.appendChild(a);

        tr.appendChild(version);
        tr.appendChild(date);
        tr.appendChild(desc);
        tr.appendChild(link);

        tbody.appendChild(tr);
      });
    })
    .catch(err => {
      tbody.innerHTML = `<tr><td colspan="4"><em>Ошибка загрузки архива.</em></td></tr>`;
      console.error(err);
    });
});
</script>
