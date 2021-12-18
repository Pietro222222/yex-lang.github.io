Lists in Yex are basically arrays, but they're a little bit different. first of all they're immutable just like any yex variable (but we can add items to it). so lets take a look how to use them

```
let _ = 
    let my_array = [1, 2, 3]
    in puts(myarray)
    >> puts(myarray[1])
```
using arrays in yex is just like using arrays in python, but...

# The Cons (::) Operator

the Cons operator is used to add new itens at the start of the array
```ml
let _ = 
    let my_array = [1, 2, 3]
    in puts(0 :: my_array)
```

in this example, we added 0 to the start of the array! but how do we append itens into the array? well... we'll need to create our own append function, dont worry its pretty easy

```ml
let append array item = 
    rev(item :: rev(array))
```

First of all, what is the `rev` function? the rev function basically reverses the array. so `[1, 2, 3]` turns into `[3, 2, 1]`. the logic behind the append function is: 

reverse the array, use the cons operator to add an item at the start of the array, reverse it back. so the first element becomes the last. this sounds kinda crappy but its funny, right? lets test it!

```ml
let append array item = 
    rev(item :: rev(array))
let _ = 
    puts(append([1, 2, 3], 4))
``` 
Output:
```
[1, 2, 3, 4]
```
it works! see, it was pretty easy!

# Head and Tail Functions

```ml
let _ = 
    let my_array = [1, 2, 3]
    in puts(head(my_array))
    >> puts(tail(my_array))
```

the head function basically returns the first element, and the tail function returns all elements but the first.