
## Installation

Install ollama

```
curl https://ollama.ai/install.sh | sh
```

Download the llama2 model

```
ollama run llama2
```

## Let's do the FizzBuzz coding challenge!

```
>>> give me the fizzbuzz in rust
Certainly! Here is the "FizzBuzz" program in Rust:
```

```
fn main() {
    for i in 1..=100 {
        println!("{}", if i % 3 == 0 {"Fizz"} else {"Buzz"});
    }
}
```
Explanation:
...

The result was not quite a correct solution. Let's fine tune it

```
>>> not quite! you write "fizz" for numbers that can be divided by 3, then "buzz" if the number can be divided by 5, otherwise the
...  number itself
Ah, I see! Thank you for correcting me. Here's the updated Rust code for "FizzBuzz":
```

```
fn main() {
    for i in 1..=100 {
        println!("{}", if i % 3 == 0 {"Fizz"} else if i % 5 == 0 {"Buzz"} else {i});
    }
}
```

Almost correct, a little fix is still required

```
>>> one more thing: if the number can be divided by both 3 and 5, then print fizzbuzz
Ah, I see! Here's the updated code for "FizzBuzz" in Rust:
```

```
fn main() {
    for i in 1..=100 {
        println!("{}", if i % 3 == 0 && i % 5 == 0 {"FizzBuzz"} else if i % 3 == 0 {"Fizz"} else if i % 5 == 0 {"Buzz"} else
{i});
    }
}
```

## Install the open webui

The webui allows you to access the AI from a browser

```
docker run -d --network=host -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
    -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

Then we can visit http://<hostname>:8080/
