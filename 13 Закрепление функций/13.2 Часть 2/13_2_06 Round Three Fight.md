Round Three Fight

Напишите программу, которая считывает вещественное число и выводит для него ближайшее целое число (i64).

Функцию round() реализовать вручную!

Тестовые данные ✅

Sample Input 1:
5.5

Sample Output 1:
6


Sample Input 2:
30.498

Sample Output 2:
30

Напишите программу. Тестируется через stdin → stdout
Верно решили 77 учащихся
Из всех попыток 60% верных


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
    let mut n: f64 = input();         
    println!("{}", round(n));       
}

fn round(n: f64)-> i64 {
     n.round() as i64    
}

