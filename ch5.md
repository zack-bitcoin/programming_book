Leaning on the Computer
==============

There is this idea that the world is heading towards an artificial intelligence revolution. That someday soon computers will have AI sufficiently advanced to build a better AI, and become more intelligent than humans in every way.

I am not sure if the AI revolution will happen. But it does seem to be the case that computers are already better at doing the majority of programming tasks.

One of the most important things you can do to increase your efficiency as a programmer, is to do less. If the computer is better at a task than you, then you should stop doing that task, and let the computer do it for you.

Instead of reading some code looking to find a certain word, you should use your editer to search and find it.

If you find yourself typing the same keys in a cycle, you should make a macro to edit the code automatically.

There are many kinds of errors that can be caught by the compiler, so you don't need to worry about catching them manually. Like, spelling errors, or forgetting to pass one of the variables to a function. Or maintaining a certain style that makes the code easier to reason about.

There are many kinds of errors that can be found at runtime, by running tests. So you don't need to personally imagine the entire space of possibilities.

Feature Maintenance AI
============

Instead of directly writing software to solve the task, you should write an AI library for solving this class of tasks. You do this by making your code in the form of pure functions as much as possible, because pure functions can be reasoned about, and the entire space of features we are interested in can be tested. In parallel with the code, you write tests.

If you have an idea about a new feature you want to add, you can ask the AI if your idea could work. You run the tests, and see which line of the test fails. In this way, the AI not only tells you that your idea doesn't work, the AI is telling you exactly why your idea is incompatible with existing code, so you know what would need to be changed to allow your new idea to work.

The job of the human is to make suggestions about new features, and the job of the computer is to explain what changes we would need to make to enable those new features, while maintaining existing features.

Making tests for a set of features for pure functions, this is easy for humans.
Suggesting new features is easy for humans.
Using pure functions to implement the well-defined changes that the computer explains, this is easy for humans.

Understanding an entire program, and what needs to be changed to enable a new feature, this is very hard for humans, but the computer can do it almost instantly.

Some people call this "test driven development"

Feature testing AI
============

Holding certain large systems in your head is impossible. You can't understand the big picture well enough to know how the parts will interact.

So instead of trying to build the whole system at once, you build the pieces, and connections between them that you do understand.

So now, you have bigger puzzle pieces to try to fit together. The set of possible ways to combine the pieces shrinks and becomes easier to reason about, as we keep connecting the parts of the puzzle.

It is like you are building a language optimized for solving kinds of problems related to the specific problem you are interested in. You are building tools optimized to solve the kind of problem you want to solve.

In this way, you don't ever have the impossible task of understanding the entire system at once. You leave that to the AI. Instead, you only look at how pairs of individual components interact together.

I have heard this called bottom-to-top programming before.

AI in the compiler for immutable variables
=========

In order to reason about the code you have written, it is helpful if when you look at a variable, you can quickly know what it's value is.

If you mutate your variable, then the programmer needs to scan a lot of lines to know what a variable is. They need to check if it was re-defined at any other line, and they need to look up the definitions of all the functions where this variable was passed as an input to that function.

AI in the compiler for enforcing dynamic vs lexical binding
==================

When it comes to languages with mutable variables, some are worse than others.
Dynamic variable binding is very bad, and you should use lexical when possible.

using lisp for the example
```
(let ((a 1)
      (g (lambda ()
           (let ((a 2))
             (+ a 1))))
      (f (lambda () a)))
 (g)
 (f))  
```

in a dynamic variable binding language, this returns 2, and in a lexical language, it returns a 1.

Dynamic languages should be avoided, because every time you want to use a function, you need to consider the entire list of variable names used in that function, and double-check that none of those variables will interfere with the namespace of the place where you want to use this function.

To write code in a language with dynamic variable binding, you need to remember a big list of words for every function, and this is something that people are bad at.

If you need to work in a language with dynamic variables binding, then you need to make your modules very small to keep the lists of words you have to memorize from getting too long.

Namespace
===========

You want your namespace to be small at every point in the code.
It is hard for humans to memorize too many words. 
Sometimes the code could be clearer to read if you re-use the same word you had used for something else in your code.

It is important that a person editing your code doesn't need to memorize some long list of words that they aren't allowed to use.

When reusing a word causes software to crash, it is very difficult to understand what went wrong. A function changes definition at an unexpected moment, very far from where you are currently editing.

So it is important to organize your code into some kind of system of modules, to protect namespace.

[chapter 6](/ch6.md)
