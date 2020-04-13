| Profesor: | Ing. Ignacio Javier Bonelli |
|-----------|-----------------------------|
| JTP:      | Ing. Hector Levi            |
| Ayudante: | Ing. Carlos Cuttita         |
| Ayudante: | Pedro Vassena               |


# Guía de Linux

Práctica básica de los comandos más comunes de GNU/linux en bash.

## man:

Ejecute el siguiente comando. ¿Por qué falló?
```bash
$ man
```
Ejecute el siguiente comando y lea brevemente la descripción. ¿Qué hace `man`?
```bash
$ man man
```
Ejecute los siguientes comandos. ¿Son lo mismo? Como desarrolladores, ¿Cuál nos interesa más?
```bash
$ man printf
$ man 1 printf
$ man 3 printf
```

## ls:

Ejecute el siguiente comando y lea brevemente la descripción. ¿Qué hace `ls`?
```bash
$ man ls
```
Ejecute el siguiente comando y observe la salida. ¿Reconoce alguna carpeta?
```bash
$ ls
```
Ejecute el siguiente comando y observe la salida. ¿Qué son los archivos y carpetas con punto adelante?
```bash
$ ls -a
```
Ejecute el siguiente comando y observe la salida. ¿Qué representan las diversas columnas?
```bash
$ ls -l
```
Ejecute los siguientes comandos. ¿Son lo mismo?
```bash
$ ls -a -l
$ ls -al
```
Ejecute los siguientes comandos. ¿Qué es lo que estamos haciendo?
```bash
$ ls ~
$ ls /
$ ls /home
```

## pwd:

Ejecute el siguiente comando. ¿Qué hace `pwd`?
```bash
$ man pwd
```
Ejecute el siguiente comando. ¿En qué directorio estamos trabajando?
```bash
$ pwd
```

## cd:

Ejecute el siguiente comando. ¿Por qué falló?
```bash
$ man cd
```
Ejecute el siguiente comando. ¿Qué hace `cd`? ¿Por qué no está en el manual ()?
```bash
$ help cd
```
Ejecute los siguientes comandos. ¿Qué hizo `cd`? ¿Qué carpeta lista `ls` cuando no tiene parámetros?
```bash
$ ls
$ cd /
$ pwd
$ ls
```
Ejecute los siguientes comandos. ¿Qué representan . y .. en linux?
```bash
$ cd /
$ pwd
$ ls
$ cd /home
$ pwd
$ ls
$ cd .
$ pwd
$ ls
$ cd ..
$ pwd
$ ls
```
Ejecute los siguientes comandos. ¿Qué es ~ en linux? ¿A qué directorio cambia `cd` cuando no tiene parámetros?
```bash
$ cd ~
$ pwd
$ cd
$ pwd
```
Ejecute el siguiente comando para iniciar una sesión de bash adentro de su sesión de bash,
permitiendo guardar el flujo de salida en un archivo. `bash` es para ejecutar la shell, `|`
es para redirigir la salida de un comando a la entrada de otro, y `tee` sirve para guardar
una copia del flujo de salida en un archivo. No es necesario que lo aprendan, pero si les
interesa está muy bueno y es útil.

`$ bash | tee log_clase_1.txt`

## mkdir:

Ejecute el siguiente comando. ¿Qué hace `mkdir`?
```bash
$ man mkdir
```
Ejecute los siguientes comandos para crear una carpeta en la cual trabajar.
```bash
$ mkdir practicalinux
$ cd practicalinux
$ pwd
```
A partir de aquí asumimos que ya sabe como detectar en qué directorio están trabajando,
utilizando pwd o observando el directorio en el prompt de su terminal,
por lo que no lo volveremos a mencionar.

Ejecute el siguiente comando y observe la salida.
```bash
$ mkdir dir0
$ ls
```
Ejecute los siguientes comandos. ¿Por qué falló el primero? ¿Cómo lo solucionamos?
```bash
$ mkdir dir1/dir2
$ mkdir -p dir1/dir2
$ ls
```

Ejecute los siguientes comandos para crear un archivo con el que poder ejecutar los siguientes comandos
```bash
$ ls >> arch0.txt
$ ls
```

El comando de dirección de flujo `>>` redirige el flujo de salida y lo agrega al final de un archivo.
Este tipos de comandos (de direccionamiento de flujo) son una herramienta muy poderosa
que le da un gran poder a los usuarios avanzados de linux para diversas tareas cotidianas.
Un ejemplo que puede servir para informática 1, es al hacer logging, emitir los logs por stderr
y redirigir stderr a un archivo, utilizando el comando:

`$ ./a.out 2>>log.txt`

Ejecute (si quiere) el comando para instalar un paquete llamado `tree`,
que permite mostrar de forma bonita carpetas y archivos de forma recursiva.

`$ sudo apt install tree`

En caso de no querer descargar el paquete, puede realizar una función similar
ejecutando este comando en su lugar cuando sea necesario.

`$ find`

## cp

Ejecute el siguiente comando. ¿Qué hace `cp`?
```bash
$ man cp
```
Ejecute los siguientes comandos. ¿Por qué falló el primero? ¿Cómo lo solucionamos?
Ejecutamos tanto `tree` como `find` para que los que instalaron `tree` puedan ver las diferencias entre ambos.
```bash
$ cp dir1/dir2 dir_3
$ cp -r dir1/dir2 dir_3
$ tree
$ find
```
Ejecute los siguientes comandos. ¿Qué hizo el primero? ¿Qué hizo el segundo?
```bash
$ cp -r dir1/dir2 .
$ cp arch0.txt dir3/
$ tree
```

## mv

Ejecute el siguiente comando. ¿Qué hace `mv`?
```bash
$ man mv
```
Ejecute los siguientes comandos. ¿Qué hizo cada uno?
```bash
$ mv arch0.txt dir0/
$ tree
$ mv dir0/arch0.txt arch1.txt
$ tree
$ mv dir0 dir4
$ tree
```

## rm

Ejecute el siguiente comando. ¿Qué hace `rm`?
```bash
$ man rm
```
Ejecute cuidadosamente (`rm` no perdona) los siguientes comandos y observe sus efectos.
```bash
$ rm arch1.txt
$ tree
```
Ejecute cuidadosamente los siguientes comandos. ¿Por qué falló el primero? ¿Cómo lo solucionamos?
```bash
$ rm dir4
$ rm -d dir4
$ tree
```
Ejecute cuidadosamente los siguientes comandos. ¿Por qué falló el primero? ¿Por qué la solución es distinta?
```bash
$ rm -d dir3
$ rm -r dir3
$ tree
```
## Finalización

Ejecute estos comandos para eliminar recursivamente todos los archivos creados,
dejando su computadora como estaba al inicio de la práctica.
```bash
$ cd ..
$ rm -r practicalinux
```
Ejecute los siguientes comandos. El primero sale de la sesión de bash interna.
El segundo le muestra que existe un archivo llamado "log_clase_1.txt" que
deberá enviar para la corrección del tp.
```bash
$ exit
$ ls -l | grep log_clase_1.txt
```

Si decide que no quiere más el paquete `tree`,
ejecute el siguiente comando para eliminarlo.

`$ sudo apt purge tree`
