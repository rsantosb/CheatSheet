# CheatSheet R Cmds
Repositorio con comandos de ayuda: R

---
*Participante:* Rocío Santos

---
# Dataframes:
## Básicos:

- print(df) : Muestra la tabla
- plot(df) : Representa gráficamente la tabla
- str(df) : Representa el objeto
- summary(df): Resumen estadístico por columnas
- ?NameFunction : Muestra ayuda de la función

- dim(df) : Rows x cols
- nrows(df) : Number of rows
- ncols(df) : Number of cols
- colnames(df) : Nombre cols

- head(df, n = ...) : Primeras n filas 
- tail(df, n = ...) : Últimas n filas

## Selección filas y columnas:
- df[1:10, ] : 10 primeras filas
- df[ , 3:4] : Columnas 3 y 4
- df[ , 'NameCol' ] = df$NameCol : Seleccionar columna 'NameCol'
- df[ condicionesLógicas ,] : Permite seleccionar filas mediante condiciones

   Ejemplo: mtcars[mtcars$cyl<6 & mtcars$gear==4,]

## Creación y eliminación tablas:

   Ejercicio: Crea una copia del conjunto de datos airquality. Comprueba con ls que está efectivamente creado y luego añádele una
   columna nueva llamada temperatura que contenga una copia de Temp. Comprueba que efectivamente está allí y luego, elimínala.
   Finalmente, borra la tabla.
   
1.   Crear tabla
      
      copyAir <- airquality
2.   Lista objetos en memoria

      ls()                                   
3.   Crear una nueva columna, copiando Temp

      copyAir$Temperatura <- copyAir$Temp
   
4.   Mostrar info de la tabla

      head(copyAir)                          

5.   Eliminar columna

      copyAir$Temperatura <- NULL           
6.   Elimimar la tabla

      rm(copyAir)                           

## Directorios:
- getwd()       : Ruta del directorio actual
- setwd("ruta") : Cambiar directorio actual a ruta
- dir()         : Lista el contenido del directorio 
- read.table( url, header = , sep = "") : Lee un fichero y crea dataframe

   También existe read.csv() o download.file()
 
---
# Gráficos:
### Variables continuas: Histograma

	hist(miair$Temp, main = "NY TEMP", xlab = "Grados", ylab = "Frecuencia", col = "steelblue")

### Variables categóricas: Barras

	barplot(table(iris$Species), main = "", xlab = "", ylab = "", col = "", horiz = TRUE)

	barplot(VADeaths[, 2], xlab = "tramos de edad", ylab = "tasa de mortalidad",
        main = "Tasa de mortalidad en Virginia\nmujer/rural")

### Relación entre 2 variables continuas: Gráficos de dispersión

	plot(cars$speed, cars$dist) :  muestra cómo aumenta dist en función de speed
	
	plot(airquality$Temp, type = "l") : usar líneas para unir los puntos de un diagrama de dispersión

	par(lty = , lwd = , & more options)
   
	// Composición de elementos gráficos
      plot(airquality$Temp)  : Puntos de la temperatura
      lines(airquality$Temp) : Unir puntos con lineas
      abline(h = mean(airquality$Temp), col = "red") : Pintar una línea horizontal roja a la altura de la temperatura media
      
   	  h = LINEA HORIZONTAL , v = LINEA VERTICAL
	

### Relación entre variable continua y variable categórica: Diagramas de caja

	boxplot(iris$Sepal.Width ~ iris$Species, col = "gray", main = "Especies de iris según la anchura del sépalo")
		
	y ~ x : Hacer algo en Y en funcion de X
	
---
COLORES = http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf

GUIDE   = http://rstudio-pubs-static.s3.amazonaws.com/7953_4e3efd5b9415444ca065b1167862c349.html

---
# Vectores:

## Creación:

- x <- 1:10			: Vector con valores 1..10
- y <- iris$Species : Vector con datos de la columna iris$Species

- ls() : List objects
- c()  : Combine values into a vector or list

- seq(1,4) = 1:4
- rep(1:4, n) 		 : Repetir secuencia n veces
	>  [1] 1 2 3 4 1 2 3 4 1 2 3 4 1 2 3 4
	
- rep(1:4, each = n) : Repetir la secuencia, cada uno n veces
	>  [1]  1 1 2 2 3 3 4 4
	
	igual a : rep(1:4, c(2,2,2,2))
	
- seq(from=1, to=2, by = 0.1) : Creando patrón de 1:2 con diferencia 0.1 por valor

- rep(1:4, times = 4:1)
	>  [1] 1 1 1 1 2 2 2 3 3 4

- rep(1:4, each = 2, len = 4) : Representa serie 1:4, cada uno 2 veces, hasta long 4 vector
	>  [1] 1 1 2 2 
	
- rep(1:4, each = 2, len = 10) : Representa serie 1:4, cada uno 2 veces, hasta long 10 vector
	>  [1] 1 1 2 2 3 3 4 4 1 1
 
- rep(1:4, each = 2, times = 3)
	>  [1] 1 1 2 2 3 3 4 4 1 1 2 2 3 3 4 4 1 1 2 2 3 3 4 4

## Inspección:

- plot(x)		  : Generic XY funcion for plotting
- length(x)		  : Long de vector
- table(y)		  : Cuenta los elementos de un vector por valor
- summary(y)	  : Resumen del contenido de un vector
- table(table(x)) : Resumen del contenido de table(x)

Dado x = 1:10
- x[(1:2)]		: 1 2 
- x[-(1:2)]		: 3:10
- x[x < 4]		: 1:3
- x[-length(x)]	: 10
- x[-length(x)]	: x sin length(x)
- x[1:(length(x)-2)] : Todos los valores de x menos los dos últimos
