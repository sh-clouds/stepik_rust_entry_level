Element Separators

Напишите программу, которая считывает два целых числа start и end и выводит числа диапазона start..=end разделяя их символом |.

Так, для диапазона 1..=5 выводом будет:1 | 2 | 3 | 4 | 5.

Тестовые данные ✅

Sample Input 1:
1
5

Sample Output 1:
1 | 2 | 3 | 4 | 5


Sample Input 2:
-5
0

Sample Output 2:
-5 | -4 | -3 | -2 | -1 | 0


Напишите программу. Тестируется через stdin → stdout
Верно решили 73 учащихся
Из всех попыток 71% верных


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
    let mut start: i32 = input(); 
    let mut end: i32 = input();     

    for i in start..=end { 
        if i == start {print!("{i} |");}
        else if i == end {print!(" {i}");}
        else {print!(" {i} |");}       
    }
}


