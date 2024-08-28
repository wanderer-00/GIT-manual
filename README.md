# Команды CLI
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
        <td>cd</td>
        <td>перемещение по папкам</td>
    </tr>
    <tr>
        <td>mkdir</td>
        <td>создание папки</td>
    </tr>
    <tr>
        <td>rm -rf</td>
        <td>удаление папки</td>
    </tr>
    <tr>
        <td>rmdir</td>
        <td>удаление папки</td>
    </tr>
    <tr>
        <td>touch</td>
        <td>создание файла</td>
    </tr>
    <tr>
        <td>rm</td>
        <td>удаление файла</td>
    </tr>
</table>

## Перемещение по папкам 
`cd путь к папке`<br>
`cd T01D01-1/src` - переместиться в папку `src`, которая лежит в папке `T01D01-1`<br>
`cd ..` - переместиться назад на 1 папку<br>
`cd ../../` - переместиться назад на 2 папки<br>

## Как узнать какие файлы хранятся в папке?
 1. Переходим в нужную папку `cd имя_папки`
 2. Выводим список файлов и папок в ней `ls`

```bash
shanikal@et-l3 ~ % cd T01D01-1         
shanikal@et-l3 T01D01-1 % ls
CHANGELOG	README.md	code-samples	datasets	misc
LICENSE		README_RUS.md	data-samples	materials	src
```

# GIT
<table>
    <tr>
        <th>Команда</th>
        <th>Описание</th>
    </tr>
    <tr>
        <td>git clone ссылка_на_репозиторий</td>
        <td>копирование репозиторя на ПК</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
    </tr>
</table>
> <a href="#clone-rep">Клонировать репозиторий</a><br>
> <a href="#branch">Ветки</a>
>> <a href="#branch-creating">Создание ветки</a><br>
>> <a href="branch-watch">Проссмотр веток</a><br>
>> <a href="#">Смена ветки</a><br>
<a href="#"></a>
<a href="#"></a>
<a href="#"></a>
<a href="#"></a>
<a href="#"></a>

## <a id="clone-rep">Клонировать репозиторий</a>
`git clone ссылка_на_репозиторий`

Ссылку на репозитой можно найти на **GitLab**, **GitHub**. Например такая:<br>
`git clone https://github.com/wanderer-00/GIT-manual.git`

## <a id="branch">Ветки</a>
### <a id="branch-creating">🧩 Создание ветки</a>
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

```bash
shanikal@et-l3 T01D01-1 % git branch
  develop
* master
```
В репозитории 2 ветки: `develop` и `master`<br>
При этом главной выбрана ветка `master` (отмечена звездочкой)

### ♻️ Смена ветки
Смени ветку и все изменения проекта будут в ней
```bash
git checkout имя_ветки
```
 
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
