# stack-lang
# syntax:
`variable <- operation arguments`

# operation types:
## create a stack
`StackName <- stack create`

Note: if the stack already exists, then nothing happens

**example:**
a`lpha stack create`

in this case you're create a stack and putting it in the alpha variable

## push onto the stack
`ERR <- StackName push elements to push here`
ERR is if there's an error (error is a stack of its own), if the error stack already exists, it'll just push onto that in a `_ ERR push whatever the error is` sub-operation of its own
stuff you push is separated by a space 

Notes:
* if a stack operation is made in the elements to be pushed area, the output of that operation will be pushed
* If the stack doesn't exist, it will be created in a sub-operation

**example:**
`error alpha push a b c d`

In this case it's pushing "a", "b", "c", "d" onto the stack where "a" will be the top most element

## pop from the stack (pops zeroeth element)
`variable <- StackName pop`

this pops the top most element. You can do funky stuff like what is given in the example
Notes:
* If the stack doesn't exist, a stack operation will be made, and nothing will be popped
* Arguments will be ignored

**example**
`beta push alpha pop`

As shown in the previous example, "a" is the top most element, therefore the "a" will be the only element of beta

## print stack
`stdout print StackName1 StackName2 StackName3 ...`
You can print as many stacks as you want. for each additional stack, it'll append to the previous output. 

**example 1:**
`stdout print alpha`

In keeping with the previous examples, this prints `b c d`

**example 2**
`stdout print alpha beta`

this prints
```
alpha: `b c d`
beta: `b`
```
