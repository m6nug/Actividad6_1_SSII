# Actividad6_1_SSII
*Manuel Gallego Bauer 1ºDAMP*
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
```
#!/bin/bash

if [ $# -eq 2 ]; then
    num1=$1
    num2=$2
    suma=$(expr $num1 + $num2)

    echo "La suma de $num1 y $num2 es $suma"
else
    echo "Error. El número de parámetros es incorrecto"

fi
```
---
### Ejercicio 7
```
#!/bin/bash

if [ $# -ne 3 ]; then
    echo "Error. Número incorrecto de parámetros"
    exit 1
fi

if ! [[ $1 =~ ^[0-9]+$ ]]; then
    echo "El primer parámetro no es un número"
    exit 1
fi

if ! [[ $2 =~ ^[0-9]+$ ]]; then
    echo "El segundo parámetro no es un número"
    exit 1
fi

case "$3" in
    "+")
        resultado=$(( $1 + $2 ))
        ;;
    "-")
        resultado=$(( $1 - $2 ))
        ;;
    "*")
        resultado=$(( $1 * $2 ))
        ;;
    "/")
        resultado=$(( $1 / $2 ))
        ;;
    *)
        echo "Se introdujo un operador inválido. Las opciones permitidas son +, -, +, /"
        exit 1
        ;;
esac
```
---
### Ejercicio 8
```
#!/bin/bash

if [ -e "$1" ]; then
    echo "El archivo $1 existe"
else
    echo "El archivo $1 no existe"
fi
```
---
### Ejercicio 9
```
#!/bin/bash

if [ -f "$1" ]; then
    echo "$1 es un archivo"
elif [ -d "$1" ]; then
    echo "$1 es un directorio"
else
    echo "$1 no es un archivo ni un directoio"
    exit 1
fi
```
---
### Ejercicio 10
```
#!/bin/bash

permisos=$(ls -l "$1" | grep -o "^.\{1\}.\{3\}.\{3\}")

if [ -z "$permisos" ]; then
    echo "No se pudo obtener información de permisos para $1"
    exit 1
fi

echo "Permisos para $1: "
echo "Lectura: $(echo $permisos | cut -c 2)"
echo "Escritura: $(echo $permisos | cut -c 3)"
echo "Ejecución: $(echo $permisos | cut -c 4)"
```
---
### Ejercicio 11
```
#!/bin/bash

for i in {1..50}
do
    echo "Hola"
done
```
