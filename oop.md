# Object-oriented programming: the right way

### Principles 
> OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things.
<br><i>Alan Kay - codeveloper of Smalltalk, considered to define the term "OOP" </i>

#### Isolation
- Isolation means local retention and protection and hiding of state-process
    - This mean no shared mutable state

#### Messaging
- Messaging means the message sender is only loosely coupled to the message receiver, through the messaging API
    - This is to help decoupling "objects"

#### (Extreme) Late binding
- (Extreme) Late binding mean to bind value of objects at runtime, instead of compile time.
    - This is the abstract of call by name/reference where implementation code is looked up by name in a lazy way

### Case study: Java

#### The static keyword
- Issue: everything is a class
- Ugly: utils class which treat class as namespace, object contain only static methods as global functions
    - The OOP way: Use Bean, but introduce overhead in memory usage, and potential concurrency issue

#### Inheritance
- Issue: diamond problem (car, big car, red car, big red car)
    - Fix: Composition pattern
- Ugly: default keyword in Interface, which defeat the purpose of inteface, being the abstraction

### Bonus: The FP perspective

#### Mutable vs immutable
- No side effects, or to be more precise, make changes explicit
    - Bottom type vs Maybe monad
    - Exception vs Try monad
    - Void function vs Writer monad or Lens

#### Imperative vs declarative
- Example: iteration vs recursion
- Machine instruction or human readable code


### References
1. https://medium.com/javascript-scene/the-forgotten-history-of-oop-88d71b9b2d9f
1. https://ovid.github.io/articles/alan-kay-and-oo-programming.html