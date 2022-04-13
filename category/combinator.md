# combinator: monad perspective

### Abstract
Relation:
* SKI system -> Applicative
* BCKW system -> Monad

### Monad
* Functor -> Applicative -> Monad
* Function type (simplified Reader monad) (->) r
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
* Alternative to join: more practical usage (functional programming definition)
- bind :: (r -> a) -> (a -> r -> b) -> (r -> b) = C (B S C)
    + use with do notation: similar to ; in imperative language
- reverse bind :: (a -> r -> b) -> (r -> a) -> (r -> b) = B S C
    + flip argument of bind

### Bonus: Combinator calculus conversion
* SKI system
- S = B(BW)(BBC) = B(B(BW)C)(BB)
- I = SK_ = CK_ = WK
* BCKW system
- B = S(KS)K 
- C = S(BBS)(KK) = S(S(K(S(KS)K))S)(KK)
- W = SS(SK)
* BTAM system: BCKW alternative
- T = CI
- A = KI
- M = WI

### References
- [] https://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html
- [] https://en.wikibooks.org/wiki/Haskell/Category_theory#Monads
- [] https://eli.thegreenplace.net/2018/haskell-functions-as-functors-applicatives-and-monads/
- [] https://hackage.haskell.org/package/data-aviary-0.4.0/docs/Data-Aviary-Birds.html
- [] https://doisinkidney.com/posts/2020-10-17-ski.html
- [] https://stackoverflow.com/questions/49412721/bird-name-for-the-combinator
