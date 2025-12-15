Capacity

Напишите программу, которая считывет строку и выведит её ёмкость и длину в виде сообщения:

capacity = {}
length = {}

                  
Тестовые данные ✅
Sample Input:

Hello, world
Sample Output:

capacity = 13
length = 13
Напишите программу. Тестируется через stdin → stdout
Верно решили 139 учащихся
Из всех попыток 52% верных


fn main() {
    let mut user_input = String::new();
    std::io::stdin().read_line(&mut user_input);    
    println!(
        "capacity = {}\nlength = {}",
        user_input.capacity(),
        user_input.len()
    );
}
