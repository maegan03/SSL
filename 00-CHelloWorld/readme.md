# TP0: Hola Mundo

"Hello, World" en C

### Compilador Elegido

Elegí el compilador GCC 14, ya que lo tengo a mano en mi sistema Linux:

~~~console
$ gcc --version
gcc (GCC) 14.2.1 20240912 (Red Hat 14.2.1-3)
Copyright (C) 2024 Free Software Foundation, Inc.
Esto es software libre; vea el código para las condiciones de copia.  NO hay
garantía; ni siquiera para MERCANTIBILIDAD o IDONEIDAD PARA UN PROPÓSITO EN
PARTICULAR
~~~

### Compilación y Ejecución:

Compilé desde la terminal con el estándar C23:

~~~sh
gcc hello.c -std=c23
./a.out > output.txt
~~~

### C2Y

Aunque haya terminado eligiendo C23 por comodidad, tuve la *osadía* de probar
C2Y, y este fue mi primer resultado:

~~~console
$ gcc hello.c -std=c2y
gcc: error: unrecognized command-line option ‘-std=c2y’; did you mean ‘-std=c23’?
~~~

Al [buscar en internet](https://www.phoronix.com/news/LLVM-Clang-19-std-C2Y)
descubrí que C2Y aún está en desarrollo, pero que clang 19 introdujo soporte.

En las páginas oficiales, sólo encontré el código fuente para compilar clang.
Por suerte, Arch Linux tiene un
[paquete](https://archlinux.org/packages/extra/x86_64/clang) de clang 19.
Ejecuté Arch Linux en un container de Docker:

```sh
docker run -it archlinux
pacman -Syu
pacman -S clang git
git clone https://github.com/maegan03/SSL
cd SSL/00-CHelloWorld
clang hello.c --std=c2y
./a.out > output.txt
```
