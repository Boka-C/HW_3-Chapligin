# Git instruction

## 1. Program availibility check: 
In a Visual code go to Terminal (Ctrl+`) and type the ```git version``` command, if Git is installed correctly, you will see its version (ex.: *git version 2.39.0.windows.1*), if not, you will see the error message and will have to install Git (go to paragraph 2). 
## 2. Installing Git:
Follow the link https://git-scm.com/downloads and download the version compatible with your device.
Install the program with default settings.
## 3. Introducing yourself to GIT: 
After installing the program, you have to introduce yourself to Git, so it'll know who's saving the versions.
To do that, you need to open Terminal (*in VS for example*) again (Ctrl+`) and run 2 commands:

```git config --global user.name «Your name with Latin letters»```

and

```git config --global user.email «Your e-mail» ```

Now Git knows you, and you can use all its abilities. To start controlling versions, first, you need to create a repository - folder, with the "magical" power of Git.

## 4. Creating a repository:
You can add an already existing folder under the Git control, or you can use the VC File menu to create a new folder\file.

![File menu and options to add or create file](Git_start.png)

*Don't forget to point out the file's extension after . if you are creating new file *(ex.: .md or .txt etc.)*

As an option, you can use the *Get Started* menu in VC if you just started working in it. 

## 5. Initializing repository

