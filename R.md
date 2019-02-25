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
