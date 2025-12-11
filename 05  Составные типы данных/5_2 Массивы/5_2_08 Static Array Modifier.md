Static Array Modifier

Напишите программу, которая считывает два целых числа. Далее инициализирует массив нулей размерностью десять и заменяет элемент в массиве по указанному индексу (первое число) на значение второго числа. После этого программа выводит получившийся массив. Гарантируется, что первое число не превышает длину массива!

Тестовые данные ✅

Sample Input:
0
-10

Sample Output:
[-10, 0, 0, 0, 0, 0, 0, 0, 0, 0]

Напишите программу. Тестируется через stdin → stdout
Верно решили 235 учащихся
Из всех попыток 76% верных


use std::io;
use std::str::FromStr;
use std::fmt::Debug;
fn read_number<T: FromStr>() -> T where <T as FromStr>::Err: Debug {
    let mut user_input = String::new();
    io::stdin().read_line(&mut user_input).expect("Не удалось прочитать ввод");
    user_input.trim().parse().expect("Не удалось преобразовать в число")
}

fn main() {
    let i1: i32 = read_number();
    let i2: i32 = read_number(); 
    let mut arr = [0; 10];
    arr[i1 as usize] = i2;
    println!("{:?}", arr); 
}