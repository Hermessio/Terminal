Linux terminal (GitBash) commands
=
---
Task 1
-

1) Посмотреть где я:
```bash
pwd
```
2) Создать папку:
```bash
mkdir exampl
```
3) Зайти в папку:
```bash
cd exampl
```
4) Создать 3 папки:
```bash
mkdir dir_1 dir_2 dir_3
```
5) Зайти в любоую папку:
```bash
cd dir_1
```
6) Создать 5 файлов (3 txt, 2 json):
```bash
touch 1.txt 2.txt 3.txt 1.json 2.json
```
7) Создать 3 папки:
```bash
mkdir dir_1_1 dir_1_2 dir_1_3
```
8. Вывести список содержимого папки:
```bash
ls -la
```
9) Открыть любой txt файл:
```bash
vim 1.txt
```
10) + написать туда что-нибудь, любой текст:
```bash
i
```
11) + сохранить и выйти:
```bash
[Esc]
:wq
[Enter]
```
12) Выйти из папки на уровень выше:
```bash
cd ..
```
13) Переместить любые 2 файла, которые вы создали, в любую другую папку:
```bash
mv dir_1/1.json dir_1/2.json dir_2
```
14) Скопировать любые 2 файла, которые вы создали, в любую другую папку:
```bash
cp dir_1/1.txt dir_1/2.txt dir_2
```
15) Найти файл по имени:
```bash
find . -name "2.txt"
```
16) Просмотреть содержимое в реальном времени (команда grep), изучите как она работает:
```bash
tail -f dir_2/1.txt | grep "so"
```
17) Вывести несколько первых строк из текстового файла:
```bash
head -3 dir_2/1.txt
```
18) Вывести несколько последних строк из текстового файла:
```bash
tail -2 dir_2/1.txt
```
19) Просмотреть содержимое длинного файла (команда less), изучите как она работает:
```bash
less -N dir_2/1.txt
```
20) Вывести дату и время:
```bash
date
```
=========

Задание *
1) Отправить http запрос на сервер:
http://162.55.220.72:5005/terminal-hw-request
```bash
curl http://162.55.220.72:5006/terminal-hw-request
curl http://162.55.220.72:5005/get_method?name="Vladimir"&age=40
```
2) Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13:
```bash
#!/bin/bash
set -x
directory_path="/d/QA VKsendzov/DZ_01_Terminal/folder_2"
cd "$directory_path" && echo "1 cd" >> "$directory_path"/result.txt
file_path="$directory_path/result.txt"
for i in {1..3}; do mkdir ./"folder_2_$i"; done && echo "2 mkdir" >> "$file_path"
cd folder_2_1 && echo "3 cd" >> result.txt && echo "3 cd" >> "$file_path" 
touch 1.txt 2.txt 3.txt 1.json 2.json && echo "4 touch 1.txt 2.txt 3.txt 1.json 2.json" >> "$file_path"
for i in {1..3}; do mkdir ./"folder_2_1_$i"; done && echo "5 mkdir" >> "$file_path"
ls -la >> "$file_path"
mv ./{1.txt,2.txt} ../folder_2_2/ && echo "7 mv" >> "$file_path"
```
```bash
chmod +x dz_01_01_red3.sh
bash dz_01_01_red3.sh
```
---
Task 2
-

1. Сделать папку dir_1
```bash
mkdir dir_1
```
2. Зайти в папку dir_1
```bash
cd dir_1
```
3. Создать папку inner_dir_1
```bash
mkdir inner_dir_1
```
4. Посмотреть где ты находишься
```bash
pwd
```
5. Находясь в папке dir_1 создать пустой текстовый файл tf_1.txt
```bash
touch tf_1.txt
```
6. Находясь в папке dir_1 через команду cat создать текстовый файл tf_2.txt со следующими строками:
- the first 1
- the second 2
- the third 3
```bash
cat > tf_2.txt 
[Enter]
- the first 1
- the second 2
- the third 3
[Ctrl+C]
```
7. Зайти в папку inner_dir_1
```bash
cd inner_dir_1
```
8. Через cat сделать текстовый файл tf_3.txt  c любыми строками
```bash
cat > tf_3.txt 
[Enter]
one
two
three
[Ctrl+C]
```
9. Через cat добавить в текстовый файл tf_3.txt строку “the second 2”
```bash
cat >> tf_3.txt 
[Enter]
the second 2
[Ctrl+C]
```
10. Через cat добавить в текстовый файл tf_3.txt строку “the sec 2”
```bash
cat >> tf_3.txt 
[Enter]
the sec 2
[Ctrl+C]
```
11. Через cat добавить в текстовый файл tf_2.txt строку “the sec 3”
```bash
cat >> ../tf_2.txt 
[Enter]
the sec 3
[Ctrl+C]
```
12. Через cat добавить в текстовый файл tf_3.txt строку “the SeCoNd 2”
```bash
cat >> tf_3.txt 
[Enter]
the SeCoNd 2
[Ctrl+C]
```
13. Через cat добавить в текстовый файл tf_2.txt строку “the seConD 2”
```bash
cat >> ../tf_2.txt 
[Enter]
the seConD 2
[Ctrl+C]
```
14. Сделать текстовый файл tf_4.txt в котором будет 15 строк.

