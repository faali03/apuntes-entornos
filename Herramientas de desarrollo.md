1. **Ejecuta el programa "Hola mundo" en los siguientes lenguajes:**

   - **bash**

     ```
     echo "Hola Mundo"
     ```

     

   - **python**

     ```
     print "Hola Mundo"
     ```

     

   - **javascript (nodejs)**

     ```
     console.log('Hola mundo');
     ```

     

   - **c**

   - 

     ```
     #include <stdio.h>
     
     int main()
     {
         printf("¡Hola, mundo!");
         return 0;
     }
     ```

   - **java**

     

     ```
     class Hola
     {
         public static void main(String[] args)
         {
             System.out.println("Hola Mundo");
         }
     }
     ```

------

**2.Para cada uno de los lenguajes anteriores, indica el proceso realizado para conseguir ejecutar el código: ¿compilación o interpretación?**

- Bash: es un lenguaje interpretado hecho en linux
- Python: este es tambien un lenguaje interpretado
- Javascript: es un lenguaje js interpretado
- C: compilado y ejecutado en linux
- Java: compilado e interpretado en linux
- Ensamblador: compilado

------

**3.Para cada uno de los lenguajes anteriores, indica el nombre del compilador o interprete utilizado en GNU/Linux.**

- Bash: terminal
- Python: Vs code
- Javascript: RunJS
- C: Terminal
- Java: terminal

------

**4.Investiga y averigua que extensión tienen los archivos de código fuente de los siguientes lenguajes:**

- bash: **.** sh
- python: py.
- php: .php
- javascript: .js
- c : .c
- c++: .cpp
- java: .java
- ensamblador: .asm
- ruby: .rb
- go: .go
- rust: .rs
- lisp: .lisp

------

6.**¿Qué extensión tienen los archivos de código objeto?**

(.obj) o extensión. o

------

7.**Lenguaje C. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes:**

8.**Lenguaje C. Código en varios archivos. Obtener el código binario ejecutable a partir del código objeto de los 3 archivos anteriores:**

Contiene el ejercicio 7 y8



1. **Bibliotecas. Define que se entiende por biblioteca o librería y los tipos que existen.**

   En informática, una **biblioteca** o, llamada por vicio del lenguaje, librería (del inglés **library**) es un conjunto de implementaciones funcionales, codificadas en un lenguaje de **programación**, que ofrece una interfaz bien definida para la funcionalidad que se invoca.

   Tipos:

   **Librerías estáticas**

   Estas se graban en un programa como ejecutables. Sirven exclusivamente para esto; después, podemos borrarlas sin problemas, ya que el programa seguirá funcionando con la función necesaria.

   **Librerías dinámicas**

   Son distintas a las estáticas en tanto en cuanto no se copian en el programa al compilarlas. Las subrutinas son cargadas en tiempo de ejecución, en vez de enlazarse en tiempo de compilación.

------

1. **Bibliotecas. ¿Qué tipo es el más utilizado actualmente? ¿Por qué?**

   Dinámica porque utilizan recursos independientes al ejecutable que las llama

------

1. **Bibliotecas. Crea una biblioteca dinámica en C que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente.**

```
gcc  -c  -fPIC  aritmetica.c

gcc  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o

cp  libaritmetica.so  /lib
```

------

1. **Bibliotecas. Crea una biblioteca dinámica en Java que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente.**

```
mkdir  aritmetica

javac  aritmetica/Aritmetica.java

jar  cvf  aritmetica.jar  aritmetica/*.class

mv  aritmetica.jar  /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext/aritm.jar
```

------

1. **Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas estáticas.**

   ventaja:

   1. No es necesario proporcionar las bibliotecas correspondientes al publicar el programa.
   2. La velocidad de carga del código es rápida y la velocidad de ejecución es ligeramente más rápida que la biblioteca de enlaces dinámicos

   Desventaja

   1. La biblioteca está empaquetada en la aplicación, lo que resulta en una gran biblioteca.
   2. La biblioteca ha cambiado y es necesario volver a compilar el programa.

------

1. **Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas dinámicas.**

Ventaja:

- Ahorra más memoria y reduce el intercambio de páginas.
- Los programas escritos en diferentes lenguajes de programación pueden llamar a la misma para que funcionen siempre que sigan la convención de llamada de función.
- Adecuado para el desarrollo de software a gran escala, lo que hace que el proceso de desarrollo sea independiente y menos acoplado, lo que es conveniente para el desarrollo y las pruebas entre diferentes desarrolladores y organizaciones de desarrollo.

Desventaja:

- El archivo ejecutable generado por el enlace estático es de gran tamaño y contiene el mismo código común, lo que causa desperdicio
- La aplicación que usa la biblioteca de enlaces dinámicos no es autónoma, y el módulo del que depende también debe existir. Si usa enlaces dinámicos al cargar, la DLL no existe cuando se inicia el programa. El sistema terminará el programa y dará un mensaje de error.

1. **Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo ejecutable para código fuente en C con make. Haz uso de un buildfile.**

   ```
   make
   
   gcc -O  -c  main.c
   gcc -O  -c  -fPIC  aritmetica.c
   gcc -O  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o
   gcc -O  -Wl,-rpath=/usr/local/lib  main.o  libaritmetica.so  -o  programa
   ```
