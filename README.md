<p align="center"><b>МОНУ НТУУ КПІ ім. Ігоря Сікорського ФПМ СПіСКС</b></p>
<p align="center">
<b>Лабораторна робота1</b><br/>
"Обробка списків з використанням базових функцій"<br/>
дисципліни "Вступ до функціонального програмування"
</p>
<p align="right"><b>Студент(-ка)</b>: Саюк Вадим Анатолійович 
<p align="right"><b>Група: КВ-21</p>
<p align="right"><b>Рік</b>: 2025</p>
  
##
##  <p align="center"><b>**ЗАГАЛЬНА УМОВА ЗАВДАННЯ**</b></p>

1. Створити список з п'яти елементів, використовуючи функції ***LIST*** і ***CONS***.
   Список має містити (напряму або у підсписках):
   - хоча б один символ
   - хоча б одне число
   - хоча б один не пустий підсписок
   - хоча б один пустий підсписок
2. Отримати голову списку.
3. Отримати хвіст списку.
4. Отримати третій елемент списку.
5. Отримати останній елемент списку.
6. Використати предикати ***ATOM*** та ***LISTP*** на різних елементах списку (по 2-3
приклади для кожної функції).
7. Використайти на елементах списку 2-3 інших предикати з розглянутих у розділі 4
навчального посібника.
8. Об'єднайти створений список з одним із його непустих підсписків. Для цього
використайте функцію ***APPEND***.

##
##  <p align="center"><b>**ЛІСТИНГ КОДУ**</b></p>
# ![Г1](https://img.shields.io/badge/1-brightgreen?style=for-the-badge) List general task
```lisp
CL-USER> (set 'a (cons '(1 2) (list 'b '() 3 '(4 c))))
((1 2) B NIL 3 (4 C))
CL-USER> a
((1 2) B NIL 3 (4 C))
```
# ![Г2](https://img.shields.io/badge/2-brightgreen?style=for-the-badge) Get a head
```lisp
CL-USER> (car a)
(1 2)
```
# ![Г3](https://img.shields.io/badge/3-brightgreen?style=for-the-badge) Get a tail
```lisp
CL-USER> (cdr a)
(B NIL 3 (4 C))
```
# ![Г4](https://img.shields.io/badge/4-brightgreen?style=for-the-badge) Get the third item in the list
```lisp
CL-USER> (third a)
NIL
```
# ![Г5](https://img.shields.io/badge/5-brightgreen?style=for-the-badge) Get the last item in the list
```lisp
CL-USER> (nth 4 a)
(4 C)
```
# ![Г6](https://img.shields.io/badge/6-brightgreen?style=for-the-badge) Use ***ATOM*** та ***LISTP***
```lisp
CL-USER> (atom (first a))
NIL
CL-USER> (atom (third a))
T
CL-USER> (atom (second (nth 4 a)))
T
CL-USER> (listp (first a))
T
CL-USER> (listp (second a))
NIL
CL-USER> (listp (nth 4 a))
T
```
# ![Г7](https://img.shields.io/badge/7-brightgreen?style=for-the-badge) Other predicates
```lisp
CL-USER> (evenp (first (nth 4 a)))
T
CL-USER> (numberp (second (nth 4 a)))
NIL
CL-USER> (< (first (first a)) (nth 3 a))
T
```
# ![Г8](https://img.shields.io/badge/8-brightgreen?style=for-the-badge) Merge the created list
```lisp
CL-USER> (append a (nth 4 a))
((1 2) B NIL 3 (4 C) 4 C)
```
