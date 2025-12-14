Deleter

Напишите программу, которая считывает два натуральных (u32) числа n и k соответственно, а затем выводит число, полученное удалением первых k цифр из числа n. Если количество удаляемых цифр нестрого больше, чем количество цифр в n, то выводится сообщение k >= n.

Тестовые данные ✅

Sample Input:
123456
3

Sample Output:
456

Напишите программу. Тестируется через stdin → stdout
Верно решили 49 учащихся
Из всех попыток 59% верных



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
    let n: u32 = input();
    let k: u32 = input();
    let s1 = n.to_string();   
    
    if k >= s1.len() as u32
    {
        println!("k >= n");
    }
    else
    {
        let n1: usize = k as usize;
        let s2 = &s1[n1..];         
        println!("{s2}");    
    }
}


