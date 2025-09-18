# Ex.No:3 Create an application of Guessing a number using common programming constructs of Rust.

## AIM:
To build a simple interactive Rust program that lets a user guess a randomly chosen number while demonstrating variables, loops, conditionals, functions, pattern matching and basic error handling..

## ALGORITHM :
1. Start the program.  
2. Import the required libraries:  
   - `std::cmp::Ordering` for comparison results (`Less`, `Greater`, `Equal`).  
   - `std::io` for user input.  
3. Define the `main` function.  
4. Print the message: *"I'm thinking of a number between 1 and 100..."*.  
5. Assign the secret number as **90**.  
6. Start an infinite loop (`loop`).  
   1. Prompt the user to enter a guess.  
   2. Read the input as a string.  
   3. Convert the input into an integer (`u32`):  
      - If conversion fails, show an error message and continue the loop.  
   4. Print the guessed number.  
   5. Compare the guess with the secret number using `cmp`:  
      - If guess < secret → print *"Too low!"*.  
      - If guess > secret → print *"Too high!"*.  
      - If guess == secret → print *"WELL! You guessed it right"*, and break the loop.  
7. End the program.  




## PROGRAM:

 ```
///
Developed by: Gokularamanan K
RegisterNumber: 212222230040
///

use std::cmp::Ordering;
use std::io;

fn main() {
    println!("I'm thinking of a number between 1 and 100...");

    let secret_number = 90;

    loop {
        println!("Please input your guess:");

        let mut guess = String::new();

        io::stdin()
            .read_line(&mut guess)
            .expect("Failed to read line");

        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => {
                println!(" Please enter a valid number.");
                continue;
            }
        };

        println!(" You guessed: {guess}");

        match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too low!"),
            Ordering::Greater => println!(" Too high!"),
            Ordering::Equal => {
                println!(" WELL! You guessed it right: {}", secret_number);
                break;
            }
        }
    }
}
```

## OUTPUT:

<img width="565" height="463" alt="image" src="https://github.com/user-attachments/assets/8275e472-f76a-4b20-92e3-7a09c749278e" />





## RESULT:
Thus, Program for Guessing a number using common programming constructs of Rust was executed successfully.

