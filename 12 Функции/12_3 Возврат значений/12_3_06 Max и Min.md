Max и Min ↘️

В редакторе кода представлена неполная программа, которую необходимо доделать. Программа должна считать в массив 10 целых чисел и вывести максимальное и минимальное значения в виде сообщений:

max:{}
min:{}

                  
Нахождение максимального элемента реализуйте в функции max(), а минимального в min()!

Тестовые данные ✅

Sample Input:
-9
-92
96
-5
-77
-5
124
34
-122
45

Sample Output:
max:124
min:-122

Напишите программу. Тестируется через stdin → stdout
Верно решили 47 учащихся
Из всех попыток 85% верных


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
    let mut array = [0i32; 10];
    
    for i in 0..(array.len())
    {
        array[i] = input::<i32>();
    } 
    
    let mut max_val = max(array);
    let mut min_val = min(array);    
    println!("max:{}", max_val);
    println!("min:{}", min_val);    
}

fn max(array: [i32; 10]) -> i32 {
    let mut val: i32 = array[0];
    for i in (1..array.len())
    {
        if val < array[i]
        {
            val = array[i]
        }     
    }
    val  
}

fn min(array: [i32; 10]) -> i32 {
    let mut val: i32 = array[0];
    for i in (1..array.len())
    { 
        if val > array[i]
        {
            val = array[i]
        }
    }
    val  
}

