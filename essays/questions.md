---
layout: essay
type: essay
title: Ask in Earnest
# All dates must be YYYY-MM-DD format!
date: 2020-01-27
labels:
  - languages
  - Rust
---

## Asking Smart Questions  

Learning a programming language is not easy. Not everything is well documented. Sometimes the language authors will include funky designs that reference old paradigms that no 20-something should ever be expected to know. Enter, [Stack Overflow](https://stackoverflow.com/). Even the name of the website is an 'in' joke. Many higher language programmers never have to think in terms of the stack at all. To make matters worse, (while it's gotten better) a lot of the people answering these questions have a high horse attitude and moderators can be quite heavy handed in removing questions.  

In order to combat the potentially downward spiral of bad questions breeding bad answers, Eric Raymond and Rick Moen wrote a pretty insightful article, ["How To Ask Questions The Smart Way](http://www.catb.org/esr/faqs/smart-questions.html). Even ignoring the actual content of the article, simply reading the headers of each section is enough to glean the right way to ask a question in a shark tank.   

## Getting 'Smart' Answers  

Before looking at good questions, I'll first exam a few ones that miss the mark. Rust is a relatively new programming language, with an a fanbase loyal enough that memes are made about people who program using it (I use Rust btw). The title of the post the is this: [why i'm getting this error in rust? while running cargo in terminal](https://stackoverflow.com/questions/59102067/why-im-getting-this-error-in-rust-while-running-cargo-in-terminal). Without even going into the body of the question, the title already breaks two rules from the smart questions article. The subject header is not specific, there are very few questions that don't involve some sort of error. Besides that, it's ungrammatical.  

As for the body of the post, the only thing there is the console log of the error. No further explanation. No code.  

Suffice it to say, this post generated some 'smart' answers.  

> Welcome to StackOverflow @AbhiSingh, please read the guide on how to ask good question and edit your with required details. – stud3nt Nov 29 '19 at 9:34  

Thank you stud3nt. In stud3nt's defense, the word 'quide' is a hyperlink to stack overflow's "how to as good questions" page.  

> Please do some searching around next time before you ask a new question. I'm pretty sure this is a common starting problem on Windows (having come across it myself) - Phi12ip  

This user answered the question a bit more helpfully, at least. 

## Making a Difficult Language a bit Easier  

It is not possible to fully avoid getting rude answers. The most perfectly crafted question, fully unanswerable by even the best developers, might still garner some scorn from certain users. That said, a good question begs to be answered. This question from Angel Angel holds the title: [How do you pass a Rust function as a parameter](https://stackoverflow.com/questions/36390665/how-do-you-pass-a-rust-function-as-a-parameter).  

The title is clear and succint. Granted, it's a relatively easy question to answer. But perhaps it is only easy to answer because it is phrased well. Following the good question, the user continues with an example of what they've tried.  

```Rust 
fn example() {
    let fun: fn(value: i32) -> i32;
    fun = fun_test;
    fun(5i32);
}

fn fun_test(value: i32) -> i32 {
    println!("{}", value);
    value
}
```

Then, the user goes above and beyond by giving a visual example of what they *want* to do:  

```Rust  
fn fun_test(value: i32, (some_function_prototype)) -> i32 {
    println!("{}", value);
    value
}
```  
`(some_function_prototype)` explains what they want to do very clearly. To this, we finally see a good answer.  

```Rust
fn fun_test(value: i32, f: &dyn Fn(i32) -> i32) -> i32 {
    println!("{}", f(value));
    value
}

fn times2(value: i32) -> i32 {
    2 * value
}

fn main() {
    fun_test(5, &times2);
}
```

User rodrigo provides a clear answer and goes way above and beyond what the question asked later in their post. For reference, this portion of the code `-> i32`, specifies a return type of a signed 32 bit integer. Following that, the random `value` sitting at the end of the function is not an error. The last line of a function with a return type is implicitly believed to be the return value and needs no `;`.  
