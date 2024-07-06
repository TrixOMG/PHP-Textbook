# PHP

## Project setup

Создаётся папка по пути:

D:/FOR PHP/htdocs/folder_name

(Без цифр в названи, иначе работать не будет)

в ней создаётся файл index.php

для перехода по захосченному файлику, который мы только что создали, надо в браузере забить:

http://localhost/folder_name/

Для отображения сообщения в браузере можно использовать следующий код:

```php
<?php
  echo"helo";
?>
```

### Extension для браузеров (Live Server)

В него нужно добавить:

- Actual Server Adress
  (просто скопируй ссылку localhost по которой перешёл до этого)

- Live Server Adress
  (чтобы его получить, на открытом файлике
  index.php нажми Ctrl + Shift + P, после чего впиши
  Live Server, и выбери функцию "Open With Live Server",
  откроется браузер и можно будет просто копирнуть ссылку оттуда)

## Комментарии в коде

Пишутся так же, как и в JS, // для "однострочного", /\* для "многострочного"

## Разметка и другие языки внутри PHP

В PHP можно использовать HTML, CSS и JS при помощи тегов

```php
<?php
  echo "helo";
?>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1>Hello World</h1>
</body>
</html>
```

## Переменные

Всё те же типы что и в JS, однако
когда идёт echo булевых переменных, выводится следующее:

- true = 1
- false = пустая строка.

```php
<?php
  $name = 'homer simpson';
  $food = 'pizza';
  echo "Hello $name, you like $food <br>";

  $number = 10.4;
  echo "$number <br>";

  $employed = false;
  $unhappy = true;

  echo "$employed <br>";
  echo "$unhappy <br>";

  $total = null;

  $total = $number * 2.3;

  echo "TOTAL: $total <br>";
?>
```

## Операторы в PHP

Всё опять так же как и в JS.

```php
<?php
  $x = 10;
  $y = 2;
  $z = null;

  $z = $x + $y;
  $z = $x / $y;
  $z = $x * $y;
  $z = $x ** $y; // степень
  $z = $x % $y; // остаток от деления

  echo "$z <br>";

  $counter = 0;
  $counter++;
  $counter--;
  $counter+= 3;
  $counter-= 3;

  echo "COUNTER: $counter <br>";

  //Порядок исполнения операторов (слева направо):
  // () ** % * / + -

?>
```
