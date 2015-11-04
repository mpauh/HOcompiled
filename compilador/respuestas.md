Ejercicio compilador:

1. Escriban qué esperan de cada uno de los pasos
1)make preprocessing:
Se encarga de las directiva como los includes y las macros creando calculator.pp.c
Usamos -E para deternos en esta etapa
gcc -E calculator.c -o calculator.pp.c
2)make assembler:
Es el trabajo mas pesado de los desarrolladores desde el codigo c y genera optimizaciones de hadware creando calculator.asm. 
Usamos -S para deternenos en esta estapa.
gcc -masm=intel -S calculator.c -o calculator.asm  
3)make object:
Pasamos del codigo assembler al codigo de la maquina con un compilador que genera un objeto binario calculator.o.
Usamos -c para deternos en esta etapa.
gcc -c calculator.c -o calculator.o
4)make executable:
Esta linkeando desde el objeto binario para crear el ejecutable calculator.e
gcc calculator.o -o calculator.e

2. ¿Qué agregó el preprocesador?
Agrega las definiciones de las funciones y se crea calculator.pp.c

3. Identificar en la rutina de assembler las funciones
Las funciones definidas son main y add_numbers y dentro de main se llama a las funciones add_numbers y printf

4. Explicar qué quieren decir los símbolos que se crean en el objeto
Son los nombres de las funciones

5. ¿En qué se diferencian los símbolos del objeto y del ejecutable?
En el objeto me pueden aparecer los descriptores undefine para los simbolos no definidos, mientras que en el ejecutable aparecen todos los simbolos necesarios para poder ejecutar las funciones, en el caso de librerias dinamicas, aparece el undefine en el descriptor y el linkeo de la libreria en el simbolo. 
