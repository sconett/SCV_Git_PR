# Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19/SCV_Git_PR"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---


![Logo](Git-Logo-2Color.png)
# Работа с Git и GitHub

## 1. Проверка наличия установленного Git
В терминале выполнить команду `git --version`.
Если Git установлен появится сообщение с информацией о версии программы, иначе будет сообщение об ошибке.

## 2. Установка Git
Загружаем последнюю версию `Git` с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании `Git` необходимо представиться. Для этого в терминале нужно ввести две команды:
```
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```

## 4. Инициализация репозитория
Для создания нового репозитория используется команда 
```
git init
```
Команду **git init** выполняют только один раз для первоначальной настройки нового репозитория. Выполнение данной команды приведет к созданию нового подкаталога **.git** в вашем рабочем каталоге, а также будет создана новая главная ветка.

## 5. Запись изменений в репозитории
Основной инструмент, используемый для определения, какие файлы в каком состоянии находятся и каким изменениям были подвержены — это команда 
```
git status
```
С ее помощью можно проверить индексацию изменений и увидеть файлы, которые не отслеживаются `Git`.

## 6. Просмотр историй коммитов
После того, как вы создали несколько коммитов или же клонировали репозиторий с уже существующей историей коммитов, вероятно вам понадобится возможность посмотреть что было сделано — историю коммитов.

Одним из основных и наиболее мощных инструментов для этого является команда
```
git log
```
## 7. Перемещение между сохранениями
```
git checkout
```
Команда **git checkout** позволяет перемещаться между ветками, созданными командой ***git branch***.

При переключении ветки происходит обновление файлов в рабочем каталоге в соответствии с версией, хранящейся в этой ветке, а `Git` начинает записывать все новые коммиты в этой ветке.

## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенные файлы и папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 9. Создание веток в Git
По умолчанию имя основной ветки в `Git` - *master*.
Создать ветку можно командой:
```
git branch <имя новой ветки>
```
Список веток в репозитории можно посмотреть с помощью команды 
```
git branch
```
Текущая ветка будет отмечена звездочкой: **\*master**

## 10. Слияние веток
Слияние используется в `Git`, чтобы собрать воедино разветвленную историю.
```
git merge
```
Команда ***git merge*** выполняет слияние отдельных направлений разработки, созданных с помощью команды **git branch**, в единую ветку.

## 11. Разрешение конфликтов

Обычннно конфликты возникают, когда два человека изменяют одни и те же строки в файле или один разработчик удаляет файл, который в это время изменяет другой разработчик. В таких случаях `Git` не может автоматически определить, какое изменение является правильным.

`Git` выводит небольшое описательное сообщение о возникновении конфликта. Чтобы получить более глубокое понимание проблемы, можно запустить команду **git status**.
```
git status
```
Команда ***git status*** часто используется во время работы с Git и помогает идентифицировать конфликтующие во время слияния файлы.
```
git log merge
```

При передаче аргумента **--merge** для команды **git log** будет создан журнал со списком конфликтов коммитов между ветками, для которых выполняется слияние.
```
git diff
```
Команда **diff** помогает найти различия между состояниями репозитория/файлов. Она полезна для выявления и предупреждения конфликтов слияния.
```
git merge --abort
```
При выполнении команды **git merge** с опцией **--abort** процесс слияния будет прерван, а ветка вернется к состоянию, в котором она находилась до начала слияния.
```
git reset
```
Команду **git reset** можно использовать для разрешения конфликтов, возникающих во время выполнения слияния, чтобы восстановить заведомо удовлетворительное состояние конфликтующих файлов.

### 12. Удаление веток
Удалить ветку можно параметром branch с добавлением флага -d и указанием имени ветки. Если вы завершили работу над веткой и объединили её с основной, можно её удалить без потери истории. Однако, если выполнить команду удаления до слияния — в результате появится сообщение об ошибке. Этот защитный механизм предотвращает потерю доступа к файлам.
```
git branch -d existing_branch_name
```
Для принудительного удаления ветки используется флаг -D с заглавной буквой. В этом случае ветка будет удалена независимо от текущего статуса, без предупреждений.
```
git branch -D existing_branch_name
```
Вышеуказанные команды удаляют только локальную копию ветки. В удалённом репозитории она может сохраниться. Если хотите стереть удалённую ветку, выполните следующую команду:
```
git push origin --delete existing_branch_name
```
## 13. Работа с удаленными репозиториями

Инструкция по применению:
1. Создать аккаунт на **`GitHub`**
2. Создать локальный репрозиторий
3. Создать удаленный репрозиторий
4. Связать локальный репрозиторий с локальным

Добавить удаленный репозиторий к проекту :
```
git remote add <имя репозитория> <адрес репозитория в сети>
```
Для получения и слияния изменений из удаленного репозитория используется команда :
```
git pull
```
Добавление из локального репозитория в удаленный репозиторий используется команда :
```
git push
```
После выгрузки из локального репозитория необходимо пройти в свой `GitHub` и пройти по зеленым кнопкам **Pull Request** , если кнопок нет перейти в вкладку pull request выбрать ветку где была конфигурация и пройти по зеленым кнопкам.

## 14. Создание экземпляра репозитория на `GitHub`

Сначала необходимо нажать на кнопку "**Fork**" в верху страницы нужного нам репозитория. Таким образом вы создадите экземпляр всего репозитория в своем аккаунте на `GitHub`.

Откройте терминал и запустите следующую команду
```
git clone <url-адрес репозитория>
```
С ее помощью репозиторий будет клонирован на ваш компьютер.

Далее переходим в клонированную директорию:
```
cd <имя репозитория>
```

## 15. Создание **pull request**
Перейдите в свой репозиторий, созданный с помощью **Fork**. Там есть кнопка «Compare & pull request» — кликните ее.

Отобразиться форма, в которой можно введсти необходимые детали относительно того, что именно вы сделали. После этого можно нажать кнопку подтверждения внизу. 