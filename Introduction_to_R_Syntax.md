# Introducción a la syntaxis de R

## Cálculos
Comencemos con la sintaxis básica para cálculos matemáticos en R. R realiza sumas, restas, multiplicaciones y divisiones con +, -, * y /:

- Results in "500"

573 - 74 + 1
 
- Results in "50"

25 * 2
 
- Results in "2"

10 / 5

Las operaciones matemáticas en R siguen el orden matemático estándar de operaciones. ¡Escribamos su primera línea de código R y calculemos algunas matemáticas básicas!

## Ejercicio

Calcule el resultado de esta ecuación: 25 * 4 + 9/3 en el bloque de código R de su cuaderno. Archivo RMD R-markdown. Antes de presionar Ejecutar, intente averiguar cuál sería la respuesta según el orden de las operaciones. ¡Tu respuesta debe coincidir con la salida!

## Código: 
```{r}
title: "Introduction to R Syntax"
output: html_notebook
25 * 4 + 9 / 3
```

## Comentarios
Irónicamente, lo segundo que vamos a hacer es mostrarle cómo decirle a R que ignore una parte de su programa. Prometemos que es muy útil saber cómo hacer esto. El texto escrito en un programa pero no ejecutado por la computadora se denomina comentario. R interpreta cualquier cosa después de un # como un comentario.
¿Por qué querría alguien que la computadora ignorara una parte de su archivo? ¡Varias razones! Los comentarios pueden:

- Proporcione el contexto de por qué algo está escrito como está:
```{r}    
# This code will be used to count the number of times anyone tweets the word
persnickety
persnickety_count <- 0
```
- Ayude a otras personas que lean el código a entenderlo más rápido:
```{r}
# This code will calculate the likelihood that it will rain tomorrow
complicated_rain_calculation_for_tomorrow()
```
- Ignore una línea de código y vea cómo se ejecutará un programa sin ella:
```{r}
# useful_value <- old_sloppy_code()
useful_value <- new_clean_code()
```
Anotar o documentar su código puede ayudar a otras personas a leer su programa más tarde. También podría ayudar a su yo futuro a comprender el código cuando vuelva atrás y lea un archivo antiguo tratando de recordar cómo funciona. Documentar su código ayudará a otros a reproducirlo y también lo ayudará a usted a convertirse en un mejor programador. Nota: En los cuadernos de R, también puede agregar documentación utilizando texto de rebajas fuera de los bloques de código.

## Ejercicio
Agregue un comentario dentro del bloque de código que explique que la línea de código dentro de notebook.Rmd está calculando el volumen en un cubo.

```{r}
title: "Introduction to R Syntax"
output: html_notebook
#En el siguiente codigo se realiza la multiplicacion de 3 numeros
3 * 3 * 3
```
## Tipos de datos
Ahora que sabe cómo calcular las matemáticas básicas y agregar comentarios que expliquen su código, profundicemos en cómo R "piensa" los diferentes tipos de datos. En R y en programación, los tipos de datos son las clasificaciones que damos a diferentes tipos de piezas de información. En esta lección, exploramos los siguientes tipos de datos R:

1.- Numérico: cualquier número con o sin punto decimal: 23, 0,03 y el valor nulo numérico NA.

2.- Carácter: cualquier agrupación de caracteres en su teclado (letras, números, espacios, símbolos, etc.) o texto. La mayoría de las cadenas están entre comillas simples: '...' o comillas dobles "...", aunque preferimos las comillas simples. A veces escuchará a este tipo referirse como "cadena".

3.- Lógico: este tipo de datos solo tiene dos valores posibles: VERDADERO o FALSO (sin comillas). Es útil pensar en los tipos lógicos o booleanos como interruptores de encendido y apagado o como respuestas a una pregunta de "sí" o "no".

4.- Vectores: una lista de datos relacionados que son todos del mismo tipo.

5.- NA: este tipo de datos representa la ausencia de un valor y está representado por la palabra clave NA (sin comillas) pero tiene su propio significado en el contexto de los diferentes tipos. Es decir, hay un NA numérico, un carácter NA y un NA lógico.

Vamos a familiarizarnos con comprobar el tipo de datos de lo siguiente:

class(2) # numeric
class('hello') # character
class('23') #character
class (FALSE) #logical
class(NA) #logical

En el ejemplo anterior, observe que la tercera línea está etiquetada como un tipo de carácter. ¿Por qué? Debido a que los caracteres 23 están entre comillas, se clasifica como un personaje.

Para imprimir un valor, debe poner el valor dentro de la siguiente sintaxis: print (). Imprime tu nombre como una cadena de caracteres.
Imprime tu edad como un tipo numérico.
En una nueva línea de código, escriba su edad como tipo de carácter.

