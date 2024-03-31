# lab02

# TUTORIAL HOW I DID HOMEWORK 2

### Part I

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.

```sh
$ echo "# lab02" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/Adam-dunno/lab02.git
$ git push -u origin main
```



```sh
Reinitialised existing Git repository in /home/adam/.git/
[main 406a755] first commit
 1 file changed, 1 deletion(-)
error: remote origin already exists.
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 3 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (14/14), 1.10 KiB | 1.10 MiB/s, done.
Total 14 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/Adam-dunno/lab02.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```





```sh
$ git remote add origin https://github.com/Adam-dunno/lab02.git
$ git branch -M main
$ git push -u origin main
```



```sh
error: remote origin already exists.
Branch 'main' set up to track remote branch 'main' from 'origin'.
Everything up-to-date
```

```sh
$ git clone https://github.com/Adam-dunno/lab02.git
```



```sh
Cloning into 'lab02'...
remote: Enumerating objects: 14, done.
remote: Counting objects: 100% (14/14), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 14 (delta 5), reused 14 (delta 5), pack-reused 0
Receiving objects: 100% (14/14), done.
Resolving deltas: 100% (5/5), done.
```

3. Создайте файл `hello_world.cpp` в локальной копии репозитория . Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода.

```sh
$ cd lab02
$ touch hello_ world.cpp
```



**hello_world.cpp:**
```sh
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello world!" << endl;
    return 0;
}
```


8. Добавьте этот файл в локальную копию репозитория.



```sh
$ git add hello_world.cpp
```



4. Закоммитьте изменения с *осмысленным* сообщением.

```sh
$ git commit -m "Added initial version of Hello world program with bad code style"
```


```sh
[main 6991008] Added initial version of Hello world program with bad code style
 1 file changed, 9 insertions(+)
 create mode 100644 hello_world.cpp
```



5. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение `Hello world from @name`, где `@name` имя пользователя.




**hello_world.cpp with greet user by name:**

```sh
#include <iostream>
#include <string>
using namespace std; 
int main()
{
  string name;
  cout << "Enter your name: ";
  cin >> name;
  cout << "Hello world from " << name << endl;
  return 0;
}
```




6. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно `git add`?



```sh
$ git commit -am "Modified program to greet user by name"
```




```sh
[main 305998b] Modified program to greet user by name
 1 file changed, 5 insertions(+), 1 deletion(-)
```



Почему не надо добавлять файл повторно `git add`?


```sh
Потому что при первом добавлении файла в Git, он уже отслеживается системой контроля версий, и при последующем коммите изменений в этом файле, Git автоматически учитывает его изменения.
```



7. Запуште изменения в удалёный репозиторий.



```sh
$ git push origin main
```




```sh
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 3 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 829 bytes | 829.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Adam-dunno/lab02.git
   406a755..305998b  main -> main
```




### Part II

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. В локальной копии репозитория создайте локальную ветку `patch1`.



```sh
$ git checkout -b patch1
```



```sh
Switched to a new branch 'patch1'
```



2. Внесите изменения в ветке `patch1` по исправлению кода и избавления от `using namespace std;`.




**hello_world.cpp with greet user by name without `using namespace std;`:**

```sh
#include <iostream>
#include <string>

int main()
{
    std::string name;
    std::cout << "Enter your name: ";
    std::cin >> name;
    std::cout << "Hello world from " << name << std::endl;
    return 0;
}
```




```sh
$ git add .
$ git commit -m "Removed using namespace std;"
```

```sh
[patch1 664f229] Removed using namespace std;
 1 file changed, 4 insertions(+), 5 deletions(-)
```



3. **commit**, **push** локальную ветку в удалённый репозиторий.



```sh
$ git push origin patch1
```





```sh
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 3 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 427 bytes | 427.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/Adam-dunno/lab02/pull/new/patch1
remote: 
To https://github.com/Adam-dunno/lab02.git
 * [new branch]      patch1 -> patch1
```

4. В локальной копии в ветке `patch1` добавьте в исходный код комментарии.



**hello_world.cpp with greet user by name, without `using namespace std;`, with commentaries:**



```sh
#include <iostream>
#include <string>

int main()
{
  std::string name;
  std::cout << "Enter your name: ";
  std::cin >> name; // write here your name, please!
  std::cout << "Hello world from " << name << std::endl;
  return 0;
}
```





