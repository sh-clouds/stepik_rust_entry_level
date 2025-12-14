Rustacean 🦀

Напишите программу, которая считывает целое число n и выводит с новой строки сообщение: Rustacean 🦀 n раз.

Тестовые данные ✅

Sample Input:
1

Sample Output:
Rustacean 🦀

Напишите программу. Тестируется через stdin → stdout
Верно решили 116 учащихся
Из всех попыток 80% верных


use std::io;
use std::str::FromStr;

fn input<T: FromStr>() -> T 
where
    T::Err: std::fmt::Debug,
{
    let mut input = String::new();
    std::io::stdin()
        .read_line(&mut input)
        .expect("Failed to read input");
    input.trim().parse::<T>().expect("Failed to parse input")
}

fn main() {       
    let mut n: u8 = input(); 
    
    for i in 0..n {
        println!("Rustacean 🦀");
    }      
}

