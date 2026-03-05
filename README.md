# LAB02 Report
## Панин ИУ8-23

### Part 1
#### Задание 1: Создайте пустой репозиторий на сервисе github.com
#### Задание 2: Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге
#### Задание 3: Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
#### Задание 4: Добавьте этот файл в локальную копию репозитория.
#### Задание 5: Закоммитьте изменения с осмысленным сообщением.
```
$ subl hello_world.cpp
#include <iostream>
using namespace std;
int main(){
	
	cout<<"Hello world!!!";
	return 0;
}
$ git add hello_world.cpp
$ git commit -m"new prog in project"
[master af52b7f] new prog in project
 1 file changed, 6 insertions(+)
 create mode 100644 lab02/hello_world.cpp
```
#### Задание 6:Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя 
#### Задание 7:Закоммитьте новую версию программы
##### Почему не надо добавлять файл повторно git add? Потому что файл уже добавлен
#### Задание 8:Запуште изменения в удалёный репозиторий.
```
$ subl hello_world.cpp
#include <iostream>
#include <string>
using namespace std;
int main(){
	string name;
	cin>>name;
	cout<<"Hello world from "<<name;
	return 0;
}
$ git commit -m"hello world update"
[master 2ec0cb5] hello world update
 1 file changed, 4 insertions(+), 2 deletions(-)
$ git push origin master
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 414 bytes | 414.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/vanishhhhh/lab02.git
   b357315..2ec0cb5  master -> master
```
#### Задание 9: Проверьте, что история коммитов доступна в удалёный репозитории.

### Part 2
#### Задание 1:В локальной копии репозитория создайте локальную ветку patch1.
#### Задание 2:Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.
#### Задание 3:commit, push локальную ветку в удалённый репозиторий.
#### Задание 4:Проверьте, что ветка patch1 доступна в удалёный репозитории.
```
$ git branch patch1
$ git checkout patch1
$ subl hello_world.cpp
#include <iostream>
#include <string>
int main(){
	std::string name;
	std::cin>>name;
	std::cout<<"Hello world from "<<name;
	return 0;
}
$ git add hello_world.cpp
$ git commit -m"update for helloworld in patch1"
[patch1 5baf106] update for helloworld in patch1
 1 file changed, 3 insertions(+), 4 deletions(-)
$ git push origin HEAD
Password for 'https://vanishhhhh@github.com':
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 414 bytes | 414.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/vanishhhhh/lab02/pull/new/patch1
remote:
To https://github.com/vanishhhhh/lab02.git
 * [new branch]      HEAD -> patch1
```

#### Задание 5 Создайте pull-request patch1 -> master.
#### Задание 6 В локальной копии в ветке patch1 добавьте в исходный код комментарии.
#### Задание 7 commit, push.
```
$ subl hello_world.cpp
#include <iostream> //подключаем библиотеки
#include <string>
int main(){
	std::string name;//иницализируем переменные
	std::cin>>name;
	std::cout<<"Hello world from "<<name;//главная часть проги
	return 0;
}
$ git commit -m"update2 for helloworld in patch1"
[patch1 6eb2843] update2 for helloworld in patch1
 1 file changed, 3 insertions(+), 3 deletions(-)
$ git push origin HEAD
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 522 bytes | 522.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/vanishhhhh/lab02.git
   5baf106..6eb2843  HEAD -> patch1
```

#### Задание 8 Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
#### Задание 9 В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
#### Задание 10 Локально выполните pull.
#### Задание 11 С помощью команды git log просмотрите историю в локальной версии ветки master.
```
$ git pull
$ git log 
commit 6eb28431f3ff8f2db08182e80ce9cd59cecd13fd (HEAD -> patch1, origin/patch1)
Author: vanishhhhh <vanpanvit@gmail.com>
Date:   Thu Mar 5 21:35:12 2026 +0300
    update2 for helloworld in patch1
commit 5baf1060489fe60b4604471890e62dacfe29ab22
Author: vanishhhhh <vanpanvit@gmail.com>
Date:   Thu Mar 5 21:07:06 2026 +0300
    update for helloworld in patch1
commit 2ec0cb5e688336597ab70a476957281717899be1 (origin/master, master)
Author: vanishhhhh <vanpanvit@gmail.com>
Date:   Thu Mar 5 20:27:44 2026 +0300
    hello world update
```
#### Задание 12 Удалите локальную ветку patch1.
```
$ git checkout master
Switched to branch 'master'
$ git branch -d patch1
error: The branch 'patch1' is not fully merged.
If you are sure you want to delete it, run 'git branch -D patch1'.
$ git branch -D patch1
Deleted branch patch1 (was 6eb2843).
```

### Part 3
#### Задание 1 Создайте новую локальную ветку patch2
```
$ git branch patch2
 
```
#### Задание 2 Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.
#### Задание 3 commit, push, создайте pull-request patch2 -> master
```
$ clang-format -i -style=Mozilla hello_world.cpp
$ git commit -m"Mozilla style HW"
$ git push -u origin patch2
```
#### Задание 4 В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
#### Задание 5 Убедитесь, что в pull-request появились конфликтны.
#Задание 6 Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.

```
$ git rebase origin/master
CONFLICT (content): Merge conflict in lab02/hello_world.cpp
error: could not apply 4d95d08... Update hello_world.cpp
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 4d95d08... Update hello_world.cpp
#include <iostream> //including libraries
#include <string>
<<<<<<< HEAD
int main(){
	std::string name;//иницализируем переменные
	std::cin>>name;
	std::cout<<"Hello world from "<<name;//главная часть проги
	return 0;
}
=======
int 
main()
{
  std::string name;
  std::cin >> name;
  std::cout << "Hello world from " << name;
  return 0;
}
>>>>>>> 5dabf7b (Mozilla format hello world)
```
#### Исправляем
```
$ git add hello_world.cpp
$ git rebase --continue
[detached HEAD 6df7760] ss2
 1 file changed, 2 insertions(+), 1 deletion(-)
Successfully rebased and updated refs/heads/patch2.
```
#### Задание 7 Сделайте force push в ветку patch2
```
$ git push --force-with-lease
Username for 'https://github.com': vanishhhhh
Password for 'https://vanishhhhh@github.com':
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 8 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (16/16), 1.62 KiB | 1.63 MiB/s, done.
Total 16 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To https://github.com/vanishhhhh/lab02.git
 + 1465695...6df7760 patch2 -> patch2 (forced update)
```
#### Задание 8 Убедитель, что в pull-request пропали конфликтны.
#### Задание 9 Вмержите pull-request patch2 -> master.
