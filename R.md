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