```sh
$ git add .
$ git commit -m "Added comments to the code"
$ git push origin patch1
```





```sh
[patch1 9c5a65c] Added comments to the code
 1 file changed, 1 insertion(+), 1 deletion(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 3 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 359 bytes | 359.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Adam-dunno/lab02.git
   664f229..9c5a65c  patch1 -> patch1
```




5. Локально выполните **pull**.



```sh
$ git checkout main  
$ git pull origin main 
```





```sh
Switched to branch 'main'
Your branch is up-to-date with 'origin/main'.
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 908 bytes | 908.00 KiB/s, done.
From https://github.com/Adam-dunno/lab02
 * branch            main       -> FETCH_HEAD
   305998b..ec396b6  main       -> origin/main
Updating 305998b..ec396b6
Fast-forward
 hello_world.cpp | 9 ++++-----
 1 file changed, 4 insertions(+), 5 deletions(-)
```




6. С помощью команды **git log** просмотрите историю в локальной версии ветки `master`.




```sh
$ git log
```




```sh
commit ec396b69c279581339ef42ad145d97a8ed5e383e (HEAD -> main, origin/main, origin/HEAD)
Merge: 305998b 9c5a65c
Author: Adam-dunno <147333284+Adam-dunno@users.noreply.github.com>
Date:   Sun Mar 31 15:58:18 2024 +0300

    Merge pull request #1 from Adam-dunno/patch1
    
    Removed using namespace std;

commit 9c5a65c316008989f7b9ad65de559e1b51229b07 (origin/patch1, patch1)
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:38:23 2024 +0300

    Added comments to the code

commit 664f2297af12a5abf71debcd13590f79e7d4542a
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:23:17 2024 +0300

    Removed using namespace std;

commit 305998b0e164c2e93026e76ae070f2000fbe7be5
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:22:20 2024 +0300

    Modified program to greet user by name

commit 69910082a65be3ff49214f1177502adedc9ffdb1
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:21:35 2024 +0300

    Added initial version of Hello world program with bad code style

commit 406a755ba76c11a8df41765fc8b5b0c30c2fbdb9
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:19:59 2024 +0300

    first commit

commit 385aeae565626fb1b9fd2f8954683add5ee821ea
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 15:17:51 2024 +0300

    first commit

commit 80c446eb54ae66d3160564be54358fbc56cf2227
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 00:33:32 2024 +0300

    first commit

commit f7ecc7222491700807c79937a385a13b6411567c
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 00:26:43 2024 +0300

    first commit

commit c3ba2579ef30384681e81fcefe8b02c9b8421b6b
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sun Mar 31 00:25:58 2024 +0300

    first commit

commit 6acdde65d2a5278824f6d5207b20faeeca22fef1
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sat Mar 30 23:56:58 2024 +0300

    first commit

commit 4abbfb863a7bffca5bd086c774a147d5ce0fe15d
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sat Mar 30 23:04:30 2024 +0300

    first commit

commit 131412fc755985e4e97e2743ca7d2dc69431f664
Author: Adam-dunno <goshaivanov2019@mail.ru>
Date:   Sat Mar 30 23:04:04 2024 +0300

    first commit

[1]+  Stopped                 git log
```





7. Удалите локальную ветку `patch1`.



```sh
$ git branch -d patch1
```




```sh
Deleted branch patch1 (was 9c5a65c).
```

