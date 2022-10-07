# Scheduler
Different Schedulers for @stealify/stealify 

## Tasks
The Main Unit that gets Scheduled in the Stealify Component System is a Task it can be composed out of many Tasks a Task gets created via composition pointing to some run able instructions and a scheduler that then gets finally thrown into a so called sink or runEffects instruction that is a form of lifecycle manager it takes your defined tasks so the run instructions and schedulers and executes them as also manages any errors or new tasks that result out of that task run. A Simple JS Example with pseudo code

```ts
const defaultScheduler = (run) => run();
runEffects([newTask({ run, defaultScheduler }), newTask({ run, defaultScheduler })]);
```

This is the basic concept of functional reactive programming by the way and also is the core of the web also a importent concept that we want to mention here is a so called tail call which does not get attached to a existing stack this sounds technical and you will most likely not know
what we are talking about here the pseudo code

```ts
const willGetTailCalled = () => willGetTailCalled();
willGetTailCalled();
```

When Tail Call is implemented correct this will result in a so called Heap that has a call stack of 2 else it would memory leak and blow up the application as willGetTailCalled() would get always added on top of each other and not get referenced.

Correct Tail call implementation is needed to code Functional Loops without concepts like for if else so we can code with that static deterministic loops that can get highly optimized. 

In JS/ES6 Tail Call got fixed so ECMAScript engines should be able to handle that correct **Hurray**
