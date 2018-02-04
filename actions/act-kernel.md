# Actualizar el kernel de Debian Jessie
```sh
$ sudo apt-get -u upgrade
```
## Instalamos aptitude
```sh
$ sudo apt-get install aptitude
$ sudo aptitude update
```

## Actualizar el kernel del sistema
```sh
$ sudo aptitude search linux-image
```

<p align="center">
  <img src="https://image.ibb.co/jREM1H/kernel.png">
</p>

```sh
# sudo aptitude install linux-image-"Versin del nucleo"
$ sudo aptitude install linux-image-4.14.0-parrot7-amd6
```

### Chuletario
#### Primera columna
    * “p” Significa que el paquete no se encuentra instalado en nuestro sistema.
    * “c” El archivo se eliminó pero los archivos de configuración todavía se encuentran.
    * “i”, el paquete se encuentra instalado.
    * “v”, el paquete es virtual.

#### Segunda columna
    * “i” El paquete se va instalar.
    * “d” El paquete se va eliminar.
    * “p” E paquete y sus archivos de configuración se van a eliminar.
    * “A” Significa que el paquete se instaló de manera automática.

#### Primera línea
Muestra el kernel actual

## Reiniciamos el sistema
```sh
$ reboot
```
