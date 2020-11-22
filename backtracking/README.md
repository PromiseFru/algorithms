## Backtracking
### What is backtracking?

* According to Wikipedia Backtracking is a general algorithm for finding all (or some) solutions to some computational problems, notably constraint satisfaction problems, that incrementally builds candidates to the solutions, and abandons a candidate ("backtracks") as soon as it determines that the candidate cannot possibly be completed to a valid solution.

* Backtracking can be applied only for problems which admit the concept of a "partial candidate solution" and a relatively quick test of whether it can possibly be completed to a valid solution. It is useless, for example, for locating a given value in an unordered table. When it is applicable, however, backtracking is often much faster than brute force enumeration of all complete candidates, since it can eliminate many candidates with a single test. 

* Backtracking is an important tool for solving constraint satisfaction problems, such as crosswords, verbal arithmetic, Sudoku, and many other puzzles.

### Pseudocode

* In order to apply backtracking to a specific class of problems, one must provide the data P for the particular instance of the problem that is to be solved, and six procedural parameters, root, reject, accept, first, next, and output. These procedures should take the instance data P as a parameter and should do the following: 
    1. root(P): return the partial candidate at the root of the search tree. 
    2. reject(P,c): return true only if the partial candidate c is not worth completing. 
    3. accept(P,c): return true if c is a solution of P, and false otherwise. 
    4. first(P,c): generate the first extension of candidate c. 
    5. next(P,s): generate the next alternative extension of a candidate, after the extension s. 
    6. output(P,c): use the solution c of P, as appropriate to the application.

* The backtracking algorithm reduces the problem to the call bt(root(P)), where bt is the following recursive procedure:
```
procedure bt(c) is
    if reject(P, c) then return
    if accept(P, c) then output(P, c)
    s ← first(P, c)
    while s ≠ NULL do
        bt(s)
        s ← next(P, s)
```

