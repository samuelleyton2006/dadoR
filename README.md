# Ejercicio dado y probabilídad modificada 

### Documentacion del programa previa 
  Requerimiento de :

- [x] Dar un numero al azar a partir de que exista la variable global y que se verifique apartir del ¨ if ¨
- [ ] A partir de la pila agregar de manera unica y recursiva el hecho de que se guarden los valores en la pila
- [ ] Sacar un promedio apartir de la funcion y que lo haga de manera recursiva en cada instancia
- [ ] testear a partir de las primeras 10 muestras el correcto funcionamiento de la modificacion en la probabilidad de numeros en el programa
- [ ] poder modificar el tamaño del arreglo para que puedan entrar mas numeros en el arreglo




``` R
  # Inicializar lista de lanzamientos en el entorno global
if (!exists("lanzamientos", envir = .GlobalEnv)) {
  lanzamientos <<- c()
}

# Probabilidades personalizadas (ajusta estos valores si lo deseas)
probabilidades <- c(0.1, 0.2, 0.2, 0.2, 0.2, 0.1)  # La suma debe ser 1

# Función para lanzar el dado
lanzar_dado <- function() {
  # Generar un número con las probabilidades definidas
  resultado <- sample(1:6, 1, prob = probabilidades)
  
  # Agregar el resultado a la lista de lanzamientos
  lanzamientos <<- c(lanzamientos, resultado)
  
  # Mantener solo los últimos 20 lanzamientos
  if (length(lanzamientos) > 50) {
    lanzamientos <<- tail(lanzamientos, 50)
  }
  
  # Imprimir el número actual
  cat(resultado, "\n\n")  # Doble salto de línea
  
  # Imprimir los últimos 20 lanzamientos en orden descendente
  cat(rev(lanzamientos), "\n")
}

# Probar la función varias veces para llenar la lista
for (i in 1:55) {
  lanzar_dado()
}


```
