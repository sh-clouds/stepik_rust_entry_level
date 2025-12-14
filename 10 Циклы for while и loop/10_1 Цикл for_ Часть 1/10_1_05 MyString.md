MyString

Напишите программу, которая считывает строку, целое число n и выводит считанную строку n раз, как показано в примерах.

Тестовые данные ✅
Sample Input:

Hello, world!
5

Sample Output:
Hello, world!
Hello, world!
Hello, world!
Hello, world!
Hello, world!

Напишите программу. Тестируется через stdin → stdout
Верно решили 113 учащихся
Из всех попыток 67% верных



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
    let mut s: String = input();
    let mut n: u8 = input(); 
    
    for i in 0..n {
        println!("{s}");
    }      
}

