# How to configure ssh

## How to generate ssh keys
1. Create directory .ssh
```sh
mkdir ~/.ssh
```
2. Open ssh folder
```sh
cd ~/.ssh
```
3. Generate ssh key (you can push enter in all)
```sh
ssh-keygen
```
4. You can see your own ssh public key
```sh
cat id_rsa.pub
```

## How to add ssh to GitHub
1. Go to configuration in GithuB - SSH & GPG Keys
<p align="center">
  <img src="https://image.ibb.co/k8n2hG/ssh_github.png">
</p>

2. Click in New SSH key
<p align="center">
  <img src="https://image.ibb.co/g3WW9w/new_ssh.png">
</p>

3. Put your public key in the key field and click in Add Key. Remember you can see your public key using:
```
cat ~/.ssh
```

