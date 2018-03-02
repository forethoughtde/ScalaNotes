## Lecture 1.1

Functional programming is a paradigms. 
**paradigms** means in science, *distinct concept or thought pattern* in some scientific discipline. 

Main programming paradigms are;
1. Imperative programming
2. functional programming and 
3. Logic programming (lesser known)

Orthogonal to the above programming languages is object oriented programming; meaning it can be combined well with the 
above three of them. 


#### Imperative programming
1. Modifying mutable variables, 
2. Using assignments and
3. composed with control structures

Understanding imperative programming as instruction sequences for Von Neumann computer; it consists of processor, memory
and bus that reads both instructions and data from memory into a processor. 
Width of the bus is one machine word so 32bit or 64bit

Strong correspondence between

Mutable variables === memory cells
Variable dereferences === load instructions
Variable assignments === store instruction
Control structures === jump

**Problem:** Conceptualizing programs word by word; reason in larger structure. **Argument made by** John Backus. 

Scale up; we need to have high level abstractions such as collection, polynomials, geometric shapes and strings

Theory in Mathematics: 
1. one or more data types, 
2. operations on these types, 
3. laws that describe the relationships between values and operations

Theory does not define mutations; it means changing something while keeping identity of something. 

Polynomial theory:
```
(a*x + b) + (c*x + d) = (a+c)*x + (b+d)

x = 3

3a + b + 3c + d = 3a + 3c + b + d
```

String theory:

Concatenation operator ++ which is associative. 

```

(a ++ b) ++ c = a ++ (b ++ c)

```

High level concepts following mathematical theories then there is no place for mutation. 

Functional programming means avoid mutations and have powerful ways to abstract and compose functions. 

Functional programming: 

**Restrict**
without mutable variables, assignments, loops and imperative control structures. 
**General**
Focuses on functions

Functions can be values that are produced, consumed and composed. 

Functions are First class citizens in FP; meaning, define function anywhere, inside another function, pass as a parameter
and return them 