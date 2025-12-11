Last Digit 2x

Напишите программу, которая считывает показатель степени (целое положительное число) числа 2 и выводит его последнюю цифру без возведения, как показано в примерах.

Так, если была считана 1, программа должна вывести: Последняя цифра 2 в степени 1 равна 2, поскольку 
2**1 равно 2. Если была считана 2, то программа должна вывести: Последняя цифра 2 в степени 2 равна 4, поскольку 2**2 равно 4. И т.д.

Тестовые данные ✅

Sample Input:
1

Sample Output:
Последняя цифра 2 в степени 1 равна 2

Напишите программу. Тестируется через stdin → stdout
Верно решили 85 учащихся
Из всех попыток 69% верных

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
    let i: i32 = input(); 
    let mut j = i;
    j = j % 4;
  
    if j == 1      { println!("Последняя цифра 2 в степени {i} равна 2"); } 
    else if j == 2 { println!("Последняя цифра 2 в степени {i} равна 4"); }   
    else if j == 3 { println!("Последняя цифра 2 в степени {i} равна 8"); }       
    else           { println!("Последняя цифра 2 в степени {i} равна 6"); }      
}


