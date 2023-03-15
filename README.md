# Actividad6_1_SSII
> Manuel Gallego Bauer 1ºDAMP
---
### Ejercicio 1
```
#!/bin/bash

echo "Introduce un número: "
read num

if [ $num -gt 0 ]; then
    echo "El número $num es positivo"
else
    echo "El número $num no es positivo"
fi
```
---
### Ejercicio 2
```
#!/bin/bash

echo "Introduce un número: "
read num

if [ $num -lt 0 ]; then
    echo "El número $num es negativo"
else
    echo "El número $num no es negativo"
fi
```
---
### Ejercicio 3
```
#!/bin/bash

echo "Introduce un número: "
read num

if [ $num -eq 0 ]; then
    echo "El número $num es 0"
else
    echo "El número $num no es 0"
fi
```
---
### Ejercicio 4
```
#!/bin/bash

echo "Introduce un número: "
read num

if [ $num -gt 0 ]; then
    echo "El número $num es positivo"
elif [ $num -lt 0 ]; then
    echo "El número $num es negativo"
elif [ $num -eq 0 ]; then
    echo "El número $num es 0"
fi
```
---
### Ejercicio 5
```
#!/bin/bash

if [ $# -ne 3 ]; then
    echo "Error. El número de parámetros es distinto de 3"

fi
```
---
### Ejercicio 6
