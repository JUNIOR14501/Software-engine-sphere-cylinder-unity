# Software-engine-sphere-cylinder
Проект направлен на разработку программного решения для 
визуализации пересечения двух геометрических тел - сферы и цилиндра - в 
трехмерном пространстве. Целью данного проекта является создание 
инструмента, который позволит пользователям визуально исследовать и 
анализировать взаимное расположение и пересечение этих тел.
Задача включает в себя разработку интерфейса, который позволит 
пользователям взаимодействовать с программой, определяя параметры сферы и 
цилиндра, а также их положение в пространстве. Данное взаимодействие 
позволит пользователям задавать произвольные значения параметров этих 
геометрических тел.
Основной задачей также является разработка алгоритма определения 
пересечения сферы и цилиндра при заданных параметрах и их позициях в 
пространстве. После обнаружения пересечения необходимо определить 
параметры пересекающихся линий и визуализировать видимые части объектов 
сцены.
Такая программа будет не только демонстрировать пересечение 
геометрических тел, но и позволит пользователям манипулировать сценой, 
вращая тела в пространстве для лучшего понимания их взаимного 
расположения и пересечения с разных углов обзора.
Таким образом, основная цель этого проекта - создание программного 
комплекса, который предоставит пользователям инструмент для визуального 
анализа пересечения сферы и цилиндра в трехмерном пространстве, что может 
быть полезно в областях, связанных с геометрией, моделированием и 
визуализацией данных.
![image](https://github.com/user-attachments/assets/37d57887-6d67-4e85-a096-afc4c9d0399f)

Интерфейс программы для задания параметров сферы и цилиндра:
1. Параметры сферы:
Радиус сферы: Поле для ввода числового значения радиуса сферы.
Координаты центра сферы (x, y, z): Три поля для ввода числовых значений координат центра сферы в трехмерном пространстве.
2. Параметры цилиндра:
Радиус основания цилиндра: Поле для ввода числового значения радиуса основания цилиндра.
Высота цилиндра: Поле для ввода числового значения высоты цилиндра.
Координаты центра основания цилиндра (x, y, z): Три поля для ввода числовых значений координат центра основания цилиндра в трехмерном пространстве.
3. Управление сценой:
Кнопка "Начать моделирование": После ввода всех параметров сферы и цилиндра пользователь может запустить процесс визуализации и анализа пересечения.
Такой интерфейс позволит пользователям удобно вводить параметры геометрических тел и манипулировать сценой для визуального анализа пересечения сферы и цилиндра в трехмерном пространстве.

Дополнительные функции.
Также при уже работающей программе, возможно менять размер, а также задавать некоторый угол вращения фигуры вокруг своей оси с помощью кнопок клавиатуры.
Кнопки T G отвечают за поворот цилиндра вокруг оси х.
Кнопки F H отвечают за поворот цилиндра вокруг оси у.
Кнопки Z X отвечают за увеличение размера цилиндра.
Кнопки C V отвечают за увеличение размера сферы. 

3.	Структуры данных.
На начальном этапе основные данные, полученные вводом в пользовательский интерфейс, заносятся в два класса Sphere и Cylinder(2).
![image](https://github.com/user-attachments/assets/9488ca21-2bdc-4153-986b-75965a118c5a)
Рисунок 2 – Классы cylinder и sphere.

Дальше используя эти данные можно начинать строить поверхности фигур.
Для построения фигур в данной программе используется инструмент юнити под названием mesh.
В Unity, "mesh" (сетка) представляет собой объект, который определяет форму графического объекта путем определения вершин, граней и других данных, необходимых для отображения трехмерной модели. Принцип работы mesh в Unity основан на использовании его компонентов для создания и отображения 3D-моделей. Вот основные компоненты и принципы работы mesh в Unity:

1. Вершины (Vertices):
Вершины представляют собой точки в трехмерном пространстве и являются основой для создания сетки. Они определяют форму объекта. Каждая вершина имеет свои трехмерные координаты (x, y, z).

2. Треугольники (Triangles):
Треугольники (или полигоны) состоят из трех вершин и определяют поверхность объекта. Меш составляется из этих треугольников, которые определяют форму и структуру модели.
Для нахождения вершин использовались параметрически заданные формулы поверхностей фигур. 
У цилиндра это: 
1)	Боковая поверхность (представляющая собой цилиндрическую поверхность);
 ![image](https://github.com/user-attachments/assets/d7e3182e-94b9-473f-9dd0-87d2faf9ffe0)

2)	торцевые поверхности( представляющие собой плоскости, ограниченные окружностью).
 ![image](https://github.com/user-attachments/assets/1bf1eace-7c41-4dc9-913b-d0ac9d0f2e0d)

Где окружность задана формулой
![image](https://github.com/user-attachments/assets/e4a0bc0c-3800-46a0-8132-e1cecb6ecb43)


У сферы поверхность задана поверхностями двух полусфер:
![image](https://github.com/user-attachments/assets/47ed256b-01c1-46fa-a6e7-e36df0e3e6b4)
  
где 
![image](https://github.com/user-attachments/assets/d847b92a-8fe4-4d97-a839-9319d25fe8fd)

Методы нахождения треугольников для каждой поверхности были сделаны по разному, вот один для примера (3).
![image](https://github.com/user-attachments/assets/49a00a77-fa0a-4b0e-81a3-b8cdaf02d684)
Функция для задания треугольников для боковой поверхности цилиндра.

Далее с помощью написанных функций и инструментов юнити создаем фигуру, на некотором пустом объекте в пространстве. 
![image](https://github.com/user-attachments/assets/e82c8f8a-c38e-4311-8214-cbbb1d35c214)
Функция отрисовки цилиндра.

4. Методы поиска и параметры пересечений
Описание метода нахождения пересечений.
Так как одна из фигур в задании является сферой, существование пересечений можно определить следующим способом:
1)	создать массивы точек, в которых хранятся все вершины, по которым строится цилиндр;
2)	если сфера будет пересекаться с цилиндром хоть в одной точке, значит расстояние от центра сферы до этой точки меньше или равно радиусу сферы;
3)	значит можно проверить все точки, лежащие в этом массиве массиве, на прохождение данного условия.  
Дальше исходя из этого можно написать некоторые условия определения с какой именно частью поверхности будет пересекаться сфера.
Пример такого кода:
 ![image](https://github.com/user-attachments/assets/8c80cca1-9d3f-4b9f-a8c4-3e8c453dadc7)
Функция проверки наличия пересечения.

Так же можно проверить и пересечения другого вида добавив пару условий. 
Например, можно найти что пересечением сферы и цилиндра является этот же цилиндр, если выполняется условие, что, все проверенные точки поверхностей меньше радиуса сферы, и не имеют точек пересечения с поверхностью сферы. Следовательно, цилиндр будет лежать внутри.

6. Примеры и тесты.
Описание и создание тестовых сценариев для проверки наличия пересечений между телами при различных значениях параметров и положениях в пространстве.
![image](https://github.com/user-attachments/assets/65b78c39-2607-4b10-8ed8-7069b9f1a8ef)
Тест 1.

Первый тест(начальный).
На нем заданы сфера с:
Радиусом  = 10;
Начальным положением = 0 0 0;
Цветом = blue;
И цилиндр с :
Радиусом = 10;
Высотой = 15;
Начальным положением = 5 5 5;
Цветом = green; 
Из их пересечения видно, что сфера пересекает цилиндр по нижней и боковой поверхности, что и написала нам программа.

![image](https://github.com/user-attachments/assets/c6eb9479-bc0d-4c63-8e92-8bc3569812ea)
Тест 2.

Второй тест(уменьшение/увеличение).
На нем заданы сфера с:
Радиусом = 10, но с помощью кнопки уменьшения, уменьшенная до радиуса = 3;
Начальным положением = 0 0 0;
Цветом = blue;
И цилиндр с :
Радиусом = 10;
Высотой = 15;
Начальным положением = 5 5 5;
Цветом = green; 
Из их пересечения видно, что сфера теперь не пересекает поверхности цилиндра, что и написала нам программа.

![image](https://github.com/user-attachments/assets/5555ff35-3ec7-4e7c-8386-0a434c339cd1)
Тест 3.

Третий тест (поворот).
На нем заданы сфера с:
Радиусом = 10, но с помощью кнопки уменьшения, уменьшенная до радиуса = 3;
Начальным положением = 0 0 0;
Цветом = blue;
И цилиндр с:
Радиусом = 10;
Высотой = 15;
Начальным положением = 5 5 5;
Цветом = green; 
И углом поворота по оси Х = 90 градусов.
Из их пересечения видно, что сфера продолжает не пересекать поверхности цилиндра, что и написала нам программа.


