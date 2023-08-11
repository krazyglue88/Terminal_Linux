# Terminal pt.1
1) Посмотреть где я            ```pwd```
2) Создать папку               ```mkdir qa```
3) Зайти в папку               ```cd qa```
4) Создать 3 папки             ```mkdir {test1,test2,test3}```
5) Зайти в любоую папку        ```cd test1```
6) Создать 5 файлов (3 txt, 2 json)     ```touch {file1.txt,file2.txt,file3.txt,file4.json,file5.json}```
7) Создать 3 папки                     ```mkdir {test4,test5,test6}```
8) Вывести список содержимого папки     ```ls``` 
                                        ```ls -la```     
9) Открыть любой txt файл                    ```vim file1.txt```
10) Написать туда что-нибудь, любой текст.   ```нажать клавишу "I", написать/вставить текст```
                               
11) сохранить и выйти.                 ```"нажать 'Esc', :wq + Enter```
12) Выйти из папки на уровень выше            ```cd ..```

13) переместить любые 2 файла, которые вы создали, в любую другую папку.   
```mv file1.txt file2.txt test4/```
                                                                          
       

14) скопировать любые 2 файла, которые вы создали, в любую другую папку.   ```cp file4.json file5.json test5/``` 
                                                                           
15) Найти файл по имени         ```find -name file2.txt```
16) просмотреть содержимое в реальном времени (команда grep) изучите как она работает.

```tail -f file1.txt``` - (просмотреть содержимое файла в реальном времени), ```ctrl+c``` - выход.

```grep 8 file1.txt``` - ( появится строка, содержащая "8")

17) вывести несколько первых строк из текстового файла       ```head -2 file1.txt```
18) вывести несколько последних строк из текстового файла    ```tail -2 file1.txt```

19) просмотреть содержимое длинного файла (команда less) изучите как она работает.   ```less name_file``` выход-клавиша ```Q```
20) вывести дату и время    ```date``` ```date -u``` (UTC)
---
__Задание *__
1) Отправить http запрос на сервер.
http://162.55.220.72:5006/terminal-hw-request

```curl 'http://162.55.220.72:5006/object_info_3?name=Ivan&age=36'```


2) Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13

Создаём файл: ```touch test1.sh```

Далее  ```vim test1.sh```

 
```
#!/bin/sh
cd qa
mkdir {test1,test2,test3}
cd test1
touch {file1.txt,file2.txt,file3.txt,file4.json,file5.json}
mkdir {test4,test5,test6}
ls -la
mv file1.txt file2.txt test4/
```

Запускаем скрипт: ```sh test1.sh``` 
# Terminal pt.2
1. Сделать папку dir_1 ```mkdir dir_1```
2. Зайти в папку dir_1 ```cd dir_1```
3. Создать папку inner_dir_1 ```mkdir inner_dir_1```
4. Посмотреть где ты находишься ```pwd```
5. Находясь в папке dir_1 создать пустой текстовый файл tf_1.txt ```touch tf_1.txt``` 
6. Находясь в папке dir_1 через команду cat создать текстовый файл tf_2.txt со следующими строками:
- the first 1
- the second 2
- the third 3
                   ```cat > tf_2.txt``` + ```Enter```
     Вводим текст:  ```the first 1
                       the second 2
                       the third 3```
     ```Enter``` ```ctrl" + "c"```
7. Зайти в папку inner_dir_1 ```cd inner_dir_1```
8. Через cat сделать текстовый файл tf_3.txt  c любыми строками  
                                                       ```cat > tf_3.txt``` ```Enter```
                                                       Вводим текст:  ```user1
                                                                         user2
                                                                         user3```
                                                              ```Enter``` ```ctrl" + "c"```
9. Через cat добавить в текстовый файл tf_3.txt строку “the second 2” 
                                                         ```cat >> tf_3.txt``` ```Enter```
                                           Вводим текст: ```the second 2```
                                            ```Enter``` ```ctrl" + "c"``` 
10. Через cat добавить в текстовый файл tf_3.txt строку “the sec 2”
                                                         ```cat >> tf_3.txt``` ```Enter```
                                           Вводим текст: ```the sec 2```
                                           ```Enter``` ```ctrl" + "c"```
