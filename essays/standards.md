---
layout: essay
type: essay
title: Programming is Hard Enough
# All dates must be YYYY-MM-DD format!
date: 2021-02-11
labels:
  - Learning
  - Coding Standards
---

While a programming language is not the same thing as a natural language, there are many parallels that can be drawn between the two. Both are used to communicate a message, both have easy and hard ways to describe one thing and both have a large community of people who believe their way of articulation to be the best. When higher level programming languages first came about there was a bit of a wild west time period for standardization of code. Some inspired individuals even went as far as writing a programming language that only works with (whitespace)[https://en.wikipedia.org/wiki/Whitespace_%28programming_language%29].  

Over time, people realized that just because the compiler was okay with the program did not mean that colleagues were okay with it. Soon enough, a revolution began with many small parties creating their own rules for writing programs.  

```
my_function() {
    return 1;
}

other_function() 
{
    return 2;
}
```

Many arguments were had over whether the opening brace '{' should be on the same line as the function, or the next one. Many more arguments were spent on whether indentation should be 2 spaces or 4 (or 3). Besides pedantic arguments, there were some that actually made sense.  

```
function1(myVariable) {
    return myVariable;
}

function2(MyVariable) {
    return MyVariable;
}

function3(my_variable) {
    return my_variable;
}
```

these 3 functions all bring in a variable, however just looking at this code isn't enough to tell really anything about the functions (besides that they are simply identity functions). However, taking a closer look at the 'myvariable' here some things might become apparent. the first function brings in 'myVariable' and uses camelCase. The second uses PascalCase and the third uses snake_case. In the normal wild west, this might not make any difference. However, let's say I was to enforce some coding standards on this code. From here on out, camel case is for literal variables, pascal case is for objects and snake case is for functions.  

Suddenly, we are able to glean a lot more information from this small code snippet than before. Better yet, if I standarized those conventions, I could write code for my IDE that was able to identify errors based on naming.  

## Don't Make a Hard Problem Harder  

In the book ("Thinking, Fast and Slow")[https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow] by Daniel Kahneman, the idea of 'system 1' and 'system 2' get introduced. System 1 is the reflex system of the brain that responds quickly and system 2 is the logical part of the brain (extremely simplified). Kahneman found that this system 2 of ours is incredibly finicky. It gets tired easily and tries hard to get out of work. Unfortunately for programmers, software development exists almost entirely in that system 2 space.  

I can recall some fond memories of mine, starting a programming project a few hours before it is due. I remember getting the project done, and then when I realize I need my code again for another project, my mind starts to blank. The code I wrote not long ago now looks completely foreign to me.  

Now that I've matured a bit in my practices, I no longer have those types of woes. I write programs in a similar fashion and follow similar patterns. In short, I appreciate the work that others have done to develop programming standards and I hope to pass the baton along in the future.  