## Código
```{r}
title: "Introduction to R Syntax"
output: html_notebook

print("Alberto Cabrera Lugo")
print(22)
print("22")
```
## Variables
Ahora que sabe cómo R clasifica algunos de los tipos de información básica, descubramos cómo almacenarlos. En programación, las variables nos permiten almacenar información y asociar esa información con un nombre. En R, asignamos variables usando el operador de asignación, un signo de flecha (<-) hecho con un quilate y un guión.

```{r}
full_name <-"Natalia Rodríguez Nuñez"
```
En el ejemplo anterior, almacenamos el valor de cadena “Natalia Rodríguez Nuñez” en una variable llamada full_name. Las variables no pueden tener espacios o símbolos en sus nombres que no sean un guión bajo (_). No pueden comenzar con números, pero pueden tener números después de la primera letra (por ejemplo, cool_variable_5 está bien).

No es una coincidencia que llamemos a estas criaturas "variables". Si necesitamos actualizar una variable pero realizar el mismo proceso lógico en ella, ¡podemos cambiar su valor! Por ejemplo, tome la variable message_string:

```{r}
# Greeting
message_string <- "Hello there"
print(message_string)

# Farewell
message_string <- "Hasta la vista"
print(message_string)
```
Arriba, creamos la variable message_string, asignamos un mensaje de bienvenida e imprimimos el saludo. Después de saludar al usuario, queremos despedirnos de él. Luego actualizamos message_string a un mensaje de salida y lo imprimimos.

- Nota: También puede usar = en lugar de <- para asignar un valor, pero los R-tists (programadores de R) prefieren hacerlo con una flecha.

## Ejercicio
Cree un nombre de variable con su nombre como una cadena.
Cree una edad variable con su edad como un número
```{r}
title: "Introduction to R Syntax"
output: html_notebook

name <- "Alberto Cabrera Lugo"
age <- 22
```
## Vectores
Mencionamos Vectores cuando presentamos los tipos de datos anteriormente. En R, los vectores son una estructura similar a una lista que contiene elementos del mismo tipo de datos.

Eche un vistazo aquí:

```{r}
spring_months <- c("March", "April","May","June")
```
En el ejemplo anterior, creamos una nueva variable con el valor de un nuevo vector. Creamos este vector separando cuatro cadenas de caracteres con una coma y envolviéndolas dentro de c ().

Algunas cosas que debe saber hacer con los vectores:

- Puede verificar el tipo de elementos en un vector usando typeof (vector_name)
- Puede verificar la longitud de un vector usando length (vector_name)
- Puede acceder a elementos individuales en el vector usando [] y colocando la posición del elemento dentro de los corchetes. Por ejemplo, si quisiéramos acceder al segundo elemento escribiríamos: vector_name [2]. Nota: En R, comienza a contar elementos en la posición uno, no en cero.

## Ejercicio
```{r}
title: "Introduction to R Syntax"
output: html_notebook

phone <- c(664,341,5867)
```
## Condicionales
En R, a menudo realizaremos una tarea basada en una condición. Por ejemplo, si estamos analizando datos para el verano, solo querremos ver los datos que caen en junio, julio y septiembre.

Podemos realizar una tarea basada en una condición usando una declaración if:

```{r}
if (TRUE) {
  print('This message will print!')
} 
```
Observe que en el ejemplo anterior tenemos una declaración if. La sentencia if se compone de:

- La palabra clave if seguida de un conjunto de paréntesis () seguida de un bloque de código, o declaración de bloque, indicado por un conjunto de llaves {}.
- Dentro de los paréntesis (), se proporciona una condición que se evalúa como VERDADERO o FALSO.
- Si la condición se evalúa como verdadera, el código dentro de las llaves {} se ejecuta o se ejecuta.
- Si la condición se evalúa como falsa, el código dentro del bloque no se ejecutará.

Saber cómo usar las declaraciones if le ayudará a introducir la lógica en su análisis de datos. También hay una forma de agregar una instrucción else. Una instrucción else debe combinar con una instrucción if, y juntas se denominan instrucción if ... else.

```{r}
if (TRUE) {
   print("Go to sleep!")
} else {
   print("Wake up!")
}

```
En el ejemplo anterior, la declaración else:

- Utiliza la palabra clave else que sigue al bloque de código de una instrucción if.
- Tiene un bloque de código que está envuelto por un conjunto de llaves {}.
- El código dentro del bloque de código de la instrucción else se ejecutará cuando la condición de la instrucción if se evalúe como falsa. Estas declaraciones if ... else nos permiten automatizar soluciones a preguntas de sí o no, también conocidas como decisiones binarias.

## Ejercicio
Cree una declaración condicional en notebook.Rmd de modo que cambie el valor del mensaje de la variable a '¡Ejecuto esto cuando sea cierto!' cuando la condición es VERDADERA, y el valor del mensaje es '¡Ejecuto esto cuando es falso!' cuando es FALSO.
```{r}
title: "Introduction to R Syntax"
output: html_notebook

message <- "I change based on a condition."
if(TRUE){
 message <- "I execute this when true!"
}else{
  message <- "I execute this when false!"
}

print(message)
```

