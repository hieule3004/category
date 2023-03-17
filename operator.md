### arity
- 0, 1, 2 are important
    - 0: contructor
    - 1: map / transformer
    - 2: reducer

### representation
- crazy idea: ops on X are functor from Set to X
    - still need more understanding of properties
    - all product, coproduct, pair type; different choice of function
    - e.g. +, *, ^ on N are just length function

### 1-properties
- idempotency: fixed point
    - inverse: opposite / reverse arrow ?; related to unitality and closure

### tensor
- tensor are nested fixed-size array -> dimensions is product type
    - reducer and array sounds like iterable again
- use lift / unlift (unitality) to move between dimensions
- transpose: reshape / swap basis, generalise to commutativity
- with strict typing
    - matrix addition make sense
    - matrix multiplication is weird

### 2-properties
- closure: endomorphism
- commutativity: paralel computation
    - both log and root are inverse of exp due to non-commutativity
- associativity: grouping / subexpression evaluation
    - maybe related lazyness / holed context (evidence?)
- distributivity: 
    - for some reason not of of great interested
    - this could be an evident that tetration is not the correct direction for higher order operations, also binops are NOT repeated application of one others