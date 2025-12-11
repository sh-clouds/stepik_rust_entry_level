MinMaxIndex

В редакторе кода представлен массив значений. Дополните код и считайте два индекса (usize), а затем выведите, являются ли считанные индексы индексами минимального или максимального элемента в массиве соответственно, как показано в примерах.

Тестовые данные ✅

Sample Input:
3
5

Sample Output:
Считанный мин.индекс корректный
Считанный макс.индекс корректный

Напишите программу. Тестируется через stdin → stdout
Верно решил 101 учащийся
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
    let array = [3, 1, 0, -5, -1, 300, 4, 2];
    let i1: usize = input(); 
    let i2: usize = input();     

    if array[i1] == *array.iter().min().unwrap()
    {
        println!("Считанный мин.индекс корректный");            
    }
    else
    {
        println!("Считанный мин.индекс некорректный");             
    }            
 
    if array[i2] == *array.iter().max().unwrap()
    {
        println!("Считанный макс.индекс корректный");             
    }
    else
    {
        println!("Считанный макс.индекс некорректный");             
    }  
}


