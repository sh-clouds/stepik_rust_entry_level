Reverse ↩️

В редакторе кода представлена неполная программа, которую необходимо доделать. Программа должна считать в массив 10 целых чисел и вывести с помощью заполнителя {:?} развернутую коллекцию.

Разворот массива реализуйте в функции reverse() !

Тестовые данные ✅

Sample Input:
-11
75
81
-34
32
-79
29
-68
-114
8

Sample Output:
[8, -114, -68, 29, -79, 32, -34, 81, 75, -11]

Напишите программу. Тестируется через stdin → stdout
Верно решили 50 учащихся
Из всех попыток 88% верных


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
    array = reverse(array);
    println!("{:?}",array);
}

fn reverse(mut array: [i32; 10]) -> [i32; 10] {
    let mut arr1 = [0i32; 10];
    
    for i in (0..array.len())
    {
        arr1[i] = array[array.len()-1-i]        
    }
    arr1   
}