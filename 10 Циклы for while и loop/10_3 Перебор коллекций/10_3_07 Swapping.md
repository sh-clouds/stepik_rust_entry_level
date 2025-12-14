Swapping

Напишите программу, которая считывает индекс (usize) и десять целых значений, меняет местами по считанному индексу предыдущий и следующие элементы, а затем выводит получившийся массив с помощью спецификатора :?.

Гарантируется, что 0 < индекс < 9.

Тестовые данные ✅

Sample Input:
1
1
2 
3
4
5
6
7
8
9
10

Sample Output:
[3, 2, 1, 4, 5, 6, 7, 8, 9, 10]

Напишите программу. Тестируется через stdin → stdout
Верно решили 69 учащихся
Из всех попыток 72% верных


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
    let mut n: usize = input(); 
    let mut array = [0; 10];
    let mut temp: i32;  
    
    for item in 0..=9 {
        array[item] = input();
    }
    
    temp = array[n - 1];
    array[n - 1] = array[n + 1];
    array[n + 1] = temp;
    println!("{:?}",array);
}


