Functional Programming

### Comparision
- OOP vs FP: the object of concern / first class citizen i.e. object/message vs function
- Imperative vs declarative: style of coding, same as procedural vs functional paradigm

### Principle
- Pure: no side-effect, expected IO result. Implementation includes:
    - no void returning function, instead, explicit return world
    - immutable data, copy instead of replace references
    - structure level pattern matching
- First class function: higher order function, higher kind type
    - not all language support this, even if do, meta-programming is not nice

### Monad
#### Mathematics
- Monoid in category of endofunctor
    - Endofunctor: higher kind * -> *. This is exactly Generics e.g. Int -> List<Int>
        - Thus monad are generics of generics (e.g. Monad<List>), with additional properties
    - Monoid: unital, associative operator
        - functor: map -> transform parameters
        - return eta: constructor -> convert raw type to parameterised type
        - join mu: flat map -> reduce multiple layers of parameterised type, allows composition / parameterised operation

#### Application
- 2 common usages:
    - control i.e. maybe, try, either
    - collections i.e. iterable, traversible