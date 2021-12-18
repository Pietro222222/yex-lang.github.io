The Pipe Operator takes the result of the last command and uses it as the last argument in a function call, lets take a look

```ml
let _ =
    [1, 2, 3]
    |> puts
```
Output
```
[1, 2, 3]
``` 
pretty cool, isnt it?

you can use pipes multiple times, like this

```ml
let _ = 
    [1, 2, 3]
    |> rev 
    |> map(fn a = a * 2)
    |> fold(0, fn acc a = acc + a)
    |> puts
```
output: 
```
12
```
this is one of my favourite features in Yex!