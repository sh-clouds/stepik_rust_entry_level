Numeric Array Inspector 🔍

Напишите программу, которая считывает 5 целых чисел, записывает их в массив и выводит элементы коллекции по индексу считанных чисел, как показано в примере. Гарантируется, что числа не отрицательны и не превышают длины массива!

Тестовые данные ✅
Sample Input:
0
1
2
1
0

Sample Output:
0, 1, 2, 1, 0

Напишите программу. Тестируется через stdin → stdout
Верно решили 233 учащихся
Из всех попыток 42% верных


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
    let i3: i32 = read_number();   
    let i4: i32 = read_number();    
    let i5: i32 = read_number();       
    let mut arr = [i1, i2, i3, i4, i5];
    println!("{}, {}, {}, {}, {}", arr[i1 as usize], arr[i2 as usize], arr[i3 as usize], arr[i4 as usize], arr[i5 as usize]); 
}
