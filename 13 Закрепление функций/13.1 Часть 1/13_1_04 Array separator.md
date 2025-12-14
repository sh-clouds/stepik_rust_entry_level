Array separator

В редакторе кода представлена неполная программа, которую необходимо доделать. Программа должна считать строчное значение sep и 10 вещественных чисел в массив и вывести (до 2 знаков) получившуюся коллекцию, элементы которой разделены строкой sep.

Вывод реализуйте в функции print_sep_arr() ! Поскольку метод trim() удаляет из строки и пробелы, а тему строк ещё не прошли, в редакторе приведен метод replace() удаляющий только символ новой строки \n.

Помните, что в Windows строка завершается символами \n\r.

Тестовые данные ✅

Sample Input:
, 
9.30
9.52
1.22
6.18
1.67
9.66
6.07
2.21
1.35
6.60

Sample Output:
9.30, 9.52, 1.22, 6.18, 1.67, 9.66, 6.07, 2.21, 1.35, 6.60

Напишите программу. Тестируется через stdin → stdout
Верно решили 78 учащихся
Из всех попыток 53% верных

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
    let mut input_b = String::new();
    std::io::stdin().read_line(&mut input_b).expect("Failed to read line");    
    let sep: String = input_b.parse().expect("Please enter a valid string");
  
    let mut arr = [0.00_f64; 10];

    for i in 0..10  
    {       
        arr[i] = input();
    }  
    print_sep_arr(arr, sep);
}

fn print_sep_arr(mut arr: [f64; 10], mut sep: String) {
    sep = sep.replace("\n", "");
    for i in 0..9  
    {   
        print!("{:.2}", arr[i]);
        print!("{sep}");
    }    
    println!("{:.2}", arr[9]);
}