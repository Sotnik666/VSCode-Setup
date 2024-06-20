# VSCode Setup
<h3>В данном руководстве описана настрока VSCode и его плагинов для удобной работы с Azure Git</h3>

# Необходимые ссылки
<table>
<li><a href="https://code.visualstudio.com/" target="_blank">Visual Studio Code</a></li>
<h3>Плагины</h3>
<li><a href="https://marketplace.visualstudio.com/items?itemName=ankitbko.vscode-pull-request-azdo" target="_blank">Azure Devops Pull Requests</a> - работа с PR внутри VSCode просмотр/редактирование/утверждение/отмена</li>
<li><a href="https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph" target="_blank">Git Graph</a> - просмотр взаимодействия с модулем, кто что создал, из каких веток куда смержил</li>
<li><a href="https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens" target="_blank">GitLens — Git supercharged</a> - большой пак модулей для VSCode, много функционала, тонкая настройка</li>
</table>

# Настройка
Данный блок описывает общую первоначальную настройку для всех разработчиков, это позволит со старта быть со схожим рабочим пространством, чтобы не путаться.
<h3>Базовая настройка VSCode</h3>
** Текст выделенный в "кавычках" означает необходимость вписать его в текстовое поле

<h4>Настройка языка:<h4>

    VSCode -> F1 -> "Configure display language" -> English
<h4>Настройка папок для скачивания проектов:<h4>

    Создаем локальную папку для проектов
    VScode -> F1 ->  "Open user settings (JSON)" -> ищем 
    "files.dialog.defaultPath" и "git.defaultCloneDirectory"
    Если поля не найдены, создаем их
    вписываем значение нашей локальной папки в виде: "C:\\localFolder\\git" 
    Обязательно двойные слеши и кавычки

<h3>Настройка расширений</h3>
<h4>Настройка Azure Devops Pull Requests</h4>

    VSCode -> F1 -> "Open user settings" -> "@ext:ankitbko.vscode-pull-request-azdo"
    
    Azdo Pull Requests: Org Url      = ссылка на коллекцию
    Azdo Pull Requests: Project Name = название проекта
    Azdo Pull Requests: Pat Token    = создать токен в tfs 
    Azdo Pull Requests: Remotes      = origin

    Как создать токен:
    ссылка на коллецию + /_usersSettings/tokens -> новый маркер -> вводим любое удобно вам имя ->
    окночание срока "специально отпределенное" -> в календаре максимально доступная дата  -> полный доступ -> Создать

<h4>Настройка Git Graph</h4>

    По желанию, по дефолту все неплохо настроено
    VSCode -> F1 -> "Open user settings" -> "@ext:mhutchie.git-graph"

<h4>Настройка GitLens</h4>

Есть заготовленная стартовая настройка, которую в дальнейшем можно поменять под по себя

    VSCode -> F1 -> "Open user settings (JSON)"

В открывшимся окне вставляем
<details>
  <summary>JSON для копирывания</summary>

  ```
  "gitlens.views.remotes.branches.layout": "list",
    "gitlens.blame.compact": false,
    "gitlens.gitCommands.skipConfirmations": [
        "fetch:command",
        "stash-push:command",
        "switch:command"
    ],
    "gitlens.hovers.currentLine.over": "line",
    "gitlens.blame.format": "${author||10} ${date}",
    "gitlens.blame.highlight.locations": [
        "gutter",
        "line",
        "overview"
    ],
    "gitlens.blame.heatmap.enabled": false,
    "gitlens.changes.locations": [
        "overview"
    ],
    "gitlens.menus": {
        "editor": {
            "blame": true,
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": true
        },
        "editorGroup": {
            "blame": true,
            "compare": true
        },
        "editorGutter": {
            "compare": true,
            "remote": true,
            "share": true
        },
        "editorTab": {
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": true
        },
        "explorer": {
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": true
        },
        "ghpr": {
            "worktree": true
        },
        "scm": {
            "graph": true
        },
        "scmRepositoryInline": {
            "graph": true,
            "stash": false
        },
        "scmRepository": {
            "authors": true,
            "generateCommitMessage": true,
            "patch": true,
            "graph": false
        },
        "scmGroupInline": {
            "stash": true
        },
        "scmGroup": {
            "compare": true,
            "openClose": true,
            "patch": true,
            "stash": true
        },
        "scmItemInline": {
            "stash": false
        }
    },
  ```
</details>

Настройка проводится через интерфейс GitLens

    GitLens -> GitLens Settings
