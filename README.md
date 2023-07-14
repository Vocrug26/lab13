<h1 align="center">МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ»</h1>
<p align="center">Лабораторная работа №7</p>
<p align="center"></p>
<br>
<p align="right">Работу выполнил Гурков Владислав Викторович</p>
<p align="right">Работу проверил Соболев Евгений Игоревич</p>


### **Цели и задачи:**
Спросите город пользователя с помощью формы. Результат запишите в переменную $city. Выведите на экран фразу 'Ваш город: %Город%'.
Решите предыдущую задачу так, чтобы пользователь не мог вводить теги и сломать сайт.
Сделайте так, чтобы форма после отправки скрывалась.
Спросите имя пользователя с помощью формы. Результат запишите в переменную $name. Выведите на экран фразу 'Привет, %Имя%'.
Спросите у пользователя имя, возраст, а также попросите его ввести сообщение (его сделайте в textarea). Выведите эти данные на экран в формате, приведенном под данной задачей. Позаботьтесь о том, чтобы пользователь не мог вводить теги (просто удаляйте их) и таким образом сломать сайт.
Спросите возраст пользователя. Если форма была отправлена и введен возраст, то выведите его на экран, а форму уберите. Если же форма не была отправлена (это будет при первом заходе на страницу) - просто покажите ее.
Спросите у пользователя логин и пароль (в браузере должен быть звездочками). Сравните их с логином $login и паролем $pass, хранящихся в файле. Если все верно - выведите 'Доступ разрешен!', в противном случае - 'Доступ запрещен!'. Сделайте так, чтобы скрипт обрезал концевые пробелы в строках, которые ввел пользователь.
Спросите имя пользователя с помощью формы. Результат запишите в переменную $name. Сделайте так, чтобы после отправки формы значения ее полей не пропадали.
Спросите у пользователя имя, а также попросите его ввести сообщение (textarea). Сделайте так, чтобы после отправки формы значения его полей не пропадали.
Дана строка 'ahb acb aeb aeeb adcb axeb'. Напишите регулярку, которая найдет строки ahb, acb, aeb по шаблону: буква 'a', любой символ, буква 'b'.
Дана строка 'aba aca aea abba adca abea'. Напишите регулярку, которая найдет строки abba adca abea по шаблону: буква 'a', 2 любых символа, буква 'a'.
Дана строка 'aba aca aea abba adca abea'. Напишите регулярку, которая найдет строки abba и abea, не захватив adca. Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aba, abba, abbba по шаблону: буква 'a', буква 'b' любое количество раз, буква 'a'.
Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aa, aba, abba, abbba по шаблону: буква 'a', буква 'b' любое количество раз (в том числе ниодного раза), буква 'a'.
Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aa, aba по шаблону: буква 'a', буква 'b' один раз или ниодного, буква 'a'.
Дана строка 'ab abab abab abababab abea'. Напишите регулярку, которая найдет строки по шаблону: строка 'ab' повторяется 1 или более раз.
Дана строка 'a.a aba aea'. Напишите регулярку, которая найдет строку a.a, не захватив остальные.
Дана строка '2+3 223 2223'. Напишите регулярку, которая найдет строку 2+3, не захватив остальные.
Дана строка '23 2+3 2++3 2+++3 345 567'. Напишите регулярку, которая найдет строки 2+3, 2++3, 2+++3, не захватив остальные (+ может быть любое количество).
Дана строка '23 2+3 2++3 2+++3 445 677'. Напишите регулярку, которая найдет строки 23, 2+3, 2++3, 2+++3, не захватив остальные.
Дана строка '*+ *q+ *qq+ *qqq+ *qqq qqq+'. Напишите регулярку, которая найдет строки *q+, *qq+, *qqq+, не захватив остальные.
Дана строка '*+ *q+ *qq+ *qqq+ _qqq qqq+'. Напишите регулярку, которая найдет строки _+, *q+, *qq+, *qqq+, не захватив остальные.
Дана строка 'aba accca azzza wwwwa'. Напишите регулярку, которая найдет все строки по краям которых стоят буквы 'a', и заменит каждую из них на '!'. Между буквами a может быть любой символ (кроме a).
Задание 1

<?php
if (!empty($_GET['city'])) {
    $city = $_GET['city'];
    echo 'Ваш город: ' . $city;
}
?>
<form action="" method="get">
    Город: <input type="text" name="city"><br>
    <input type="submit">
</form>
Задание 2

<?php
if (!empty($_GET['city'])) {
    $city = strip_tags($_GET['city']);
    echo 'Ваш город: ' . $city;
}
?>
<form action="" method="get">
    Город: <input type="text" name="city"><br>
    <input type="submit">
</form>
Задание 3

<?php
if (isset($_POST['city'])) {
    if (!empty($_POST['city'])) {
        $city = strip_tags($_POST['city']);
        echo 'Ваш город: ' . $city;
    } else {
        echo 'Город не был указан';
    }
} else {
?>
    <form action="" method="post">
        Город: <input type="text" name="city"> <br>
        <input type="submit">
    </form>
<?php
} ?>
Задание 4

