# How to install Spotify Linux

<p align="center">
  <img src="http://images.wondershare.com/images/music/spotify-logo2.png" width="250">
</p>

## Install on Debian
### First option
 1. Add the Spotify repository signing keys to be able to verify downloaded packages
```sh
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0DF731E45CE24F27EEEB1450EFDC8610341D9410
```
 2. Add the Spotify repository
```sh
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list
```
 3. Update list of available packages
```sh
sudo apt-get update
```
 4. Install Spotify
```sh
sudo apt-get install spotify-client
```

### Second option
 1. Install aptitude
```sh
sudo apt-get install aptitude
```
 2. Install spotify-client with aptitude
```sh
sudo aptitude install spotify-client
```

### Posible errors
#### Error with libgcrypt.so
spotify: error while loading shared libraries: libgcrypt.so.11: cannot open shared object file: No such file or directory
##### Fix (option 1)
```sh
sudo dpkg -i libgcrypt11_1.5.0-5+deb7u1_amd64.deb
```
##### Fix (option 2)
1. Try to execute:
```sh
/usr/bin/./spotify
```
2. All ok? Let's do:
```sh
echo "alias spotify='/usr/bin/./spotif'" >> ~/.bashrc
```
#### Fix (option 3 - not recommended)
```sh
sudo ln -s /usr/lib64libgcrypt.so /usr/lib64libgcrypt.so.1
```
