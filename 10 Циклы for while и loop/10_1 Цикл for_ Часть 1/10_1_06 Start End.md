Start End

Напишите программу, которая считывает строку, два целых числа start и end, а затем выводит считанную строку с диапазоном start..end.

Тестовые данные ✅

Sample Input:
Я люблю учиться!
0
10

Sample Output:
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!
Я люблю учиться!

Напишите программу. Тестируется через stdin → stdout
Верно решили 100 учащихся
Из всех попыток 76% верных



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
    let mut start: u8 = input();  
    let mut end: u8 = input(); 
    
    for i in start..end {
        println!("{s}");
    }      
}
