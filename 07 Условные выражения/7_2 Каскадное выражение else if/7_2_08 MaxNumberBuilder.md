MaxNumberBuilder 

Напишите программу, которая считывает трехзначное число, а затем формирует наибольшее число из его цифр и выводит результат.

Тестовые данные ✅

Sample Input:
123

Sample Output:
321

Напишите программу. Тестируется через stdin → stdout
Верно решили 117 учащихся
Из всех попыток 57% верных


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
    let i1: i32 = input();
    let mut a1: i32 = i1 / 100;    
    let mut a2: i32 = (i1 - a1*100) / 10;
    let mut a3: i32 = i1 % 10;
    
    if a1 > a2 { (a1, a2) = (a2, a1) };
    if a2 > a3 { (a2, a3) = (a3, a2) };
    if a1 > a2 { (a1, a2) = (a2, a1) };
    
    println!("{a3:.1}{a2:.1}{a1:.1}");       
}
