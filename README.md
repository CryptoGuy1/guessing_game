# 🎯 Guessing Game in Rust

This is a simple, fun, and beginner-friendly **command-line guessing game** written in Rust. The program randomly selects a number between **1 and 100**, and your goal is to guess the number correctly. After each guess, the game will give you feedback — whether your guess was too high, too low, or just right.

This project is a great introduction to:
- Rust syntax and project structure
- User input and output
- Random number generation
- Pattern matching and error handling

---

## 📦 About the Project

The guessing game is a classic programming exercise that showcases some of Rust’s core features, such as:

- The `rand` crate for generating random numbers
- Standard input and output using `std::io`
- Handling `Result` and `Option` types with `match`
- Control flow with `loop`, `break`, and `Ordering`

---

## 🧠 What You’ll Learn

By exploring or modifying this project, you will practice:

- Reading input from the user
- Parsing input and handling errors
- Working with variables and mutable state
- Using external crates from [crates.io](https://crates.io)
- Writing clean and idiomatic Rust code

---

## 🛠 Installation and Setup

### 🧰 Prerequisites

Make sure you have [Rust](https://www.rust-lang.org/tools/install) and `cargo` installed:

bash
rustc --version
cargo --version


If not installed, get Rust with:

bash
curl https://sh.rustup.rs -sSf | sh



### 🚀 Running the Game

1. Clone the repository:

bash
git clone https://github.com/your-username/guessing-game.git
cd guessing-game


2. Run the game using Cargo:

bash
cargo run


3. Follow the prompts and try to guess the secret number!

---

## 🧾 Sample Output


Guess the number!
Please input your guess.
> 50
You guessed: 50
Too small!

Please input your guess.
> 75
You guessed: 75
Too big!

Please input your guess.
> 62
You guessed: 62
You win!
```

---

## 📁 Project Structure

```
guessing-game/
├── Cargo.toml         # Dependency configuration
└── src/
    └── main.rs        # Main logic for the guessing game
```

---

## 📜 Source Code (`main.rs`)

```rust
use rand::Rng;
use std::cmp::Ordering;
use std::io;

fn main() {
    println!("Guess the number!");

    let secret_number = rand::thread_rng().gen_range(1..=100);

    loop {
        println!("Please input your guess.");

        let mut guess = String::new();

        io::stdin()
            .read_line(&mut guess)
            .expect("Failed to read line");

        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => continue,
        };

        println!("You guessed: {guess}");

        match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!"),
            Ordering::Greater => println!("Too big!"),
            Ordering::Equal => {
                println!("You win!");
                break;
            }
        }
    }
}
```

---

## ✨ Possible Improvements

Want to level up the game? Try adding:

- 🧮 Attempt counter to track number of guesses
- 🧠 Difficulty levels (easy: 1–50, hard: 1–500)
- ⏱ Time limit or countdown timer
- 💡 Hints after a certain number of failed attempts
- 📊 Leaderboard or scoring system

---

## 🧪 Tests

No formal tests included, but you can practice:
- Writing unit tests to check input parsing
- Mocking random values for deterministic testing

---

## 🙌 Acknowledgements

This game is inspired by the official [Rust Book](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html), Chapter 2 tutorial. It’s a great resource for learning Rust from scratch!

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 💬 Feedback

Feel free to [open an issue](https://github.com/your-username/guessing-game/issues) or fork the repo and improve it.  
Pull requests are welcome!

---

Happy coding! 🦀  
*“Build fun, build fast, build in Rust!”*
```

---

Would you like a `LICENSE` file or a `.gitignore` file to go with it? I can generate those too.
