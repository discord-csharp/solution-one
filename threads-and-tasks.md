# Threads, Tasks and More

### Talk overview
This presentation recaps some of the basics of writing code that makes use of threads, tasks and asynchronous features in C#. It is a modified version of a talk the author has given to his team at Microsoft.

This is an intermediate level talk aimed at developers still learning how to write parallel and async code in C#.

Material covered includes:

* What are threads?
* What are tasks?
* What are the rare cases you would want to use threads directly instead of tasks?
* What is asynchronous code?
* What actually happens when we await an async method?
* Common misconceptions about async code and parallelism.
* How continuations work.
* How to run multiple async methods in parallel.
* The perils of mixing sync and async code.
* The non-zero cost of making code async.
* Using Task.Yield to avoid blocking the caller.
* The purpose of the Thread Pool.

Finally, the talk concludes with a demonstration putting some of these conepts together by illustrating the thread pool thread creation algorithm, how high bursts of activity can lead to disaster when executing I/O bound tasks, and how using async solves this problem beautifully.

### Slides
The slides for this talk can be found under the /threads-and-tasks-slides folder, [here](./threads-and-tasks-slides)