To inicialize versions tracking we have to inicialize our file, to do that just type in terminal (ctrl+` - if it's closed) command:

 ```git init```

 ![How it looks in terminal (bash)](Git_init.jpg)

 Here we go, Git knows which folder it has to track, but keep in mind, that the file's versions aren't recording yet.

 ## 6. Adding file

 Thins our file is already in the repository, we can check its status, to do that we use the command:

 ```git status```

 Probably, you will see the message, that you have 1 untracked file. To add our file for tracking, we need to use the command:

```git add [your file]```

*You can type only the first 4 symbols of your file's name and press the Tab button so Git will type it for you*

If you don't see any errors or mistakes, that means, that now our file is tracking, and we are ready to go.

After adding the file, we can check its status again, just to insure, that everything works.

![How git add and git status look](Git_add%2Bstatus.jpg)

Here we go! Now, all new changes will be ready to commit. But keep in mind that, **you have to save all the changes in the file by typing Ctrl + s or turn on the Auto save function through the File menu in VC.**

## 7. Committing your actions.

 We already know, how to add a file to the repository, but Git's magic still doesn't work properly - it just doesn't have any commits, so it can't understand which versions of the file you have. 
 After typing several lines, or even symbols, if you think that it's good enought to become one of the versions of your file, you will commit them by using the command:

 ```git commit -m "[your comment]"```

 -m is a kind of message, so just type shortly, what have you done with your file (but usually, the first commit is named > initial commit ), and don't forget to put your comments inside of quotes ".

***Don't forget to check git status sometimes, and if there are any issues, use the git add function before committing.***

## 8. Can we see the changes?

Till Git is controlling all the committed versions of our folder and files in it, we can see which lines or symbols did we change since the last commit. To see that, we need to use comand: 

```git diff```

![How does the command git diff looks](Git_diff.jpg)

So you can see the difference between the last committed and yet uncommitted version of your file, where added/changed/deleted lines are marked with different colors. 

## 9. Can we see commit's history? 

Now, when we have several commits we can see all of them with the changes and our comments. To do that just type and submit in the terminal command:

```git log``` 

You will see all your changes and commit details, like author, date, and comment. pay attention that all of the commits have their own hash number, due to which it can be identified. 

![How git log looks in terminal](Git_log.jpg)


But if the history is too long and you just need to see it shorter, you always can use the command:

```git log --oneline```

In that case, you'll see only the beginning of the commit's number and your comment.

 *Don't forget to use "--" symbels before the > oneline atribute.*

 ![Short version of logs](Git_log_short.jpg)

## 10. Can we see only comments from previous versions? 

Git gives you the ability to switch between the versions of your file, so you will have all the committed versions safe, and you still can see one of the previous versions. To do that, you need the command git checkout and the first 4-7 numbers of the commit's hash number (you can check them by using ```git log --oneline``` command), for ex.: 

``` git checkout 276f43d ```

So you can switch between the versions, without harming any of them.

**Keep in mind, that in the switched version, logs will be valid only for that version, which was created before your recent one. To see the recent version you can use the ```git checkout - ``` command.**

## 11. Добавление изображения

Для добавления изображения, оно должно находиться в папке репозитории; Указывая символы  > ``` ! [ ] ( ) ``` мы добавляем изображение. внутри квадратных скобок ``` [ ] ``` пишем описание картинки, которое будет отображаться в случае, если картинка не загрузиться, а в круглых скобках ```( )``` указываем относительный путь изображения (можно скопировать кликнув правой кнопкой мыши на файл в проводнике VSC).

На пример:

![Скрин_примера](ex.logo.jpg) 

![Git logo](1color-darkbg@2x.png)

Но файлы не принято отслеживать, поэтому чаще всего их добавляют в список игнорирования. Для создания списка игнорирования нужно создать в рабочей папке новый файл с названием ```.gitignore``` и в нем указать названия файлов для игнорирования с расширениями и каждый файл на отдельной строчке. Если мы все сделали правильно, то VSC подсветит их серым цветом и гит перестанет их отмечать как несохраненные.

![Git ignore example](Git_ignore.png)

Также мы можем добавить в игнорирование все файлы 1 типа, для этого в списке игнорирования указываем > *. и расширение файла (png/jpg и т.д.) 

```
*.png
```

## 12. Создание веток в Git

Для проверки существующих веток используем команду ```git branch``` (по умолчанию создаётся ветка мастер, обычно выделена цветом и т.к. она единственная то она же и та, в которой мы находимся, об этом говорит знак * ).

Для создания новой ветки пишем ```git branch  branch_name``` где branch_name это название новой ветки.

После создания, для начало работы в ней, пишем команду ```git checkout branch_name``` 

Новые ветки можно использовать как черновики.

Для переноса информации из дополнительной ветки в ветку **\*master** нужно перейти в главную ветку (мастер) и выполнить команду:

 ``` 
 git merge branch_name 
 ```

 Список веток можно посмотреть командой ``git branch``.

Для того, что-бы создать и сразу переключиться на ветку, можно сразу набрать команду ```git checkout -b branch_name" 

 ## 13. Конфликт при слиянии.

 Если информация в ветке мастер, и в ветки которую мы пытаемся слить с ней различается (построчно), то при попытке слияния может произойти конфликт. VSC предложит разрешить конфликт Либо выбрав одну из версий (текущею или входящею), либо сохранив обе версии. 

 ![Conflict example](Conflict.jpg)

Не забываем закоммитить все, после слияния.

## 14. Удаление веток

Для удаления веток после слияния нужно набрать команду: 
```
git branch -d branch_name
```
В случае если в ветке есть несохраненные и не влитые в ветку master изменения, гит сообщит об этом. Мы можем посмотреть разницу, внести изменения сохранить и закоммитить их командой > git commit -am "", влить все изменения в ветку мастер и только после разришения всех конфликтов беспрепятственно удалить ненужную ветвь.
Либо, если нам не нужны все изменения и вся информация в ветви, мы можем принудительно удалить всю ветвь используя команду 
```
git branch -D branch_name 
```
Напомню, что и в одном и в другом случае, мы должны находиться НЕ в той ветки которую удаляем (для проверки всегда можно использовать команду ```git branch```). 

## 15. Работа с удаленным репозиторием.

Для работы  с удаленным репозиторием необходимо иметь аккаунт на https://github.com/, рядом с иконкой профиля есть знак + с помощью которого можно создать репозиторий:

![New_repository_icon](new_rep.jpg) 

Необходимо выбрать один из 3 вариантов:

* Создание нового репозитория в командной строке
* "толкнуть" (push) существующий репозиторий
* импортировать код с другого репозитория 

![Options_of_creating_repository_on_GitHub](new_opt.jpg)

В случае, если у нас ещё нет локального репозитория, нам подходит 1 вариант, смотрим на предложенные команды, создаем папку, открываем её в VSC, запускаем терминал (Ctrl + `) и выполняем все команды из перечня по очереди, тем самым создавая локальный репозиторий:

echo "# Remote" >> README.md - создает файл и записывает туда заголовком 1-го уровня Remote.

git init - инициализирует репозиторий

git add README.md - добавляет указанный файл в отслеживание версий

git commit -m "first commit" - создает первый коммит, фиксируя изменения в репозитории.

git branch -M main - переименование текущей ветки (необходимо, т.к. в локальном репозитории основная ветка у нас master, а на удаленном main. Мы можем сливать только одноименные ветки.)

git remote add origin https://github.com/Boka-C/Remote.git - связываем локальный репозиторий с удаленным (командой ```git remote``` проверяем есть ли связь между локальным и удаленным репозиторием, если нам нужно просмотреть эту информацию вместе с путем, то добавляем параметр -v ```
git remote -v```)

git push -u origin main - отправляет изменения с локального репозитория в удаленный.

Если мы все сделали правильно, то на ГитХабе после обновления страницы мы увидим наш репозиторий и файл README.md 

![readme_on_GitHub](README_on_GitHub.jpg)


При этом у нас есть возможность работать как в локальном репозитории, так и на стороне ГитХаба, либо на другом устройстве. Для стягивания изменений, с сервера ГитХаб, используем команду 
```
git pull
```

И видим, что все прошло успешно и нет никаких ошибок.

![Git_pull](git_pull.jpg)

После данной команды, документ с удаленного репозитория мерджится с локальным и локальный репозиторий становится актуальным.

Для актуализации удаленного репозитория (загрузки на него последней версии документа с локального репозитория), мы пользуемся командой ```git push``` .

Если нет никаких конфликтов, то мы увидим успешную актуализацию данных на удаленном репозитории: 

![git_push_command](Git_push.jpg)

Соответственно все изменения будут отображены на ГитХаб после обновления странички. 

Если у нас информация на одних и тех же строчках различается в удаленном и локальном репозитории и изменения сохранены и закоммитены и там и там, то опять-таки возникнет конфликт, сообщение о котором мы увидим как в терминале:

![Conflict_terminal](conflict_terminal.jpg)

так и в самом VCS

![Conflict_VSC](conflict_lines.jpg)

Пути решения такие же, как и в случае локальных слияний (пункт 13). В некоторых версиях VSC может не отображаться диалоговое окно разрешения конфликтов, но точно всегда будет видна маркировка гит-а, в таком случае просто в ручном режиме корректируем различия и таким способом решаем конфликт. 

После разрешения конфликта, сохраняем изменения и коммитим их.

## 16. работа с чужими репозиториями.

Для работы с чужим репозиторием необходимо либо иметь прямую ссылку, либо найти его в поисковой строке на ГитХаб.

![Search_line](search.jpg)

После того, как нашли необходимый репозиторий, копируем ссылку на него, нажав на соответствующую кнопку в меню кода:

![Copy_link](code.jpg)

При необходимости создаем новую папку, открываем её в VSC, запускаем терминал и выполняем команду ```git clone https://github.com/....``` (вставляем скопированную ссылку после > git clone).

В случае успешного клонирования, у нас скопируется весь репозиторий с ГитХаб.

![Git_clone_command](Git_clone.jpg)

По умолчанию копируется название с ГитХаба, но если в конце команды, после ссылки приписать новое название, то оно копируется с новым названием.

После успешного копирования нам нужно перейти именно в эту папку, для этого есть 2 варианта: либо команда ```cd <folder_name>```; либо с проводника VSC, правым кликом на папке и в меню выбрав > Открыть во встороенном терминале.

### Предложение изменений.

Для того, что бы предложить влядельцу репозитория наши изменения, мы сперва делаем на ГитХабе "форк" его репозитория: 
![Fork_on_GitHub](fork.jpg)

Ищем этот "форк" в своих репозиториях:

![Your_reposytory_online](YouR_onli.jpg)

Открываем его и копируем ссылку на него (через меню Code)

Клонируем данный репозиторий на наш комп (```git clone https://github.com/Boka-C/TestPullRequest.git```)

Переходим в него набрав в терминале команду ```cd <folder_name> ``` (можно набрать первые 3-4 символа названия и использовать кнопку Tab для автозаполнения)

Если мы хотим предложить автору какие-то изменения, то они всегда создаются в новой ветке (git branch <branch_name> создаем ветку, git checkout <branch_name> переходим в неё). 

После внесения всех изменений (добавление/изменения/удаления/корректирования файлов) не забывая закоммитить это все, вливаем в репозиторий на Гит Хаб, используя команду ```git push ```. Если в изначальном репозитории нет ветки с тем же названием что и в вашем, может выскочить ошибка:

![Push_error](push_error.jpg)

В таком случае можно выполнить команду предлагаемую Гит-ом, например: 
```
git push --set-upstream origin new
```

Тем самым мы в удаленном репозитории создали ветку с таким же названием, в чем можно убедиться в ответе на команду:

![new_branch](new.jpg)

После успешной выгрузки локальной версии в наш удаленный репозиторий можно обновить страничку ГитХаба и увидеть актуальную версию нашего локального документа, НО важно обратить внимание на то, в какой ветке вы находитесь на ГитХабе. Т.к. все наши изменения находятся в новой ветке, необходимо переключиться на неё соответствующей кнопкой: 

![Branch_switch](branch_online.jpg)

Для запроса на слияние на ГитХаб нужно перейти во вкладку > Pull request и нажать на кнопку New pull request 

![Pull_request](pull_request.jpg)

После чего нужно будет выбрать для сравнения необходимую ветку:

![Branch_to_compear](compear.jpg)

И пишем название запроса, комментарий к нему и отправляем запрос, нажав на зеленую кнопку. 