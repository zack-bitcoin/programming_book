Development Cycle
===========

The development cycle is like this:

* you make a change to the code.
* you test that change.
* you comprehend the results of that test.

The biggest factor in how quickly I can program is in how quickly I can complete cycles.

If my cycle length is 2x longer, like 20 seconds instead of 10 seconds, you might think that this means it would take me 2x longer to write the code. But it is much more severe. If the cycle length is 2x longer, it seems to take around 4x longer to write the same code.

The problem is that as the cycle gets longer, it becomes more difficult to remember all the factors involved in the part of the code I am writing. I lose focus more frequently. So I need to use 2x more cycles to accomplish the same tasks. 2x longer for each cycle, and 2x as many cycles, means in total it takes 4x longer to finish.

So if you can reduce your cycle length from 60 seconds down to 10 seconds, you should be able to finish the same project in 1/36th as much time. You can finish a month of work in a day.

You need a lot of oxygen when you are doing heavy thinking. Having a fast cycle length also helps because it reminds you to breath. You can have your breathing in sync with your cycle length. One breath per cycle.

To have fast cycles, you need to depend on the computer to do all the things that humans are bad at. You need to have an instinctive control over your editor, so you don't waste any time trying to remember how to use your editor.

To have fast cycles, you need the tests to run quickly. It is important that your tests have as few sleep statements as possible, ideally none. If your tests are still too slow, you can organize them, so you are only testing the part of the code that you are currently editing. That way you don't need to run all the tests all the time.

Something else that can slow your cycles down is if your language has a slow compilation process. In that case you should look into ways of only re-compiling the part of the code that changed instead of re-compiling everything, or you should look into using an interpreter instead of compiling every time. Or you can change the compiler settings to optimize for fast compiling instead of for fast code.

Another thing that can slow your cycles is if your test involves contacting some API on a remote server. In that case it is important to duplicate these servers on your local machine, at least with the part of the data that you are using for this test. By having all the servers duplicated locally, api requests will be instant.

You need to be extremely strict when it comes to optimizing your cycle length. Do not compromise.
Building tools that shorten your cycle length is almost always a good investment.

[glossary](/README.md)
