## Laboratory work V

Данная лабораторная работа посвещена изучению фреймворков для тестирования на примере **GTest**

```sh
$ open https://github.com/google/googletest
```
## Homework

### Задание
1. Создайте `CMakeList.txt` для библиотеки *banking*.
2. Создайте модульные тесты на классы `Transaction` и `Account`.
    * Используйте mock-объекты.
    * Покрытие кода должно составлять 100%.
3. Настройте сборочную процедуру на **TravisCI**.
4. Настройте [Coveralls.io](https://coveralls.io/).
```sh
┌──(kali㉿kali)-[~]
└─$ /home/kali/GOSICK070404/workspace/projects/
                                                                                                                                                                             
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects]
└─$ git clone https://github.com/tp-labs/lab05 lab05
Cloning into 'lab05'...
remote: Enumerating objects: 137, done.
remote: Counting objects: 100% (25/25), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 137 (delta 18), reused 16 (delta 16), pack-reused 112
Receiving objects: 100% (137/137), 918.92 KiB | 2.01 MiB/s, done.
Resolving deltas: 100% (60/60), done.
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects]
└─$ cd lab05               
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$ git init                                        
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint:   git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint:   git branch -m <name>
Initialized empty Git repository in /home/kali/GOSICK070404/workspace/projects/lab05/.git/
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$ git remote remove origin
error: No such remote: 'origin'
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$ git remote add origin https://github.com/GOSICK070404/lab05
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$ git remote remove origin                                   
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$ git remote add origin https://github.com/GOSICK070404/lab05
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$  git submodule add  https://github.com/google/googletest.git
Cloning into '/home/kali/GOSICK070404/workspace/projects/lab05/googletest'...
remote: Enumerating objects: 26402, done.
remote: Counting objects: 100% (9781/9781), done.
remote: Compressing objects: 100% (548/548), done.
remote: Total 26402 (delta 9392), reused 9236 (delta 9233), pack-reused 16621
Receiving objects: 100% (26402/26402), 12.09 MiB | 3.19 MiB/s, done.
Resolving deltas: 100% (19622/19622), done.
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/GOSICK070404/workspace/projects/lab05]
└─$  cd banking
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/workspace/projects/lab05/banking]
└─$ rm CMakeList.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/workspace/projects/lab05/banking]
└─$ nano CMakeLists.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/workspace/projects/lab05/banking]
└─$ mkdir .github
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/workspace/projects/lab05/banking]
└─$ mkdir .github/workflows
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/workspace/projects/lab05/banking]
└─$ cd .github/workflows
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/lab05/banking/.github/workflows]
└─$ nano cmake.yml
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/lab05/banking/.github/workflows]
└─$ nano CMakeLists.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/lab05/banking/.github/workflows]
└─$  mkdir tests
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/lab05/banking/.github/workflows]
└─$ cd tests
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/banking/.github/workflows/tests]
└─$ nano test_Account.cpp
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/banking/.github/workflows/tests]
└─$ nano test_Transaction.cpp
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/banking/.github/workflows/tests]
└─$  mkdir coverage
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/banking/.github/workflows/tests]
└─$  cd coverage
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/.github/workflows/tests/coverage]
└─$ touch temp.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/.github/workflows/tests/coverage]
└─$ git add -A
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/.github/workflows/tests/coverage]
└─$ git commit -m"from tp-labs with tests"
[master (root-commit) 6483f8e] from tp-labs with tests
 15 files changed, 597 insertions(+)
 create mode 100644 .gitmodules
 create mode 100644 LICENSE
 create mode 100644 README.md
 create mode 100644 banking/.github/workflows/CMakeLists.txt
 create mode 100644 banking/.github/workflows/cmake.yml
 create mode 100644 banking/.github/workflows/tests/coverage/temp.txt
 create mode 100644 banking/.github/workflows/tests/test_Account.cpp
 create mode 100644 banking/.github/workflows/tests/test_Transaction.cpp
 create mode 100644 banking/Account.cpp
 create mode 100644 banking/Account.h
 create mode 100644 banking/CMakeLists.txt
 create mode 100644 banking/Transaction.cpp
 create mode 100644 banking/Transaction.h
 create mode 160000 googletest
 create mode 100644 preview.png
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/.github/workflows/tests/coverage]
└─$ git push origin master
Username for 'https://github.com': GOSICK070404
Password for 'https://GOSICK070404@github.com': 
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 2 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (21/21), 889.13 KiB | 20.68 MiB/s, done.
Total 21 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/GOSICK070404/lab05
 * [new branch]      master -> master
 ```
## Links

- [C++ CI: Travis, CMake, GTest, Coveralls & Appveyor](http://david-grs.github.io/cpp-clang-travis-cmake-gtest-coveralls-appveyor/)
- [Boost.Tests](http://www.boost.org/doc/libs/1_63_0/libs/test/doc/html/)
- [Catch](https://github.com/catchorg/Catch2)

```
Copyright (c) 2015-2021 The ISC Authors
```
