to read and write files in Yex, we have the `fread` and `fwrite` functions, lets see how to use them.

# Writing in a file

```ml 
let _ = 
    fwrite("/path/to/file", "content")
```

the fwrite functions returns an Error Type (:ok or :err), so it should be fine to handle errors

### note
when the fwrite function returns an error, it also returns the reason, example: 

```ml
let _ = 
    fwrite("/root/test", "content")
    |> puts
```
Output:
```
[:err, "PermissionDenied"]
```

the same happens with fread

# Reading a file
```ml 
let _ = 
    fread("/path/to/file")
    |>puts 
```