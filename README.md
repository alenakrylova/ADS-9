# Алгоритмы и структуры данных (ADS-9)

![GitHub pull requests](https://img.shields.io/github/issues-pr/NNTU-CS/ADS-9)
![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/NNTU-CS/ADS-9)

Срок выполнения задания:

**по 26 мая** 

![Relative date](https://img.shields.io/date/1716757200) 

## Задание

> Разработать версию бинарного дерева поиска для частотного анализа слов из текстового файла. Загрузить и проанализировать англоязычную версию романа Л.Толстого "Война и мир".

## Пояснение

В данной работе нужно взять за основу реализацию бинарного дерева поиска и адаптировать его для анализа слов из текстового файла. 

Под анализом в данной работе понимается **частотный** анализ встречаемости слов, то есть какое слово сколько раз встретилось.

Шаблон дерева необходимо поместить в **include/bst.h**.

Далее, необходимо определить функцию __BST\<std::string\> makeTree(const char* filename)__, расположенную в файле **alg.cpp**. Функция должна принимать строку с именем файла для анализа и возвращать построенное дерево, содержащее слова из предложенного файла **src/war_peace.txt**. Под словом понимается непрерывная последовательность латинских букв, преобразованная к НИЖНЕМУ регистру.

**Важно!**

Мы анализируем из файла только последовательности символов в ASCII-кодировке, латинские буквы. Все другие сочетания символов игнорируются! Цифровые последовательности тоже игнорируются! Заглавные буквы должны преобразовываться в нижний регистр! 

## Пример работы с файлом в С++

```cpp
    const char* filename = "name.txt"

    // открываем файл на чтение
    std::ifstream file(filename);

    // если файл не открылся, прекращаем работу
    if (!file) {
        std::cout << "File error!" << std::endl;
        return;
    }

    int count=0;

    // читаем содержимое файла посимвольно
    while(!file.eof())
    {
        int ch=file.get();
        count++;
    }
    // закрываем файл
    file.close();
    // выводим число символов
    std::cout << count <<std::endl;
```