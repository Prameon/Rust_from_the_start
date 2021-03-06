# Rust - Язык Программирования.
*"Язык, позволяющий каждому создавать надёжное и эффективное программное обеспечение"*


[Присоеденяйтесь на Discord](https://discord.gg/DgPFg73jmb)
___


![alt text](https://www.rust-lang.org/static/images/rust-logo-blk.svg)

версия rust 1.56.1.(1 Ноября 2021)

Полезные ссылки:
- [Официальный Сайт](https://www.rust-lang.org/ru/)
- [Github](https://github.com/rust-lang/rust) 
- [Docs.rs](https://docs.rs/) 
- [Std](https://doc.rust-lang.org/std/) 
- [Crates.io](https://crates.io/)
- [Коды ошибок](https://doc.rust-lang.org/error-index.html)
---
## Установка Rust.
- [Инструкция](https://www.rust-lang.org/ru/tools/install)
- [или Инструкция на doc.rust-lang.ru](https://doc.rust-lang.ru/book/ch01-01-installation.html)

Oбновить Rust:
 ```
 $  rustup update stable
 ```
Проверить версию Rust
 ```
 $ rustc --version
 ```
---
Учебники:

- [Rust book](https://doc.rust-lang.org/book/)
- [Rust book - на русском](https://doc.rust-lang.ru/book/)
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
- [Rust by Example - на русском](https://doc.rust-lang.ru/stable/rust-by-example/)

- [Тур по Rust](https://tourofrust.com/00_ru.html)
- [Учебник Roguelike - In Rust ](https://bfnightly.bracketproductions.com/chapter_0.html)
- [Struct ↔ JSON](https://riptutorial.com/rust/example/3782/struct---json)

# Глава 1. Первый проект.
## Создать и запустить проект с помощью Cargo.
__Cargo__ является системой сборки и менеджером пакетов в Rust.
***
__Терминал(powershell):__
```
$ cargo new name
$ cd name
$ cargo run
( $ cargo build ) 
```
Вывод терминала:
```  
Hello, world!
```
Файлы проекта:
 - name \ src \ main.rs (вход в программу, вы пишете код приложения)
 - name \ Cargo.toml (для подключения сторонних библиотек)
***


### Создаем первый проект __name__.

__1. Для создания проекта нужно воспользоваться терминалом.__
```cargo 
$ cargo new name
```
*где __name__ названее вашего проекта.
(также я нахожусь в папке C:\Coding\Rust\)*

```cargo
далее нужно перейти в каталог name:
$ cd name

(вернутся назад)
$ cd..
```
2. Запустить проект команда в каталоге проекта.
```cargo 
$ cargo run
```
или так, но запустить в ручную файл name.exe. 

В папке:
...\name\target\debug\name.exe
```cargo 
$ cargo build 
```

### Выводит:
```cargo  
$ cargo run     
   Compiling name v0.1.0 (C:\Coding\Rust\name)
    Finished dev [unoptimized + debuginfo] target(s) in 1.22s
     Running `target\debug\name.exe`
Hello, world!
```
Вывод в консоли:
```  
Hello, world!
```
### Проект name.
Разберем проект который мы создали с выше.
- папка __\src__ (с нашим кодом)
- Cargo.toml (для подключения сторонних библиотек)


файл src\main.rs
```rust
fn main() {
    println!("Hello, world!"); 
}
// fn main(){} вход в программу
// println!("") макрос для печати текста
// Hello, world! текст для печати.
// ;
``` 

файл Cargo.toml
```toml  
[package]
name = "name" 
version = "0.1.0" 
edition = "2021" 

#Смотрите больше ключей и их определений на https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
# ниже добавляются сторонние библиотеки 
```
`edition = "2021"` - указывает год выпуска стабильной версии Rust, которую я сейчас использую.

Выводы:

- Мы создали проект
- запустили проект. . . и посмотрели что выводит.
- посмотрели файлы которые были созданы.   

## Вход в программу `fn main()`
`fn main()` - Это главная функция с которой происходи запуск программы.

файл src\main.rs
```rust
fn main() {

}
``` 
В это функции мы пишем код. а точней мы пишем в фигурных скобках `{..}`, это тело функции. 

`{}` после того как программа дойдет до закрытия скобок, она выполнится полностью и закроется, а также данные которые находятся в теле функции  будут очищены.

## Вывод в консоль.`println!("Вывод в консоль:{}", x);`
В данном случае наша программа ничего не делает, но при создании проекта с помощью cargo. Мы получаем код который выводить в консоли текст "Hello, world!".
```rust
fn main() {
    println!("Hello, world!"); 
}
``` 
именно с этой фразы начинается любое программирование.

мы часто будем использовать макрос `println!("Вывести число:{}", a)` вывод в консоль, для проверки и получения результата.

 `"Вывести число:"` - в кавычках указывается текст.  
 `"{}", a` - данные в переменой `a`, подставится в `{}`.

 можно использовать несколько  
 `println!("Вывести числа a {} и b {}", a, b)` 

## Комментарии. `// `, `/* */`
Комментарии служит для заметок или описания сложных кусков кода. Часть с комментарием пропускается компилятором.

*.rs*
```rust
// Однострочные
/*
  Много строчные
*/
/// Документация
//! Документация
```
*.toml*
```toml  
# Однострочные
```
> Именно на комментарии новичкам нужно обращать внимание или находить документацию.


# Глава 2
В первой главе мы создали проект. Далее мы будем работать в файле `main.rs`. в папке `src`.

## 1. Переменные `let _name`
```rust
let snake_case = 1; //Переменная с данными
let _snake_case; //Переменная без данных
``` 
Переменные - владеют какими-то данными, которые хранятся в памяти. 
Мы называем переменную ( даем имя ) и присваиваем или создаём данные. Когда мы передаем переменную, мы передаем сами данные.

- `let` - создает переменную
- `name` - это имя переменной, мы сами выбираем имя. (пишутся в нижнем регистре `let snake_case`, если мы не используем намерено то пишем `_` перед переменой `let _snake_case`)
- `=` - оператор присваивания, т.е. это имя будет ровно этим данным. 
- `1` - сами данные которыми владеем переменная.
- `;` - символ завершения оператора.


Разберем на примере:

Возьмём 1000 рублей, которые мы должны сохранить. 
эти данные мы явно запомним... 

1. __Дано: 1000.__

2. Теперь нам нужно *название* для неё.

Что это будет?

Может, это просто данные - *data*,
может что это деньги - *cash*,
название должно быть любым, но интуитивно понятным для другого программиста.
но в любом случае для чего-то сложного можно оставит и комментарий.
```rust
fn main() {
    let cash = 1000; //рублей 
}
``` 
Переменная :
```rust
cash
```
Данные которыми владеет переменная:
```rust
1000
```
Сделаем вывод в консоль
```rust
fn main() {
    let cash = 1000;
    println!("Сохранили {} рублей", cash);  
}
// println!("") макрос для печати 
// println!("{}", cash); подставить данные в текст.
``` 
Теперь можем скомпилировать и запустить
```cargo 
$ cargo run
```

### 1.1. `mut` или способы изменить переменную.
По умолчанию все Rust переменные являются неизменяемыми.
чтобы дать возможность изменять данные в переменой нужен `mut`.
```rust
let mut cash = 1000;
cash = 500;
``` 
>теперь не будет ошибок когда изменим переменную. если тип совпадает

### 1.2. `Затенение` или способы изменить переменную.
Можно объявить переменную с тем же именем которое было использовано раньше и такая новая переменная заменит(затеняет) предыдущую.

```rust
let cash = 1000;
let cash = cash + 500; //1000+500
let cash = 500;//500
``` 
 
## 2. Типы Данных.

Rust является статически типизированным языком. Это означает, что он должен знать типы всех переменных во время компиляции.

Ранее мы записали не указывая тип потому что компилятор сам понимает какой тип данных мы передаем, но иногда компилятору нужно помочь.

Создается переменная и указывается её имя `let _name`, за ним указывается тип данных `:type`,
делее уже происходит присваивание и т.д.

Примеры типов: 
```rust
//Связанные с числами
let _name:i32 = 1; //Целочисленный от -.. до +..
let _name:u32 = 1; //Целочисленный от 0 до ..
let _name:f64 = 1.0; //Числа с плавающей запитой

//Булевые(Логические) значения (Правда/Лож)(1/0)
let _name:bool = true; //Булевые 
let _name:bool = false; //Булевые

//Связанные с символами
let _name:char = "С"; //Посимвольные (один символ)
let _name:String = "Строки"; //Строки 
let _name:&str = "Срезы"; //Срезы

//Сложные/Составные типы (Группы из выше перечисленных типов)
let _name:[i32; 5] = [1, 2, 3, 4, 5]; //Массивы 
let _name:(i32, f64, u8) = (1, 1.0, 1); //Кортежи
let _name:NewType = NewType::new(); //Свой тип созданный с помощью struct или enum
```
---

## 3. Функции `fn name(){..}`.
В первой главе мы уже немного познакомились с функцией `fn main(){..}` - это вход в программу. Компилятор запускает первой функцию `main();`- это значит запускает код внутри фигурных скобках.
```rust
fn main(){
  /*
  Код, который будет запущен.
  */
}
```
Мы можем создать свои функции и поместить в её код, а затем вызвать эту функцию.
```rust
fn main(){
    func();
    //..
}
fn func(){
   /*
  Код, который будет запущен.
  */
}
```
1. компилятор вызывает `main()`
2. `main()` доходит `{` 
3. `main()` вызывает `func();` 
4. `func()`запускает код `{/*Код, который будет запущен.*/}`
5. `//..`
6. `main()` доходит до`}`
7. программа завершается.

### Задачи функции:

### Функция - запускает код, внутри фигурных скобок `{..}`, при вызове функции. 

Вызов функции:
```rust
func();
```
Функция:
```rust
fn func(){
    //ничего не делает
}
```
```rust
fn func(){
    println!("function");//печатает в консоли "function"
}
```
### Функция - Возвращает данные, мы их запишем в переменную.

Вызов функции:
```rust
let foo = func();
```
Функция:
```rust
fn func() ->i32{
    1
}
```
### Функция - Принимает, обрабатывает и возвращает данные.
Вызов функции:
```rust
let foo = func(1);
```
Функция:
```rust
fn func_print(x: i32) ->i32{
    let y = x + 1; //обрабатывает
    y //возвращает
}
```
---
- `fn` - Создает функцию.
- `main` - Это имя функцию, мы сами выбираем имя. (пишутся в нижнем регистре `snake_case`)
- `()` - В скобки мы принимаем, переменные для использования в фигурных скобках`{}`.
- Примеры:
- 1. `()` не принимаем аргументы.
- 2. `(name: i32)` переменные.
- 3. `(&name: i32)` ссылки на переменные.
- 4. `(&mut name: i32)` изменяемые ссылки на переменные.
- `->i32` Тип данных, которые функция возвращает. (`->`и тип данных). Можно не указывать, если функция ничего не возвращает(по умолчанию `->()`).
- `{..}` - Тело функции. 
- 1. `..` - Сам код.
- 2. `{__;}`- этот код запускает, при вызове функции.
- 3. `{x}` - этот код возвращает, данные при вызове функции.
не ставятся `;` - когда функция возвращает данные.

## Глава 3A. Типы. Связанные с числами
### 1. Целочисленный 

>Примеры: .. -3, -2, -1, 0, 1, 2, 3 ..

По умолчанию `:i32`

```rust
let name = 1000;
//------------------
let name:i32 = 1000;
let name = 1000i32;  
let name = 1_000i32; 
// можно записать по разному, на примере i32.
```
Размер	| Знаковый	|Беззнаковый
:--:| :--:| :--:
8-bit	| i8	| u8
16 бит	| i16 |	u16
32 бита |	i32 |	u32
64 бита	| i64	| u64
128 бит |	i128 |	u128
arch |	isize |	usize

`isize` и `usize` зависит от разрядности операционной системы. 

- i8 от -128 до 127.
- i16 от −32 768 до 32 767
- ..
- u8 от 0 до 255.
- u16 от 0 до 65 535
- ..

---
### 2. Числа с плавающей запитой.

>Примеры: 1.0, 1.11, 1.001 

По умолчанию `f64`
```rust
let name = 1000.0;
//--------------------
let name:f64 = 1000.0;
let name = 1000f64;  
let name = 1_000_f64; 
// можно записать по разному, на примере f64.
```
Размер	| Знаковый	
:--:| :--:| 
32-bit	| f32	
64 бит	| f64 
---
## Арифметические Операторы `+`, `-`, `/`, `*`, `%`
- [Все Операторы](https://doc.rust-lang.ru/book/appendix-02-operators.html)

Мы получаем результат действий оператора в переменную `resoult`

```rust
let a = 1;
let b = 2;
let resoult = a + b; //Сложение 
let resoult = a - b; //Вычитание 
let resoult = a / b; //Деление 
let resoult = a * b; //Умножение  
let resoult = a % b; //Остаток от деления 
```
`%` - Остаток от деления, выведет либо 0 или 1. если остаток есть то 1, если нет то 0.

---
## Методы для работы с числами.
Метод - это та же функция, которая уже имеет реализацию для конкретного типа. Другими словами другой программист уже написал весь код за вас, нам только нужно вызвать метод и подставить аргументы которые принимает метод, и получить результат.

Используя методы, мы используем [std](https://doc.rust-lang.org/std/) Стандартную библиотеку Rust.

[i8](https://doc.rust-lang.org/std/primitive.i8.html)
[i16](https://doc.rust-lang.org/std/primitive.i16.html)
[i32](https://doc.rust-lang.org/std/primitive.i32.html)
[i64](https://doc.rust-lang.org/std/primitive.i64.html)
[u8](https://doc.rust-lang.org/std/primitive.u8.html)
[u16](https://doc.rust-lang.org/std/primitive.u16.html)
[u32](https://doc.rust-lang.org/std/primitive.u32.html#method.pow)
[u64](https://doc.rust-lang.org/std/primitive.u64.html)
[f32](https://doc.rust-lang.org/std/primitive.f32.html#method.pow)
[f64](https://doc.rust-lang.org/std/primitive.f64.html)


Пример:
```rust 
//Возведение в степень.
/*(5 в степени 2 ровно 25. т.е. 5*5.)*/

//Пример 1 
let a = 5;
let b = 2;
let resoult = i32::pow(a, b); 
//Пример 2 
let a:i32 = 5;
let b = 2;
let resoult = a.pow(b);
```
Пример 1. 

`i32::pow(a, b);` - это метод `pow()`, для типа `i32`. принимает два аргумента число которое нужно возвести в степень и саму степень. и получаем результат в `resoult`.

Пример 2.

во втором примере мы создаем переменную `a` (объект) и задаем тип `i32`, чтобы компилятор мог сам найти методы типа `i32`.
так как мы позиционируем переменную как изменение объекта, то запись `a.pow(b)`.
изменяем объект `a` методом `.pow(b)`. тот же результат получаем  в `resoult`.

Аналогично для других типов. 

---
Список методов, которые могут пригодится, при работе с числами. 

- Возведение в степень [i32::pow()](https://doc.rust-lang.org/std/primitive.i32.html#method.pow),
[i64::pow()](https://doc.rust-lang.org/std/primitive.i64.html#method.pow), [f32::powf()](https://doc.rust-lang.org/std/primitive.f32.html#method.powf), [f64::powf()](https://doc.rust-lang.org/std/primitive.f64.html#method.powf)

- Квадратный корень [f32::sqrt()](https://doc.rust-lang.org/std/primitive.f32.html#method.sqrt)
[f64::sqrt()](https://doc.rust-lang.org/std/primitive.f64.html#method.sqrt)



---
## `as` или преобразование числовых типов.
Нельзя использовать разные типы - это ошибка. Даже если `i32` и `i64`.

`as`, позволяющее очень легко преобразовывать числовые типы.
```rust
let a:i64 = 1;
let x = a as i32;
```

Выше был пример `/` с целыми числами результат 0. но если нам нужны дробные, мы бы написали так. 
```rust
let a = 1;
let b = 2;
let resoult = a / b; //0
let resoult = a as f64 / b as f64; //0.5
```
>Преобразовывать нужно каждую переменную.

>если нужно преобразование в строку то используйте метод `to_string()`.
---

## Практика с числами.

Создаём новый проект `math_example`, будем работать в файле `main.rs`.

Задание 1: "Создать функцию `sum()` (сумма), для сложения двух чисел `x`, `y`"
```rust
fn main() {
    let x = 19595;
    let y = 25458;
    println!("{}", sum(x, y))
}
fn sum(x:i32, y:i32) ->i32{
    //твой код.
}

//cargo run 
//45053
```

1. Создаем функцию `fn`
- Называем `sum()`
- Создаем аргументы, которые принимает указывая их тип.`x:i32, y:i32`
- Указываем тип который мы хотим получить.`->i32` и `{}` 
2. Думаем над реализацией.
- Сложение - это арифметическое выражение. Оператор `+`
- Математика в школе `x + y`  

```rust
fn sum(x:i32, y:i32) ->i32{
    x + y
}
```
> `;` не нужно.

далее аналогично с вычитанием, умножением делением и т.д. или просто ищем нужный метод `i32::saturating_add(x, y)` или `i32::wrapping_add(x, y)`. разница этих методов появится при переполнения значений.


Задание 2: "Создайте функцию по формуле частоты колебания струны."

TeX
$$
f = {1 \over 2l}{\sqrt{F \over pS}}
$$

![alt text](https://github.com/Prameon/Rust_from_the_start/blob/main/example/math_example/src/date/Tex2Img_1637483265.jpg)

f — частота колебаний (Гц),
l — длина струны (м),
F — сила натяжения струны (Н),
ρ — плотность материала струны (кг/м³),
S — площадь поперечного сечения струны (м²).

```rust
fn main() {
    let frequency = osc_string(0.648, 32.0, 1118.0, 0.001);
    println!("{}", frequency)
}

fn osc_string(
    l:f64,
    f:f64, 
    p:f64, 
    s:f64) ->f64{
    
    (1.0 /(2.0 * l ))*(f64::sqrt(f /(p * s)))
}
```
