# Hello World

As you already know, Yex is a functional scripting language, but its also expression oriented, which means that every variable is in fact an expression. lets take a look at the `Hello, World!`.

```ml
let _ =
    puts("Hello, World!")
```
Output:
```
Hello, World!
```

as you can see, we started our program with `let _ =`, this is almost the main function, but theres a difference, since Yex is expression oriented each variable is the result of some given command, because of that, we need to assign a variable to the `puts()` function call. now you may be wondering `ok, so does "puts" return anything?`, yes. it does, everything in Yex does. by default, the value is `Nil`, the null value, but `puts` returns something else, lets take a look.

```ml
let _ = 
    puts("Hello, World!")
let _ = 
    puts(_)
```

Output
```
Hello, World!
:ok
```

it printed `:ok`, we're not going to explain `:ok` for now. 

# Running multiple Commands

If you try to run this Code: 
```ml 
let _ = 
    puts("Hello")
    puts("World!")
```
you'll get this error
```
[3:9] Expected `let`, found `puts`
```

basically the compiler is saying "hey, you need to assign a variable to the second `puts` too!"

if we run 
```ml
let _ = 
    puts("Hello")
    let _ = 
        puts("World!")
```

It works!
```
Hello
World!
```

but, its kinda crappy, we dont want to keep adding `let _ =` for each command, thats why Yex has the `in` keyword, the `in` keyword basically tells the compiler `You know the last command? keep it, but run me`

```ml
let _ = 
    let _ = 
        puts("Hello")
        in puts("World!")
```

Output:
```
Hello
World!
```

note that we still added the `let _ = ` for the new command, its because we dont have any variable, therefore nothing to save in the memory, so we dont need the `in` keyword inside the first `let _ = ` block.

### The Sequence (>>) Operator

the `>>` operator basically tells the compiler `You know the last command? well, we dont need him anymore, run me`

```ml
let _ = 
    puts("Hello")
    >> puts("World!")
```
Output: 
```
Hello
World!
```

See? it works! but you shouldnt use it everywhere, it has its use cases. to understand better, lets take a loot at this code

```ml
let _ = 
    let my_var = 3
    in puts(my_var)
```
Output:
```
3
```

It prints `3`, but what if we try to run the same code, but instead of `in` we use `>>`?

```ml
let _ = 
    let my_var = 3
    >> puts(my_var)
```

And we have an error!

Output: 
```
[4:2] Expected `in` after let expression, found <eof>
```

this error message may sound weird (and it actually does), but the compiler is telling us that we should use the `in` keyword somewhere in the code. ok lets run this code:

```ml
let _ =
	let my_var = 3
	>> puts(my_var)
	in puts(my_var)
```
Output:
```
[3:16] unknown variable :my_var
```

now that we've used the `in` keyword to print `my_var`, the compiler tell us another error `unknow variable :my_var`. at this point you probably already got it, since the >> ignores the last command, this variable doesnt exist yet.

we if we try to run this code
```ml
let _ =
	let my_var = 3
	>> puts(3)
	in puts(my_var)
```

the output is 
```
3
:ok
```
"What? it printed `:ok`!" 
<br>
it printed `:ok` because the value of the variable my_var is the result of the last operation (`>> puts(3)`) 