### Part III

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. Создайте новую локальную ветку `patch2`.
2. Измените *code style* с помощью утилиты [**clang-format**](http://clang.llvm.org/docs/ClangFormat.html). Например, используя опцию `-style=Mozilla`.
3. **commit**, **push**, создайте pull-request `patch2 -> master`.



```sh
$ clang-format -i -style=Mozilla hello_world.cpp
$ git checkout -b patch2
$ git add .
$ git commit -m "Changed code style using clang-format"
```




```sh
Switched to a new branch 'patch2'
[patch2 4aac1fe] Changed code style using clang-format
 1 file changed, 7 insertions(+), 7 deletions(-)
```




4. В ветке **master** в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.




**hello_world.cpp with greet user by name, without `using namespace std;`, with new commentaries. Code style: clang-format:**




```sh
#include <iostream>
#include <string>

int
main()
{
  std::string name;
  std::cout << "Enter your name: ";
  std::cin >> name; // напишите здесь свое имя пожалуйста!!!
  std::cout << "Hello world from " << name << std::endl;
  return 0;
}
```





```sh
$ git add .
$ git commit -m "Updated comments in the code"
$ git push origin main
```




```sh
[patch2 11cf720] Updated comments in the code
 1 file changed, 1 insertion(+), 1 deletion(-)
Everything up-to-date
```



```sh
git push origin patch2
```




```sh
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 3 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 677 bytes | 677.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/Adam-dunno/lab02.git
   4aac1fe..11cf720  patch2 -> patch2
```



5. Для этого локально выполните **pull** + **rebase** (точную последовательность команд, следует узнать самостоятельно). **Исправьте конфликты**.





```sh
$ git checkout patch2
$ git pull --rebase origin main
$
```





```sh
Already on 'patch2'
From https://github.com/Adam-dunno/lab02
 * branch            main       -> FETCH_HEAD
Current branch patch2 is up to date.
```

**Исправьте конфликт**.


```sh
$ git add .
   git rebase --continue
```




```sh
fatal: No rebase in progress?
```



6. Сделайте *force push* в ветку `patch2`




```sh
$    git push origin patch2 --force
```



```sh
Everything up-to-date
```

**проверка запуска программы**:


```sh
$ gcc hello_world.cpp -o hello_world
```






```sh
/usr/bin/ld: /tmp/cce8uc3q.o: warning: relocation against `_ZSt4cout' in read-only section `.text'
/usr/bin/ld: /tmp/cce8uc3q.o: in function `main':
hello_world.cpp:(.text+0x24): undefined reference to `std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> >::basic_string()'
/usr/bin/ld: hello_world.cpp:(.text+0x35): undefined reference to `std::cout'
/usr/bin/ld: hello_world.cpp:(.text+0x3d): undefined reference to `std::basic_ostream<char, std::char_traits<char> >& std::operator<< <std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*)'
/usr/bin/ld: hello_world.cpp:(.text+0x4b): undefined reference to `std::cin'
/usr/bin/ld: hello_world.cpp:(.text+0x53): undefined reference to `std::basic_istream<char, std::char_traits<char> >& std::operator>><char, std::char_traits<char>, std::allocator<char> >(std::basic_istream<char, std::char_traits<char> >&, std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> >&)'
/usr/bin/ld: hello_world.cpp:(.text+0x64): undefined reference to `std::cout'
/usr/bin/ld: hello_world.cpp:(.text+0x6c): undefined reference to `std::basic_ostream<char, std::char_traits<char> >& std::operator<< <std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*)'
/usr/bin/ld: hello_world.cpp:(.text+0x7e): undefined reference to `std::basic_ostream<char, std::char_traits<char> >& std::operator<< <char, std::char_traits<char>, std::allocator<char> >(std::basic_ostream<char, std::char_traits<char> >&, std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> > const&)'
/usr/bin/ld: hello_world.cpp:(.text+0x85): undefined reference to `std::basic_ostream<char, std::char_traits<char> >& std::endl<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&)'
/usr/bin/ld: hello_world.cpp:(.text+0x90): undefined reference to `std::ostream::operator<<(std::ostream& (*)(std::ostream&))'
/usr/bin/ld: hello_world.cpp:(.text+0xa1): undefined reference to `std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> >::~basic_string()'
/usr/bin/ld: hello_world.cpp:(.text+0xc7): undefined reference to `std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> >::~basic_string()'
/usr/bin/ld: /tmp/cce8uc3q.o: in function `__static_initialization_and_destruction_0(int, int)':
hello_world.cpp:(.text+0x10d): undefined reference to `std::ios_base::Init::Init()'
/usr/bin/ld: hello_world.cpp:(.text+0x128): undefined reference to `std::ios_base::Init::~Init()'
/usr/bin/ld: /tmp/cce8uc3q.o:(.data.rel.local.DW.ref.__gxx_personality_v0[DW.ref.__gxx_personality_v0]+0x0): undefined reference to `__gxx_personality_v0'
/usr/bin/ld: warning: creating DT_TEXTREL in a PIE
collect2: error: ld returned 1 exit status
```




**HOMEWORK 2 COMPLETE!**
