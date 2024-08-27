# Оглавление
<table>
    <tr>
        <th>Команда</th>
        <th>Описание</th>
    </tr>
    <tr>
        <td>ls</td>
        <td>список файлов и папок</td>
    </tr>
    <tr>
        <td>cd путь</td>
        <td>перемещение по папкам</td>
    </tr>
    <tr>
        <td>mkdir имя_папки</td>
        <td>создание папки</td>
    </tr>
    <tr>
        <td>rmdir имя_папки</td>
        <td>удаление папки</td>
    </tr>
    <tr>
        <td>touch название_файла</td>
        <td>создание файла</td>
    </tr>
    <tr>
        <td>rm название_файла</td>
        <td>удаление файла</td>
    </tr>
</table>



# Команды CLI
## Перемещение по папкам 
`cd путь к папке`<br>
`cd T01D01-1/src` - переместиться в папку `src`, которая лежит в папке `T01D01-1`<br>
`cd ..` - переместиться назад на 1 папку<br>
`cd ../../` - переместиться назад на 2 папки<br>

## Как узнать какие файлы хранятся в папке?
 1. Переходим в нужную папку
 2. Выводим список файлов и папок в ней

```bash
shanikal@et-l3 ~ % cd T01D01-1         
shanikal@et-l3 T01D01-1 % ls
CHANGELOG	README.md	code-samples	datasets	misc
LICENSE		README_RUS.md	data-samples	materials	src
shanikal@et-l3 T01D01-1 %
```

![enter image description here](https://macmaniac.ru/content/uploads/ls.jpg)

# GIT
## Клонировать репозиторий
`git clone ссылка_на_репозиторий`

Ссылку на репозитой можно найти на **GitLab**, **GitHub**. Например такая:<br>
`git clone https://github.com/wanderer-00/GIT-manual.git`

## Ветки
### 🧩 Создание ветки
1. Перейти в папку репозитория `cd путь_к_папке_репозитория`
2. Создать ветку `git branch имя_ветки`

```bash
cd T01D01-1
git branch develop
```
```bash
shanikal@et-l3 ~ % cd T01D01-1 
shanikal@et-l3 T01D01-1 % git branch develop
```
В консоли ничего нет, как понять, что ветка создалась?
### 👁️ Проссмотр веток
```bash
git branch
```

<details>
  <summary>пример использования</summary>

```bash
shanikal@et-l3 T01D01-1 % git branch
  develop
* master
```
В репозитории 2 ветки: `develop` и `master`<br>
При этом главной выбрана ветка `master` (отмечена звездочкой)
</details>

### ♻️ Смена ветки
Смени ветку и все изменения проекта будут в ней
```bash
git checkout имя_ветки
```
<details>
  <summary>пример использования</summary>
 
```bash
shanikal@et-l3 T01D01-1 % git checkout develop
M	src/ai_door_management_module.sh
M	src/ai_initial_module.sh
M	src/ai_module_2.sh
M	src/important_data_for_ai_module_2.txt
Switched to branch 'develop'
shanikal@et-l3 T01D01-1 % git branch
* develop
  master
```
</details>

### &#10060; Ошибки при попытке просмотреть, создать или сменить ветку?
```bash
shanikal@et-l3 ~ % git branch
fatal: not a git repository (or any parent up to mount point /Users)
Stopping at filesystem boundary (GIT_DISCOVERY_ACROSS_FILESYSTEM not set).
```
Вы находитесь <b>не в папке</b> репозитория

<details>
  <summary>Справочные материалы</summary>
<a href='https://gist.github.com/Jekins/2bf2d0638163f1294637'>Инструкция по MarkDown</a>
</details>
