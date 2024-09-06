## GIT - система контроля версий

есть понятия local(локального) и remote(удаленного) репозиториев

первый поможет в работе над версиями кода, когда вы работаете над ним сами без команды
второй нужен для командной работы и взаимодействия с другими разработчиками

git репозиторий - это хранилище, в котором находится история изменений проекта



0. советую ознакомиться с `https://www.notion.so/`. удобно сохранять заметки

1. инициализация нового репозитория в выбранной папке (директории): `git init`

2. проверить является ли папка частью репозитория можно командой: `git status`

3. индексация одного файла: `git add <filename>`

4. индексация всех файлов: `git add .`

5. сделать коммит с сообщением (сохранить версию кода): `git commit -m "init"`

6. посмотреть полную историю коммитов со временем и автором: `git log` - `q` для выхода из режима просмотра

7. посмотреть короткую историю - только сообщение и идентификатор: `git loq --oneline` - `q` для выхода из режима просмотра!

8. связать локальный репозиторий с удаленным: `git remote add origin <repo>`

9.  узнать с каким удаленным репозиторием связана папка: `git remote -v`

10.  добавить файлы из локального в удаленный репозиторий и установить ветку для push по умолчанию: `git push -u origin main`

11.  добавить новую локальную ветку: `git branch <имя ветки>`

12.  переключиться на новую локальную ветку: `git checkout <имя ветки>`

13. сделать слияние с другой веткой: `git merge <имя ветки>`

14. чтобы в удаленном репозитории появилась новая ветка ее нужно создать из вашей локальной ветки, например: `git push origin <имя ветки>` только так после появления новой удаленной ветки у вас появится возможность сделать pull request

15. подтянуть изменения из удаленной ветки в локальную: `git pull origin <branch>`

16. .gitignore - это файл, в который мы заносим файлы и папки, которые не хотим передавать в удаленный репозиторий

17. если файл уже был проиндексирован, то при добавлении в .gitignore он все равно будет заметен при последующем коммите

18. снять индексацию с файла: `git rm -r --cached <имя файла>`. только после этой команды сработает добавление ранее проиндексированного файла / папки

19. если git просит сделать коммит, а вы считает что изменений еще недостаточно - можете спрятать изменения в 'тайник' с помощью команды `git stash`. это даст вам возможность, например, переключить ветки

20. чтобы вернуть на ветку 'спрятанные' изменения нужна команда: `git stash pop`

21. Перемещение во времени по истории коммитов `git checkout <коммит>`

22. Удаление всей истории после выбранного коммита `git reset --hard <коммит>`

23. Просмотр истории всех действий с идентификаторами (удобно если сделали reset и передумали) `git reflog`

24. Удалить новые один коммит из истории сохранив код до и после него `git revert <коммит>`.  если в результате этой команды вы попадаете в редактор кода vim - выйти из него сохранением коммита по умолчанию `:wq`. если будут конфликты - решите их в merge editor

26. В случае если git не дает сделать push, но вы уверены в своем решении можно сделать push 'c силой' `git push -f` или force push.