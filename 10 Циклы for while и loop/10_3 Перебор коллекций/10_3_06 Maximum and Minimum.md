Maximum and Minimum

Напишите программу, которая считывает натуральное значение n (u8) и столько же вводимых пользователем целых чисел. Программа должна вывести среди них максимальный и минимальный элемент в виде сообщений: Максимальное число: {} и Минимальное число: {}.

Тестовые данные ✅
 
Sample Input:
10
-1
-2
-3
-4
-5
-6
-7
-8
-9
-10

Sample Output:

Максимальное число: -1
Минимальное число: -10
Напишите программу. Тестируется через stdin → stdout

Верно решили 73 учащихся
Из всех попыток 65% верных


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
    let mut n: u8 = input();        
    let mut val: i32;
    let mut val_max: i32;    
    let mut val_min: i32;  
    
    val = input();  
    val_min = val;      
    val_max = val;     
    
    for i in 1..n {
        val = input();
        if val_min > val
        {
            val_min = val;
        }
        else if val_max < val
        {
            val_max = val;
        }                   
    }  
    println!("Максимальное число: {val_max}"); 
    println!("Минимальное число: {val_min}");     
}