11. Через cat добавить в текстовый файл tf_2.txt строку “the sec 3”
                                       ```cat >> ../tf_2.txt``` ```Enter```

  Вводим текст: ```the sec 3``` ```Enter``` ```ctrl" + "c"```

12. Через cat добавить в текстовый файл tf_3.txt строку “the SeCoNd 2”
                           ```cat >> tf_3.txt```
             Вводим текст: ```the SeCoNd```
             ```Enter``` ```ctrl" + "c"```       
13. Через cat добавить в текстовый файл tf_2.txt строку “the seConD 2”
                                       ```cat >> ../tf_2.txt```

                                   Вводим текст: ```the seConD 2``` ```Enter``` ```ctrl" + "c"```

14. Сделать текстовый файл tf_4.txt в котором будет 15 строк.
                 ```for i in {1..15}; do echo "$i" >> tf_4.txt; done```
15. Сделать текстовый файл tF_5.txt в котором будет 13 строк.
                 ```for i in {1..13}; do echo "$i" >> tF_5.txt; done```
16. Вывести список всех файлов в папке. 
                                        ```ls -l```
17. Выйти из папки inner_dir_1
                               ```cd..```
18. Вывести содержимое файла tf_3.txt в терминал.
                                ```cat inner_dir_1/tf_3.txt```
19. Найти путь к файлу tf_4.txt
                              ```realpath tf_4.txt```
20. Отчистить файл tf_4.txt от содержимого без удаления самого файла.
                                                       ```:> inner_dir_1/tf_4.txt```
21. Найти путь к файлам у которых есть  “tf” в названии.
                                                         ```find . -name "tf*"```
22. Найти путь к файлам у которых есть  “tf” в названии и буквы в любом регистре.
                                                         ```find . -iname "tf*"```
23. Найти строки в файлах где есть комбинация букв “sec” в текущей папке
                                                           ```grep sec *```
24. Найти строки в файлах где есть комбинация букв “sec” в любом регистре в текущей папке
                                                           ```grep -i sec *```
25. Найти строки в файлах где есть только комбинация букв “sec” в текущей папке
                                                           ```grep -w sec *```
26. Найти строки в файлах где есть только комбинация букв “sec” в любом регистре в текущей папке
                                                           ```grep -wi sec *```
27. Найти строки в файлах где есть комбинация букв “second” в текущей папке
                                                           ```grep second *```
28. Найти строки в файлах где есть комбинация букв “second” в любом регистре в текущей папке
                                                           ```grep -i second *```
29. Найти строки в файлах где есть комбинация букв “second” во всех папках ниже уровнем
                                                           ```grep -r second *```
30. Найти только путь и название файла в строках которых есть комбинация букв “second” в текущей папке
                                                          ```grep -L second *```
31. Найти все строки во всех файлах где нет комбинации “second”
                                                              ```grep -v second *```
32. Найти только название и путь к файлам где нет комбинации “second”
                                                              ```grep -Lv second *```
33. Вывести в терминал 4 последних строк любого текстового файла
                                                         ```tail -4 inner_dir_1/tF_5.txt```
34. Вывести в терминал 4 первые строки любого текстового файла.
                                                       ```head -4 inner_dir_1/tF_5.txt```
35. Команда в одну строку. Создать папку и создать текстовый файл с содержиммым.
     ```mkdir my_file && echo "Hello, this is Ivan" > my_file/greeting.txt``` - создастся папка и внутри неё текстовый файл с содержимым
     ```mkdir my_file|echo Hello, this is Ivan > greeting.txt``` - создастся папка и отдельно от неё текстовый файл с содержимым
36. Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
```grep -l -r sec|xargs -I {} mv {} my_file/```
37. Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”            ```grep -l -r sec| xargs -I {} cp {} my_file/```
38. Команда в одну строку. Найти все строки c “sec” во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл.
                               ```grep -r sec|cat >> new.txt```
39. Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово “sec”
                      ```grep -rl sec|xargs rm -f```
40. Просто вывести в терминал строку “Good job!!”
                                                  ```echo '"Good Job!!"'```
                  
