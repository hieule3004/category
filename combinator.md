# combinator: monad perspective

### Abstract
#### Relation
\* SKI system -> Applicative

\* BCKW system -> Monad

#### Lambda calculus
\* variables have arbitrary type
- combinators have arbitrary arity

\* combinators are total function (no abstraction)
- variable: simple argument return (command no args) e.g. I, K
- application: (command with args) the return type of combinator is return type of the command
- Corollary: at most 1 argument (function/variable) act as command
    - new return type to maximise generality of applicable function
    - unique due to constructive proof: if there are 2 such functions (e.g a -> c and b -> c), then a merge function must exist (e.g. c -> c -> d) then d is the new return type.


### Monad
\* Functor -> Applicative -> Monad

\* Function type (simplified Reader monad) (->) r
- Function
id :: a -> a = I
flip :: (b -> a -> c) -> a -> b -> c = C
- Functor
fmap :: (a -> b) -> (r -> a) -> (r -> b) = B
- Applicative
return :: a -> (r -> a) = K
ap :: (r -> a -> b) -> (r -> a) -> (r -> b) = S
- Monad (category theory definition)
unit :: a -> (r -> a) = K
join :: (r -> r -> a) -> (r -> a) = W

\* Alternative to join: more practical usage (functional programming definition)
- bind :: (r -> a) -> (a -> r -> b) -> (r -> b) = C (B S C)
    + use with do notation: similar to ; in imperative language
- reverse bind :: (a -> r -> b) -> (r -> a) -> (r -> b) = B S C
    + flip argument of bind

### Bonus: Combinator calculus
\* SKI system
- S = B(BW)(BBC) = B(B(BW)C)(BB)
- I = SK_ = CK_ = WK

\* BCKW system
- B = S(KS)K 
- C = S(BBS)(KK) = S(S(K(S(KS)K))S)(KK)
- W = SS(SK)

\* BTAM system: BCKW alternative
- T = CI
- A = KI
- M = WI

### Bonus: Fixed point
Y :: (a -> a) -> a
Y f = f (Y f)
- this is recursion

### References
1. https://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html
1. https://en.wikibooks.org/wiki/Haskell/Category_theory#Monads
1. https://eli.thegreenplace.net/2018/haskell-functions-as-functors-applicatives-and-monads/
1. https://hackage.haskell.org/package/data-aviary-0.4.0/docs/Data-Aviary-Birds.html
1. https://doisinkidney.com/posts/2020-10-17-ski.html
1. https://stackoverflow.com/questions/49412721/bird-name-for-the-combinator
