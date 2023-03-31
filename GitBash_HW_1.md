# Git_Bash_HW_1

1. Посмотреть где я
- `pwd` //*print working directory*

2. Создать папку
- `mkdir dir` //*make directory*

3. Зайти в папку
- `cd dir` //*change directory*

4. Создать 3 папки
- `mkdir dir1 dir2 dir3`
- `mkdir {dir1,dir2,dir3}`
- `mkdir dir{1..3}`

5. Зайти в любую папку
- `cd dir1`

6. Создать 5 файлов (3 txt, 2 json)
- `touch file1.txt file2.txt file3.txt file4.json file5.json`
- `touch {file1.txt,file2.txt,file3.txt,file4.json,file5.json}`
- `touch file{1..3}.txt file{4..5}.json`

7. Создать 3 папки
- `mkdir dir4 dir5 dir6`
- `mkdir {dir4,dir5,dir6}`
- `mkdir dir{4..6}`

8. Вывести список содержимого папки
- `ls -la`

9. Открыть любой txt файл
- a) `cat file1.txt`
- b) `vim file1.txt`

10. Написать туда что-нибудь, любой текст
- a) `cat > file1.txt`
    - `Hello world!`
- b) <pre><kbd>i</kbd> //*#insert - режим редактирования*</pre>
    - `Hello world!`

11. Сохранить и выйти
- a) <pre><kbd>ctrl</kbd>+<kbd>c</kbd></pre>
- b) <pre><kbd>esc</kbd> //*выйти из режима редактирования*</pre>
   `:wq`

12. Выйти из папки на уровень выше
- `cd ..`
- `cd -`

### —
13. Переместить любые 2 файла, которые вы создали, в любую другую папку
- `mv dir1/{file1.txt,file4.json} dir2` //*move*
- `mv dir1/*.* dir2` //*переместить все файлы из папки dir1 в папку dir2*

14. Скопировать любые 2 файла, которые вы создали, в любую другую папку
- `cp dir2/{file1.txt,file4.json} dir3` //*copy*

15. Найти файл по имени
- `find -name file2.txt`
- `find -name file2*`

16. Просмотреть содержимое в реальном времени (команда grep). Изучите как она работает
- `tail -f dir1/file2.txt` //*просмотреть содержимое в реальном времени, обновлять информацию по мере появления новых строк в файле* <pre><kbd>ctrl</kbd>+<kbd>c</kbd> //*выйти из режима просмотра*</pre>

```
grep Hello world! file1.txt //найти запись Hello world! в файле file1.txt
grep -i Hello world! file1.txt //найти запись Hello world! в файле file1.txt без учета регистра
grep -v Hello world! file1.txt //отобразить строки в файле file1.txt, в которых нет Hello world!
grep -с Hello world! file1.txt //посчитать кол-во строк, содержащих Hello world!
grep -R Hello world! folder2 //показать все файлы, содержащие Hello world!
Эти функции можно комбинировать, например: grep -iс Hello world! file1.txt
```
Ответ: `tail -f anything_1.txt | grep --line-buffered 17: >> test_qq.txt`

17. Вывести несколько первых строк из текстового файла
- `head -2 file1.txt` //*выведет первые 2 строки*
- `head file1.txt` //*по умолчанию выводит первые 10 строк*

18. Вывести несколько последних строк из текстового файла
- `tail -2 file1.txt` //*выведет последние 2 строки*
- `tail file1.txt` //*по умолчанию выводит последние 10 строк*

19. Просмотреть содержимое длинного файла (команда less). Изучите как она работает
- `less file1.txt` //*используется для постраничного просмотра больших текстовых файлов* <pre><kbd>v</kbd> //*откроет текстовый редактор и позволит изменять контент*</pre> <pre><kbd>q</kbd> //*выйти из режима просмотра*</pre>

20. Вывести дату и время
- `date`

### Задание *
1. Отправить http запрос на сервер <http://162.55.220.72:5005/terminal-hw-request>
- `curl http://162.55.220.72:5005/terminal-hw-request`

- `curl "http://162.55.220.72:5005/get_method?name=Mr.Bond&age=27"`
    - Ответ: ["Mr.Bond","27"]

- `curl -X POST "http://162.55.220.72:5005/get_method?name=Mr.Bond&age=27"`
    - Ответ: "Natalia MOLODEC"


2. Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
- `nano script.sh` //*создать файл*

```
#!/bin/bash
cd fol
mkdir fol{1..3}
cd fol1
touch f{1..3}.txt f{4..5}.json
mkdir fol{4..6}
ls -la
cd ..
mv fol1/{f1.txt,f4.json} fol2
```

- `chmod +x ./script.sh` //*сделать файл исполняемым*
- `./script.sh` //*запустить файл*
