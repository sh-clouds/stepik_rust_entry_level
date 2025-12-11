MinNumberBuilder

Напишите программу, которая считывает трехзначное число, а затем формирует наименьшее трехзначное число из его цифр и выводит результат.

Тестовые данные ✅

Sample Input:
130

Sample Output:
103

Напишите программу. Тестируется через stdin → stdout
Верно решил 101 учащийся
Из всех попыток 48% верных


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
    if a1 == 0 && a2 == 0 { (a1, a3) = (a3, a1) }
    else if a1 == 0 { (a1, a2) = (a2, a1) }
    
    println!("{a1:.1}{a2:.1}{a3:.1}");       
}




