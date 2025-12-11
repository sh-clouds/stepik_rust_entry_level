a AND b

Напишите программу, которая считывает два целых числа a (i8) и b (i8) и выводит для них операцию побитового И в виде сообщений. Так, если a = 5, а b = 2, то вывод будет выглядеть следующим образом:

00000101 :a
00000010 :b
00000000 :a & b
Тестовые данные ✅

Sample Input:
-86
2

Sample Output:
10101010 :a
00000010 :b
00000010 :a & b

Напишите программу. Тестируется через stdin → stdout
Верно решили 96 учащихся
Из всех попыток 68% верных


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
    let mut a: i8 = input();
    let mut b: i8 = input();
 
    println!("{:08b} :a", a);
    println!("{:08b} :b", b); 
    println!("{:08b} :a & b", a&b);    
}
