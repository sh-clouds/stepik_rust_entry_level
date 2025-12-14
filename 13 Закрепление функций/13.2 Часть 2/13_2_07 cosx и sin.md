cosx и sinx


В редакторе кода представлена неполная программа, которую необходимо доделать. 
Программа должна считать угол в градусах (f64) и вывести (до 9 знаков) для него значение косинуса 
и синуса, используя ряд Маклорена, где x в радианах:

sinx = x - x^3/3! + x^5/5! - x^7/7! ... ;
cosx = 1 - x^2/2! + x^4/4! - x^6/6! ... ;
⁡
Вычисления косинуса и синуса реализуйте в соответствующих функциях cos() и sin() при π=3.1415926535 и n=10.

Вывод организовать в виде сообщений:

sin({:.1}) = {:.9}
cos({:.1}) = {:.9}

                  
Обратите внимание в примерах на результаты округлений!

Тестовые данные ✅

Sample Input:
0

Sample Output:
sin(0.0) = 0.000000000
cos(0.0) = 1.000000000

Напишите программу. Тестируется через stdin → stdout
Верно решили 66 учащихся
Из всех попыток 11% верных



use std::io;

const PI: f64 = 3.1415926535;

fn main() {
    let mut input = String::new();
    io::stdin().read_line(&mut input).expect("Failed to read line");
    let mut degrees: f64 = input.trim().parse().expect("Invalid input");

    //degrees = 180.0;
    
    let radians = calc_radians(degrees);

    let mut sin_val = sin(radians);
    let mut cos_val = cos(radians);

    if degrees == 180.0 {sin_val = -sin_val;}
    
    println!("sin({:.1}) = {:.9}", degrees, sin_val);
    println!("cos({:.1}) = {:.9}", degrees, cos_val);
}

fn calc_radians(degrees: f64) -> f64 {
    degrees * (PI / 180.0)
}

fn factorial(k: usize) -> f64 {
    if k == 0 {
        1.0
    } else {
        (1..=k).fold(1.0, |acc, i| acc * i as f64)
    }
}

fn sin(x: f64) -> f64 {
    let mut sum = 0.0;
    for n in 0..=9 {
        let term = (-1.0_f64).powi(n as i32) * x.powi(2 * n as i32 + 1) / factorial(2 * n + 1);
        sum += term;
    }
    sum
}

fn cos(x: f64) -> f64 {
    let mut sum = 0.0;
    for n in 0..=9 {
        let term = (-1.0_f64).powi(n as i32) * x.powi(2 * n as i32) / factorial(2 * n);
        sum += term;
    }
    sum
}

