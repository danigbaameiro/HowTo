# How to reproduce music on Emacs

## Install emm
```sh
$ sudo apt-get install emm
```

## Add emm to emacs
```sh
$ wget http://ftp.gnu.org/gnu/emms/emms-5.0.tar.gz
$ tar -zxf emms-5.0.tar.gz
$ mv emms-5.0 .emacs.d/lisp
```

## Edit emacs configuration and add
```sh
;;; emms
(add-to-list ‘load-path “~/.emacs.d/lisp/emms-5.0/”)
(require ‘emms-setup)
(emms-standard)
(emms-default-players)
```

### Configure default folder
```sh
;;; Add this line to .emacs
(setq emms-source-file-default-directory “~/Music/”)
```

## Put sond into Music folder
```sh
# You need install youtube-dl
$ youtube-dl --extract-audio --audio-format mp3 <video URL>
```

## How to use
### Play
```sh
M-x emms-play-file
```

### Stop
```sh
M-x emms-stop
```