<?php
if (!empty($_GET['name'])) {
    $name = strip_tags($_GET['name']);
    echo 'Привет, ' . $name;
}
?>
<form action="" method="get">
    Имя: <input type="text" name="name"><br>
    <input type="submit">
</form>
Задание 5

<?php
if (!empty($_GET['name']) & isset($_GET['age']) & !empty($_GET['message'])) {
    $name = strip_tags($_GET['name']);
    $age = strip_tags($_GET['age']);
    $message = strip_tags($_GET['message']);
    echo 'Имя: ' . $name . "</br>";
    echo 'Возраст: ' . $age . "</br>";
    echo 'Соосбщение: ' . $message . "</br>";
}
?>
<form action="" method="get">
    Имя: <input type="text" name="name"><br>
    Возраст: <input type="text" name="age"><br>
    Введите сообщение: <textarea name="message" rows="5" cols="50"> </textarea> <br>
    <input type="submit">
</form>
Задание 6

<?php
if (!isset($_POST['age'])) {
?>
    <form action="" method="POST">
        Возраст: <input type="text" name="age"> <br>
        <input type="submit">
    </form>
<?php
} else {
?>
<?php
    if (isset($_POST['age'])) {
        $age = strip_tags($_POST['age']);
        echo 'Возраст: ' . $age;
    }
} ?>
Задание 7

<?php
if (!empty($_GET['login']) & !empty($_GET['password'])) {
    $login = "user_123";
    $pass = "123456789";
    $formLogin = trim($_GET['login']);
    $formPassword = trim($_GET['password']);
    if ($login == $formLogin & $pass == $formPassword) {
        echo 'Доступ разрешён';
    } else {
        echo 'Доступ запрещён';
    }
}
?>
<form action="" method="get">
    Логин: <input type="text" name="login"> <br>
    Пароль: <input type="password" name="password"> <br>
    <input type="submit">
</form>
Задание 8

<?php
if (!empty($_GET['name'])) {
    $name = strip_tags($_GET['name']);
    echo 'Привет, ' . $name;
}
?>
<form action="" method="get">
    Имя: <input type="text" name="name" value="<?php if (isset($_GET['name'])) echo $_GET['name']; ?>"> <br>
    <input type="submit">
</form>
Задание 9

<?php
if (!empty($_GET['name']) & !empty($_GET['message'])) {
    $name = strip_tags($_GET['name']);
    $message = strip_tags($_GET['message']);
    echo 'Имя: ' . $name . "</br>";
    echo 'Соосбщение: ' . $message . "</br>";
}
?>
<form action="" method="get">
    Имя: <input type="text" name="name" value=" <?php if (isset($_GET['name'])) echo $_GET['name']; ?>"><br>
    Введите сообщение: <textarea name="message" rows="5" cols="50">
    <?php if (isset($_GET['message'])) echo $_GET['message']; ?>
    </textarea> <br>
    <input type="submit">
</form>
Задание 10

$string = 'ahb acb aeb aeeb adcb axeb';
preg_match_all('/a.{1}b/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 11

$string = 'aba aca aea abba adca abea';
preg_match_all('/a.{2}a/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 12

$string1 = 'aba aca aea abba adca abea';
preg_match_all('/ab.{1}a/i', $string1, $array1);
echo '<pre>';
var_dump($array1);
echo '</pre>';

$string2 = 'aa aba abba abbba abca abea';
preg_match_all('/ab+a/i', $string2, $array2);
echo '<pre>';
var_dump($array2);
echo '</pre>';
Задание 13

$string = 'aa aba abba abbba abca abea';
preg_match_all('/ab*a/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 14

$string = 'aa aba abba abbba abca abea';
preg_match_all('/ab{0,1}a/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 15

$string = 'ab abab abab abababab abea';
preg_match_all('/(ab)+/i', $string, $array);
echo '<pre>';
var_dump($array[0]);
echo '</pre>';
Задание 16

$string = 'a.a aba aea';
preg_match_all('/a\.a/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 17

$string = '2+3 223 2223';
preg_match_all('/2\+3/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 18

$string = '23 2+3 2++3 2+++3 345 567';
preg_match_all('/2\++3/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 19

$string = '23 2+3 2++3 2+++3 445 677';
preg_match_all('/2\+*3/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 20

$string = '*+ *q+ *qq+ *qqq+ *qqq qqq+';
preg_match_all('/\*q+\+/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 21

$string = '*+ *q+ *qq+ *qqq+ *qqq qqq+';
preg_match_all('/\*q*\+/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Задание 22

$string = 'aba accca azzza wwwwa';
preg_match_all('/a[^a]+a/i', $string, $array);
echo '<pre>';
var_dump($array);
echo '</pre>';
Вывод:
После выполнения данной лабораторной работы я улучшила свои навыки работы с таким языком программирования как PHP. Все поставленные цели и задачи были выполнены.# lab13
