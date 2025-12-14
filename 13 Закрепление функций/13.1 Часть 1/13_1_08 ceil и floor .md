ceil и floor

В редакторе кода представлена неполная программа, которую необходимо доделать. Программа должна считывать вещественное число и выводить его округления до ближайшего наибольшего и наименьшего целого числа.

Округления до ближайшего наибольшего и наименьшего целого числа реализуйте в соответствующих функциях ceil() и floor()!

Тестовые данные ✅

Sample Input:
1.1

Sample Output:
2
1

Напишите программу. Тестируется через stdin → stdout
Верно решили 73 учащихся
Из всех попыток 59% верных.


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
    let mut num: f64 = input(); 
    let mut icell: i64 = 0; 
    let mut ifloor: i64 = 0;
        
    icell = ceil(num);
    ifloor = floor(num);
    println!("{icell}");
    println!("{ifloor}");
}

fn ceil(num: f64) -> i64 {
    num.ceil() as i64
}

fn floor(num: f64) -> i64 {
    num.floor() as i64
}