Last Digit 9x + 4y

Напишите программу, которая считывает натуральные показатели степени (u32) чисел 9 и 4, и выводит последнюю цифру суммы 9x + 4y без возведения, как показано в примерах.

Так, если была считана 1 и 1, программа должна вывести: Последняя цифра суммы равна 3, поскольку 
9**1+4**1 равно 13. Если была считана 1 и 2, то программа должна вывести: Последняя цифра суммы равна 5, поскольку 
9**1+4**2 равно 25. И т.д.

Тестовые данные ✅

Sample Input:
1
1

Sample Output:
Последняя цифра суммы равна 3

Напишите программу. Тестируется через stdin → stdout
Верно решил 81 учащийся
Из всех попыток 46% верных


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
    let i1: u32 = input(); 
    let i2: u32 = input();     
    let mut j = i2;
    j = j % 4;
    let mut k1: u32;
    let mut k2: u32;
    
    if i1 % 2 == 0 { k1 = 1; }
    else { k1 = 9; }
    
    if i2 % 2 == 0 { k2 = 6; }
    else { k2 = 4; }
     
    println!("Последняя цифра суммы равна {}", (k1+k2) % 10);   
}