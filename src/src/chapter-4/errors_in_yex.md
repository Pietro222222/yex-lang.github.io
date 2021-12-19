Errors in Yex are represented by the :err and the :ok type. lets create a function that returns an error when a value is an integer to demonstrate how errors work in Yex
```ml
let function arg = 
    if type(arg) == "num" then 
        err("argument is a number")
    else 
        ok("argument accepted")
```
now lets call the function!

```ml 
let _ = 
    puts(function(2))
    >> puts(function("string"))
```    
Output:
```
[:err, "argument is a number"]
[:ok, "argument accepted"]
```
so we got an array with the status (:err or :ok) and the message

lets now handle this error

```ml
let _ = 
    let res = function(2)
    in if res[0] == :err then 
        panic("GOT AN ERROR!!!!!")
    else 
        puts("Everythings fine")
```

output:
``` 
[10:36] GOT AN ERROR!!!!!
``` 

try to change the value to a string and see the result!

# The Panic function

the panic function does what it say it does, it panics and prints where it was called `[10:36]` in the last examlpe




