![](https://git-scm.com/images/logos/1color-darkbg@2x.png)
 # My Git Tutorial
## __Markdown__
Markdown - облегченный язык разметки. Создан в 2004 году писателем и блогером Джоном Грубером.
### __Базовый синтаксис__
* #### __Заголовки__
Заголовки создаются при помощи символа решетка.  Уровень заголовка определяется количеством решеток перед ним. Всего их может быть шесть. 

* #### __Форматирование__
Текст можно сделать курсивным или жирным с помощью нижних подчеркиваний и звездочек.


* #### __Списки__

Маркированные списки делаются при помощи дефиса, проставляемого перед каждым пунктом.
Нумерованные списки создаются при помощи цифр.

* #### __Горизонтальные линии__
Три раза ввести символ звездочка или дефис
* #### __Ссылки__
Ссылку можно вставить при помощи круглых скобок, при этом заголовок к ссылке указывается в квадратных скобках.
* #### __Цитаты__
Абзац в цитату выделяют при помощи угловой скобки. Ее нужно ставить перед каждой строчкой цитаты.
* #### __Выделение__
Часть теста можно выделить при помощи одиночных обратных кавычек. 
___
## __Intro to Git__
Для того, чтобы начать пользоваться Git, необходимо установить [Git](https://git-scm.com/download/mac) на компьютер.
Также для работы понадобится [Visual Studio Code](https://code.visualstudio.com).

При создании нового проекта необходимо сначала создать новый репозиторий. Для этого на компьютере создаем папку, далее открываем ее при помощи Проводника VS Code.

Из проводника создаем новый файл, присваиваем имя с расширением.

Управление версиями происходит из коммандной строки.

## **Команды Git**

`git --version` - показывает текущую версию Git 

*`git config --global user.name "name"`* - задает имя для коммитов

*`git config --global user.email "email@abc.com"`* - задает почту для коммитов

*`git init`* - инициализирует репозиторий

*`git add`* - подготавливает файл к сохранению

*`git commit`* - сохраняет изменения в файле

*`git commit -m "Your short summary about the commit"`* - сохраняет изменения с комментариями

*`git status`* - показывает статус репозитория

*`git log`* - показывает историю изменений (сначала и до текущего момента!) 

*`git checkout имя ветки`* - перемещает между ветками

*`git checkout первые несколько символов коммита`* - перемещает к запрашиваемой сохраненной версии

*`git checkout master`* - перемещает к актуальной версии файла

*`git diff`* - показывает разницу между сохраненной версией файла и текущей

*`git branch название`* - создает новую ветку

*`git branch`* - показывает все ветки, звездочкой отмечает текущую

*`git merge название ветки`* - добавляет к текущей ветке другую ветку

*`git branch -d название`* удаляет ветку

*`git log --graph`* - выводит список коммитов в виде графа

*`git commit --amend -m"Новый комментарий"`* - меняет комментарий к последнему коммиту 

## **Работа с терминалом**
Вызвать терминал в VS Code можно из меню View -> Terminal.

Чтобы не писать команды заново, можно пользоваться стрелками вверх - вниз на клавиатуре.

Чтобы очистить терминал, нужно ввести команду *`clear`*.

Чтобы втоматически подставить название файла, используем клавишу *`Tab`*.

Посмотреть и изменить все возможные комбинации клавиш можно из меню Code -> Preferences -> Keyboard Shortcuts.

## **Работа с ветками**
### __Создание веток__
1. Для создания новой ветки используется команда *`git branch имя_ветки`*
2. Для перехода между ветками используется команда *`git checkout имя_ветки`*
3. Для того чтобы создать новуюветку и сразу переключиться на нее используем команду *`git checkout -b имя_ветки`*
### __Слияние веток__
1. Слияние веток происходит путем добавления в текущую ветку
2. Для слияния веток используется команда *`git merge название ветки`* 
3. Далее команда *`git add`*
4. Сохраняем *`git commit -m "Your short summary about the commit"`* 
5. Переходим в ветку, в которую хотим добавить информацию *`git checkout master`*
6. Сливаем

Еще одним способом перекинуть изменения из одной ветки в другую является команда  *`git rebase название ветки`*. Такой способ называется перебазированием 
### Конфликты при слиянии и их разрешения
1. Конфликты возникают при наличии противоречащих коммитов
2. После разрешения конфликта файл нужно закоммитить

Смоделируем конфликт слияния.

Попытка №1.
В ветку Мастер были внесены изменения: нумерованные списки поменяли на заголовки. Изменения не были сохранены. 

Далее создали новуюветку branch_conflicts и в ней также поменяли элемент нумерованного списка на заголовок и добавили этот текст. При слитии получаем сообщение Уже обновлено

Попытка №2 
В созданной ветке conflict_log добавлен этот параграф. В попытке №1 изменен текст (Мастер вместо master, добавлен перенос текста). Переключаемся обратно на мастер. Добавляем это предложение. Пробуем слить. Снова сообщение Уже обновлено

Попытка №3

Пробуем снова изменить conflict_log и слить. Конфликт! Задача выполнена

### __Удаление веток__

Для удаление ветки необходимо выполнить команду *`git branch -d название`* . 

Такая команда не будет выполнена, если ветка, которую мы хотим удалить еще не была слита.
Для удаления неслитой ветки используется команда *`git branch -D название`* . 

### __Дополнительная информация__ 

Для того, чтобы посмотреть последний коммит в каждой ветке, выполняем команду *`git branch -v`* 

Чтобы посмотреть те ветки, которые уже были слиты с текущей, используется команда *`git branch -merged`* 

Чтобы посмотреть ветки, которые еще не были слиты в текущую, вызываем команду *`git branch --no-merged`* 

Чтобы посмотреть разницу между ветками, запускаем команду *`git diff имя_ветки1 имя_ветки2`* 

![](https://avatars.githubusercontent.com/u/9919?s=280&v=4) 
# GitHub Tutorial

1. Создаем новый репозиторий на [GitHub](https://github.com). 
2. Добавляем в терминале новый сервер для Git, куда будем отправлять файлы проекта `git remote add origin https://ссылка на репозиторий GitHub`.
3. Если терминал выдает ошибку "внешний репозиторий origin уже существует", можно поменять ссылку на репозиторий `git remote set-url origin *new_link*`.
4. Проверяем, что сервер добавился `git remote -v`.
5. Теперь можно пушить проект на GitHub. В терминале набираем `git push -u origin master`
6. При первом добавлении файла GitHub нужно связать с Git, поэтому Git запросит авторизацию GitHub (ввести пароль аккаунта). После ввода пароля файл будет добавлен на GitHub.
7. Если изменения в файл были внесены на сайте, нужно обновить локальный репозиторий при помощи команды `git pull`. Кроме команды git pull для получения изменений используется команда `git fetch`. Она отличается от первой тем, что при `git pull` все изменения автоматически сливаются с файлом, а `git fetch` дает возможность сначала просмотреть все изменения и только потом слить их при помощи команды `git merge`. По сути `git pull` - это объединенные команды `git fetch` и `git merge`
8. Для того, чтобы скоприровать себе репозиторий другого пользователя, используем функцию `Clone` на сайте
![](https://docs.github.com/assets/cb-33207/images/help/repository/https-url-clone-cli.png)
9. Для того, чтобы получить возможность предлагать свои изменения к репозиториям других пользователей, используем функцию `Fork` на сайте

![](https://docs.github.com/assets/cb-6294/images/help/repository/fork_button.jpg)

## Создание Pull Request
1. Форкаем репозиторий
2. Создаем свою ветку - важно вносить изменения в отдельной ветке, тк в pull request автоматически будут добавляться все изменения, сделанные в ветке.
3. Вносим изменения
4. Делаем Pull Request 
5. Добавляем ОченьВажныйКомментарий
6. Отправляем

## Клонирование репозитория через терминал
1. На сайте копируем адрес репозитория
2. В терминале запускаем команду `git status`, чтобы проверить, что мы находимся не в репозитории. НЕ СОЗДАВАТЬ РЕПОЗИТОРИЙ ВНУТРИ РЕПОЗИТОРИЯ! 
3. Для создания нового репозитория создаем новую папку на компьютере. Открываем ее в  VS Code File -> Open folder. 
4. Снова запускаем компанду `git status`, чтобы проверить, что мы не в репозитории. 
5. Если все хорошо, в терминале запускаем команду `git clone скопированная ссылка`. 
6. При попытке перейти на любую ветку созданного репозитория, должна возникнуть ошибка fatal: не найден git репозиторий (или один из родительских каталогов): .git Ошибка говорит о том, что мы не находимся в репозитории. Поэтому следующим шагом переходим в созданную на шаге 3 папку.
7. Переходим внутрь созданной папки при помощи команды `cd начинаем вводить имя Tab`

Вот и все

