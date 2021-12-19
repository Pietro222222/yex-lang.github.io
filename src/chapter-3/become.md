The Become Keyword allows you to have recursion, Google: 
`In computer science, a tail call is a subroutine call performed as the final action of a procedure. If the target of a tail is the same subroutine, the subroutine is said to be tail recursive, which is a special case of direct recursion. Tail recursion is particularly useful, and often easy to handle optimization in `. lets take a look at it

```ml
let for_each cb arr = 
	let loop current max array callback myself = 
		callback(array[current])
		>> if current == max then 
			0
		else 
			become myself(current+1, max, array, callback, myself)

	in loop(0, #arr-1, arr, cb, loop) 

let _ =
    [1, 2, 3]
    |> for_each(puts)
```
Output:
```
1
2
3
```

in this example, we created the `for_each` function, used to run a function with with the arg being an element of the array