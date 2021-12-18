# What Are Partial Applications?

at least for me, partial applications are a new concept, and they're SUPER COOL! they're basically functions with an arg already set, lets take a look for better understanding

```ml
let sum a b = 
    a + b
let _ = 
    let my_partial_application = sum(15)
    in puts(my_partial_application(15))
    >> puts(my_partial_application(5))
``` 
Output:
```
30
20
```

See? its pretty cool!