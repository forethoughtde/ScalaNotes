## Lecture 1.3

The lecture is about evaluation strategies and termination. 

#### Overview

Scala uses *call-by-value* evaluation strategy by default ( exponential performance advantages ) and does support *call-by-name* by adding **=>** operator in front
of arguments

call-by-value plays nice with imperative effects and side effects. 

Both strategies reduce to same value providing expression terminates.

##### Rules
1. CBV terminates then CBN terminates as well.
2. The other direction is not true. 

Example showing *call-by-name* evaluation strategy in Scala
```
def constOne(x: Int, y: => Int) = 1
```

Example showing CBN terminates but CBV doesn't
```
def first(x: Int, y: Int) = x
```

##### CBN
```
first ( 3, loop )
reduced to 3
```

##### CBV
```
first ( 3, loop )
Will try to reduce loop to a value and get into infinite loop
```
