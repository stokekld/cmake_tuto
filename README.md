# Tutorial Cmake

CMake es un sistema de código abierto diseñado para construir, hacer pruebas y empaquetar software. Es usado para controlar el proceso de compilación usando una plataforma simple y archivos de configuración independientes del compilador. Genera makefiles nativos y espacios de trabajo que pueden ser usados en el entorno de compilación que tu prefieras. [más](https://cmake.org/overview/)

## Instalación

* Debian
```
$ sudo apt-get install cmake
```

* Fedora
```
$ sudo yum install cmake
```

## Variables Globales

* `CMAKE_BINARY_DIR`: Si estás construyendo desde la fuente, esta variable es la misma que `CMAKE_SOURCE_DIR`. De otra manera, es la raiz del árbol de directorios.

* `CMAKE_SOURCE_DIR`: Es el directorio desde donde se ejecuta cmake.

* `EXECUTABLE_OUTPUT_PATH`: Esta variable se puede modificar para especificar el lugar donde cmake debe poner todos los archivos ejecutables en vez de ponerlos en `CMAKE_CURRENT_BINARY_DIR`.
  ```
  set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
  ```

* `LIBRARY_OUTPUT_PATH`: Esta variable se puede modificar para especificar el lugar donde cmake debe poner todas las bibliotecas en vez de ponerlos en `CMAKE_CURRENT_BINARY_DIR`.
  ```
  set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)
  ```

* `PROJECT_NAME`: Es el nombre del proyecto definido por el comando `project()`.

* `PROJECT_SOURCE_DIR`: Contiene la ruta completa de los archivos fuente del projecto.
  ```
  add_executable(hello ${PROJECT_SOURCE_DIR}/test.cpp)
  ```