Пустые строки:
```bash
for i in {1..15}; do echo >> tf_4.txt; done
```
С нумерацией:
```bash
seq 15 | cat > tf_4.txt
```
15. Сделать текстовый файл tF_5.txt в котором будет 13 строк.

Пустые строки:
```bash
for i in {1..13}; do echo >> tF_5.txt; done
```
С нумерацией:
```bash
seq 13 | cat > tF_5.txt
```
16. Вывести список всех файлов в папке.
```bash
find . -maxdepth 1 -type f
```
17. Выйти из папки inner_dir_1
```bash
cd ..
```
18. Вывести содержимое файла tf_3.txt в терминал.
```bash
cat inner_dir_1/tf_3.txt
```
```bash
find -type f -name "tf_3.txt" -print
```
```bash
find -type f -name "tf_3.txt" -exec cat {} \;
```
19. Найти путь к файлу tf_4.txt
```bash
find -type f -name "tf_4.txt" -exec readlink -f {} \;
```
```bash
find -type f -name "tf_4.txt" | xargs readlink -f
```
20. Отчистить файл tf_4.txt от содержимого без удаления самого файла.
```bash
cat > inner_dir_1/tf_4.txt
```
21. Найти путь к файлам у которых есть  “tf” в названии.
```bash
find -type f -name "*tf *" | xargs readlink -f
```
22. Найти путь к файлам у которых есть  “tf” в названии и буквы в любом регистре.
```bash
find -type f -iname "*tf *" | xargs readlink -f
```
23. Найти строки в файлах где есть комбинация букв “sec” в текущей папке
```bash
grep -n sec *
```
24. Найти строки в файлах где есть комбинация букв “sec” в любом регистре в текущей папке
```bash
grep -ni sec *
```
25. Найти строки в файлах где есть только комбинация букв “sec” в текущей папке
```bash
grep -nw sec *
```
26. Найти строки в файлах где есть только комбинация букв “sec” в любом регистре в текущей папке
```bash
grep -niw sec *
```
27. Найти строки в файлах где есть комбинация букв “second” в текущей папке
```bash
grep -n second *
```
28. Найти строки в файлах где есть комбинация букв “second” в любом регистре в текущей папке
```bash
grep -ni second *
```
29. Найти строки в файлах где есть комбинация букв “second” во всех папках ниже уровнем
```bash
grep -rn second *
```
30. Найти только путь и название файла в строках которых есть комбинация букв “second” в текущей папке
```bash
grep -l -d skip second * | xargs readlink -f
```
```bash
grep -l -d skip second * | xargs realpath
```
31. Найти все строки во всех файлах где нет комбинации “second”
```bash
grep -rnv second
```
32. Найти только название и путь к файлам где нет комбинации “second”
```bash
grep -rvl second | xargs readlink -f
```
33. Вывести в терминал 4 последних строк любого текстового файла.
```bash
tail -n 4 tf_2.txt
```
34. Вывести в терминал 4 первые строки любого текстового файла.
```bash
head -n 4 tf_2.txt
```
35. Команда в одну строку. Создать папку и создать текстовый файл с содержиммым.
```bash
mkdir dir_1_1 && cat > dir_1_1/inn.txt
[Enter]
oki
doki
[Ctrl+C]
```
36. Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
```bash
grep -rlw sec | xargs mv -t dir_1_1
```
37. Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
```bash
mkdir dir_1_2 && grep -rlw sec | xargs cp -t dir_1_2
```
38. Команда в одну строку. Найти все строки c “sec” во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл.
```bash
grep -rh sec > new.txt 
```
39. Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово “sec”
```bash
grep -rlw sec | xargs rm
```
40. Просто вывести в терминал строку “Good job!!”
```bash
echo "Good job!!"
```
---