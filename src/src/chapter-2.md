as you already know, Yex is a dynamic typed language, you can give a variable any type you want, a function can return any type and so on.

Yex has many data types


|    Name   |                 Description                  |
|:---------:|:--------------------------------------------:|
| `Bool `   | the boolean type                             |
| `Num  `   | the number type, its a float                 |
| `Str  `   | the string type                              |
| `Nil  `   | null value                                   |
| `Err`     | :err and :ok type, useful for error handling |
| `Table`   | Tables are something like Js Objects         |
| `Lists`   | basically arrays                             |

we wont talk about all the data types in this chapter.

# note 
All variables in Yex are `immutable`. the only way to change a variable's value is to re-declare it!