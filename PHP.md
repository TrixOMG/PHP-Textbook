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

## $\_GET and $\_POST variables

$\_GET

- данные добавляются в url страницы
- не безопасен
- имеет лимит по символам (char limit)
- Bookmark is possible w/ values
- Better for a search page

$\_POST

- Data is packaged inside the body of HTTP request
- More Secure
- No data limit
- Cannot bookmark
- Requests are not cached
- Better for submitting credentials

### $\_GET

Получение данных с формы.
У формы обязательно должен быть атрибут action
который укажет к какому именно файлу php мы
посылаем данные.
и атрибут method.

Конкатенация string происходит через оператор "."
Если переменная простая, её можно вставить в string
как есть.
Если переменная сложная, как в примере ниже,
нужны {}

При использовании get все данные засабмиченной
формы отобразятся в адресе страницы,
это небезопасно.

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>_GET and _POST variables</title>
</head>
<body>
  <form action="index.php" method="get">
    <label for="username">username:</label>
    <br>
    <input type="text" id="username" name="username"/>
    <br>

    <label for="password">password:</label>
    <br>
    <input type="text" id="password" name="password"/>
    <br>

    <input type="submit" value="Log In"/>
  </form>
</body>
</html>

<?php
echo $_GET["username"] . "<br>";
echo "{$_GET["password"]}<br>";
?>
```

### $\_POST

При использовании \_POST данные засабмиченной
формы не отображаются в адресе страницы.

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>_GET and _POST variables</title>
</head>
<body>
  <form action="index.php" method="post">
    <label for="quantity">quantity:</label>
    <br>
    <input type="number" name="quantity" id="quantity"/>
    <br>
    <input type="submit" value="Total"/>
  </form>
</body>
</html>

<?php
  $item = 'pizza';
  $price = 5.99;
  $quantity = $_POST["quantity"];
  $total = $quantity * $price;
  echo "You have ordered: {$quantity} {$item}/s with total price of \${$total}<br>";
?>
```

## Math functions

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math functions</title>
</head>
<body>
  <form action="index.php" method="post">
    <label>x:</label>
    <input type="text" name="x"/>
    <br>
    <label>y:</label>
    <input type="text" name="y"/>
    <br>
    <label>z:</label>
    <input type="text" name="z"/>
    <br>

    <input type="submit" value="Total"/>
  </form>
</body>
</html>

<?php
  $x = $_POST['x'];
  $y = $_POST['y'];
  $z = $_POST['z'];
  $total = null;

  //$total = abs($x);
  //$total = round($x);
  //$total = floor($x);
  //$total = ceil($x);
  //$total = pow($x, $y);
  //$total = max($x, $y, $z);
  //$total = min($x, $y, $z);
  //$total = pi();
  //$total = rand(1, 100);

  echo $total;
?>
```

## If else statements

Идентично JS, однако else if пишется слитно.

```php
<?php
  $age = 101;
  if($age > 18) {
    ...
  } elseif($age < 50) {
    ...
  } else {
    ...
  }
?>
```

## Logical operators

Идентично JS.

```php
<?php
  $statement1 = true;
  $statement2 = false;

  if($statement1 && $statement2) {
    echo "statement1 and statement2 are true";
  } elseif ($statement1 || $statement2) {
    echo "statement1 or statement2 is true";
  } elseif (!$statement1) {
    echo "statement1 is false";
  }
?>
```

## Switch statements

Идентично JS.

```php
<?php
  $color = "green";

  switch($color) {
    case "red":
      echo "color is red";
      break;
    case "green":
      echo "color is green";
      break;
    case "blue":
      echo "color is blue";
      break;
    default:
      echo "color is not red, green or blue";
  }
```

## For loops

Идентично JS.

```php
<?php
  for($i = 0; $i < 10; $i++) {
    echo $i;
  }
?>
```

## While loops

Идентично JS.

```php
<?php
  $i = 0;
  while($i < 10) {
    echo $i;
    $i++;
  }
?>
```

## Arrays + Foreach loops

```php
<?php
  $colors = array("red", "green", "blue");
  array_push($colors, "yellow", "purple");
  array_pop($colors);
  array_shift($colors);
  $colors = array_reverse($colors);
  echo count($colors) . "<br>";

  foreach($colors as $color) {
    echo $color . "<br>";
  }
?>
```

## Associative arrays

An arrays made of key-value pairs
(Like Map in JS)

Функции, применяемые к обычным массивам работают
и с ассоциативными массивами.

```php
<?php
  $ages = array(
    "Peter" => 35,
    "Ben" => 37,
    "Joe" => 43
  );
  echo $ages["Peter"] . "<br>";

  $ages["Peter"] = 36;
  $ages["Mary"] = 23;

  echo $ages["Peter"] . "<br>";

  $keys = array_keys($ages);
  $vals = array_values($ages);

  print_r($keys);
  echo "<br>";
  print_r($vals);
  echo "<br>";

  foreach($ages as $key => $value) {
    echo $key . " is " . $value . " years old <br />";
  }
