# Команды CLI
## Перемещение по папкам 
`cd путь к папке`<br>
`cd T01D01-1/src` - переместиться в папку `src`, которая лежит в папке `T01D01-1`<br>
`cd ..` - переместиться назад на 1 папку<br>
`cd ../../` - переместиться назад на 2 папки<br>

## Как узнать какие файлы хранятся в папке?
 1. Переходим в папку
 2. Выводим список файлов и папок в ней

`ls`

![enter image description here](https://macmaniac.ru/content/uploads/ls.jpg)

# GIT
## Клонировать репозиторий
`git clone ссылка_на_репозиторий`

Ссылку на репозитой можно найти на **GitLab**, **GitHub**. Например такая:<br>
`git clone https://github.com/wanderer-00/GIT-manual.git`

## Ветки
### Создание
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
### Проссмотр веток
```bash
git branch
```
```bash
shanikal@et-l3 T01D01-1 % git branch
  develop
* master
```
В репозитории 2 ветки <b>develop</b> и <b>master</b>
