Tables are one of my favourite things in Yex, they work the same way JavaScript Objects Does!

lets see how we create them.
```ml 
let my_table = {}
```
pretty easy, right? but at the moment our table is empty, to add stuff there is pretty easy too!
```ml
let _ = 
    let my_table = {:your_item = value}
    in puts(my_table)
```

easy!!! but how do we insert new values there after its declaration? in yex we have the `insert` function, but, since yex variables are immutable we'll need to re-declare it. lets see how we do that!

```ml 
let _ = 
    let my_table = {:item = 2} 
    in puts(my_table)
    >> let my_table = insert(:item_name, 20, my_table)
    in puts(my_table)
```
output: 
``` 
{:item = 2}
{:item = 2, :item_name = 20}
```

it worked! but until now tables are basically useless, because we dont know how to get values from there, so lets see how we do that

```ml
let _ = 
    let my_table = {:item = 20}
    in puts(my_table[:item])
```
output:
```
20
```

Thats it! tables are pretty simple yet powerful!