in Yex, we have 3 functions to mess up with folders `readdir`, `mkdir` and `rmdir`.

both return and array with `:err` and the message when something wrong happens

# Reading a directory

```ml
let _ = 
    readdir("/tmp")
    |> puts
```
the readdir function returns an array of tables similar to this:

```ml
[{:filename = "file", :isdir = false}, {:filename = "dir", :isdir = true}]
```

# Creating a directory

```ml
let _ = 
    mkdir("/path/to/dir")
``` 

the mkdir function returns an `:ok` or `[:err, "message"]`

# deleting a dir


```ml
let _ = 
    rmdir("/path/to/dir")
``` 

the rmdir function returns an `:ok` or `[:err, "message"]`