an if condition in Yex is almost the same as its in JavaScript, lets take a look 

```ml
let _ = 
    let my_var = 1
    in if my_var == 1 then 
        puts("1")
    else 
        puts("anything else")
```
Output:
```
1
```

try to change the value to anything else. theres also else if

```ml
let _ = 
    let my_var = 1
    in if my_var == 1 then 
        puts("1")
    else if my_var == 2 then 
        puts("2")
    else 
        puts("anything else")
```