?>
```

## isset() + empty()

- isset(): true if variable is declared and
  not null

- empty(): true if variable is not declared,
  false, null, ""

```php
<?php
  $name = "John"; //false, 1, null

  if(isset($name)) {
    echo "variable name is set";
  } else {
    echo "variable name is not set";
  }
  echo "<br>";

  if(empty($name)) {
    echo "variable name is empty";
  } else {
    echo "variable name is not empty";
  }
?>
```

Checking if form is filled:

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>isset() + empty()</title>
</head>
<body>
  <form action="index.php" method="post">
    <label>username:</label>
    <br>
    <input type="text" name="username" />
    <br>
    <label>password:</label>
    <br>
    <input type="password" name="password" />
    <br>
    <input type="submit" name="login" value="Log In"/>
    <br>
  </form>
</body>
</html>

<?php

  if(isset($_POST["login"])) {
    $username = $_POST["username"];
    $password = $_POST["password"];

    if(empty($username)) {
      echo "Username cannot be empty";
    } elseif (empty($password)) {
      echo "Password cannot be empty";
    } else {
      echo "Hello {$username}";
    }
  }
?>
```

## Work with Radio buttons in PHP

Радиокнопки должны иметь одинаковый атрибут name
чтобы нельзя было выбрать несколько вариантов
одного значения.

По значению атрибута name мы получаем
value в PHP через методы $\_POST или $\_GET.

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Radio buttons</title>
</head>
<body>
  <form action="index.php" method="post">
    <input type="radio" value="Visa" name="card"/>
    <label >Visa</label> <br>
    <input type="radio" value="Mastercard" name="card"/>
    <label >Mastercard</label> <br>
    <input type="radio" value="Mir" name="card"/>
    <label>Mir</label> <br>
    <input type="submit" name="confirm" value="Confirm"/>
  </form>
</body>
</html>

<?php
  if(isset($_POST['confirm'])) {
    if(isset($_POST['card'])) {
      $credit_card = $_POST['card'];
      echo $credit_card;
    } else {
      echo "Please select credit card";
    }
  }
?>
```

## Work with Checkboxes in PHP

Атрибут name можно задать "массивом" добавив
после привычного ключа []
(как в примере и блоке ниже)

> name="foods[]"

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Checkboxes</title>
</head>
<body>
  <form action="index.php" method="post">
    <input type="checkbox" name="foods[]" value="Pizza"/>
    Pizza <br>
    <input type="checkbox" name="foods[]" value="Hamburger"/>
    Hamburger <br>
    <input type="checkbox" name="foods[]" value="Hotdog"/>
    Hotdog <br>
    <input type="checkbox" name="foods[]" value="Taco"/>
    Taco <br>
    <input type="submit" name="submit"/> <br>
    </form>
</body>
</html>

<?php
  if(isset($_POST['submit'])) {
    $foods = $_POST['foods'];

    foreach($foods as $food) {
      echo $food . "<br>";
    }
  }
?>
```

## Functions in PHP

Почти то же самое, что и в JS.

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>isset() + empty()</title>
</head>
<body>
  <form action="index.php" method="post">
    <input type="checkbox" name="foods[]" value="Pizza"/>
    Pizza <br>
    <input type="checkbox" name="foods[]" value="Hamburger"/>
    Hamburger <br>
    <input type="checkbox" name="foods[]" value="Hotdog"/>
    Hotdog <br>
    <input type="checkbox" name="foods[]" value="Taco"/>
    Taco <br>
    <input type="submit" name="submit"/> <br>
    </form>
</body>
</html>

<?php
  if(isset($_POST['submit'])) {
    $foods = $_POST['foods'];
    printArray($foods, 123);
  }

  function printArray($array, $number) {
    foreach($array as $food) {
      echo "Food: ". $number . " " . $food . "<br>";
    }
  }
?>
```

## Useful String Functions in PHP

```php
<?php
  $username = '       Pavel Nikitin    ';
  echo strtolower($username). '<br>';
  echo strtoupper($username). '<br>';
  echo trim($username) . '<br>';
  echo str_pad($username, 30, "*", STR_PAD_BOTH) ."<br>";
  echo str_replace("P", "-", $username) . '<br>';
  echo strrev($username) . '<br>';
  echo str_shuffle($username) . '<br>';
  echo strcmp($username, 'Pavel') . '<br>';
  echo strlen($username) . '<br>';
  echo strpos($username, 'N') . '<br>';
  echo substr($username, 0, 10) . '<br>';

  $fullname = explode(" ", trim($username));

  foreach ($fullname as $caracters) {
    echo "Explode: ".$caracters . "<br>";
  }

  $userArr = array('Pavel', 'Nikitin');

  echo "Implode: ".implode("-", $userArr) . "<br>";
?>
```
