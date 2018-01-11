# How to configure git

## Install git
```sh
sudo apt-get install git
```
## Configure global settings git
1. User identity
```sh
 git config --global user.name "John Doe"
 git config --global user.email johndoe@example.com
```
2. Editor 
```sh
 git config --global core.editor emacs
```

3. See your new configuration
```sh
 git config --list
```
