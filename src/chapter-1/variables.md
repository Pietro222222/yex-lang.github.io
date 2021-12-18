Every Variable in Yex is immutable, so, if you create it, it'll have the same value forever.


Lets learn how to create a variable in Yex, its pretty easy!

```ml
let _ = 
    let my_var = my_value
```
See? pretty easy!

sometimes we need to change the value of a variable, in that case, re-declare it. technically its not the same variable, but who cares? it'll work perfectly.

```ml
let _ = 
    let my_var = 10
    in let my_var = 5
    in puts(my_var)
```

the variable is now 5!