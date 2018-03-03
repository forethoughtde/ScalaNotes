## Lecture 1.2
Elements of Programming

Non-trivial programming languages provide:

1. primitive expressions representing the simplest elements
2. ways to combine and abstract expressions; Abstract expression means giving a name to expression and referring them 
later on. 

Opening the REPL from sbt 
```
sbt console
``` 
[Primitive expression](https://www.ocf.berkeley.edu/~shidi/cs61a/wiki/Expression#Call_expressions)

Non-primitive expression evaluated as follow:

1. Take the leftmost operator
2. Evaluate the operand (left before right)
3. Apply the operator to the operands

A name in the expression will be evaluated by replacing it with the right hand side of its definition.

Evaluation stops when the process results in a value. 

**Example**
```
(2 * pi) * radius

(2 * 3.14) * radius

(6.28) * radius

(6.28) * 3

18.84
```

#### Parameters

Definitions can have parameters. Parameters are defined as below. 

```
def Square(x: Int):Int = x * x

def sumOfSquare(x: Int, y: Int) = square(x) + square(y)
```

Definition parameters are defined inside parenthesis; parameter name is followed by :(colon) then space then datatype. 

##### Datatypes in Scala
1. Int, --- 32 bit integer
2. Double, and -- 64 bit floating point number
3. Boolean (true or false)

#### Evaluation of functional application

1. Evaluate all function arguments (from left to right)
2. Replace all the function application by right-hand side and at the same time
3. Replace formal parameters of the function by actual arguments

##### Example 

```
sumOfSquares(3, 2+2)
sumofSquares(3, 4) ---> Step 1 (Evaluate all function arguments)
square(3) + square(4) ---> Step 2 (Replace all function application by right-hand side)
3 * 3 + square(4) ---> Step 3 (Replace formal parameters of the function by actual arguments)
9 + square(4)
9 + 4 * 4
9 + 16
25
```

This scheme of evaluation is called substitution model; idea underlying in this model is reduce an expression to a value. 

##### Avoid side effect

For example, 
```
c++
```
In the above expression, there is no better way to use substitution model to reduce it to a value because it changes value of c in a single expression. 

#### Alternative evaluation strategy

Instead of evaluating the function arguments at first, apply the right-hand side of the function application with unreduced arguments

**Example**
```
sumOfSquares(2, 3 + 3)
square(2) + square( 3 + 3 )
2 * 2 + square( 3 + 3)
4 + square( 3 + 3)
4 + (3+3) * (3 + 3)
4 + 6 * (3 + 3)
4 + 6 * 6
4 + 36
40 
```

There are two ways to evaluate a function; *call-by-value* and *call-by-name*

Both evaluation reduces to same value if the reduced expression consists of pure function and both evaluation terminates.

##### Advantages

*call-by-value* evaluates the function arguments only once. 
*call-by-name* does not evaluates unused arguments

