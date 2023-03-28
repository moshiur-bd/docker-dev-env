# How to setup alpine linux container for C++ development/contest

- Install alpine image.
- Into the container install following packages by just executing the command
```
apk add fish git neovim make g++ wget
```
- Run 
```
nvim
```
- ...



# ALternatively just build the dockerfile to quickly get started
- Create a docker container and ssh into it
```
docker build -t "cpp-img" .
docker run --name cpp -it -v /path/to/a/host/folder:/root/repos cpp-img
```
- Execute command `nvim`
- Fix mago config. Run `mango parse`. Edit `~/.mango/config.json` file to fix Workspace and SrcDir field
