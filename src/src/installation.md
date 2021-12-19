# part 1

Yex is written in rust, therefore it depends on rust. 

## Linux Rust Installation 

Installation steps for Linux

### ArchLinux

in ArchLinux you can install Rust through pacman 
```
# pacman -S rust 
```

for more information take a look at [this](https://wiki.archlinux.org/title/Rust)  

### Any Other Distro
```
curl https://sh.rustup.rs -sSf | sh
```


## Yex Installation 

Yex comes in 2 versions, the lite and the full. the lite version has less features, but also less packages, so the compile time will be faster, although yex doesnt take too long to compile. 

### What should i choose?

you probably should pick the full version, because it contains the REPL (interactive mode). if you dont need the repl, then pick the lite version.

### full version installation

```
cargo install --git https://github.com/nonamescm/yex-lang.git --features=repl
```

### lite version installation
```
cargo install --git https://github.com/nonamescm/yex-lang.git
```

### Notes

yex is installed in the `cargo` bin directory, not in `/usr/bin/`, therefore you wont be able to run `yex`, to fix this simply add this line to your .bashrc/.zshrc
 
```
export PATH=/home/<your_user>/.cargo/bin:$PATH
```
