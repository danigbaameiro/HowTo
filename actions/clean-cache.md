# Liberar espacio
Hacer una limpieza de la carpeta /var/cache/apt/archives, donde se guardan los paquetes necesarios para instalar programas y aplicaciones. 

## Saber cuánto espacio están ocupando estos archivos
```sh
$ du -sh /var/cache/apt/archives
```

## Recuperar el espacio
```sh
$ sudo apt-get autoclean
```

## Elimina del cache los paquetes .deb con versiones antiguas
```sh
$ sudo apt-get clean
```

## Elimina todos los paquetes del cache.
```sh
$ sudo apt-get autoremove
```
