to create a function theres 2 ways. 

# Creating a function with arguments

if you want to create a function that receives arguments, thats the way to go

```ml
let greetings name = 
    puts("Hello " + name)
let _ = 
    greetings("Yex")
```

# Creating a function without arguments

to create a function without any arguments its a little different

```ml 
let hello_world = fn = 
    puts("Hello World!")

let _ = 
    hello_world()
```

fn is the Anonymous Functions keyword, so you can do something like this
```ml
let _ = 
    puts((fn arg = arg*2)(2))
```
useful, right?

# returning values
the return value of a function is always its last command

```ml
let my_function arg = 
    if arg == 1 then 
        true
    else 
        false
let _ = 
    puts(my_function(2))
    >> puts(my_function(1))
```
Output:
```
false
true
```