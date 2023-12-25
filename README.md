# Actividad Bash
*Manuel Gallego Bauer 1ºDAMP*
---
### Ejercicio 1
```bash
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
```bash
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
```bash
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
```bash
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
```bash
#!/bin/bash

if [ $# -ne 3 ]; then
    echo "Error. El número de parámetros es distinto de 3"

fi
```
---
### Ejercicio 6
```bash
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
```bash
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
```bash
#!/bin/bash

if [ -e "$1" ]; then
    echo "El archivo $1 existe"
else
    echo "El archivo $1 no existe"
fi
```
---
### Ejercicio 9
```bash
#!/bin/bash

if [ -f "$1" ]; then
    echo "$1 es un archivo"
elif [ -d "$1" ]; then
    echo "$1 es un directorio"
else
    echo "$1 no es un archivo ni un directorio"
    exit 1
fi
```
---
### Ejercicio 10
```bash
#!/bin/bash

permisos=$(ls -l "$1" | grep -o "^.\{1\}.\{3\}.\{3\}")

if [ -z "$permisos" ]; then
    echo "No hay información de permisos de $1"
    exit 1
fi

echo "Permisos de $1: "
echo "Lectura: $(echo $permisos | cut -c 2)"
echo "Escritura: $(echo $permisos | cut -c 3)"
echo "Ejecución: $(echo $permisos | cut -c 4)"
```
---
### Ejercicio 11
```bash
#!/bin/bash

for i in {1..50}
do
    echo "Hola"
done
```
---
### Ejercicio 12
```bash
#!/bin/bash

    echo "Introduce una palabra: "
    read palabra
for i in {1..10}
do
    echo "La palabra introducida es: $palabra"
done
```
---
### Ejercicio 13
```bash
#!/bin/bash

num_veces=$1

for i in $(seq 1 $num_veces)
do
    echo "Hola"
done
```
---
### Ejercicio 14
```bash
#!/bin/bash

n=$1

for ((i=0; i<=n; i++))
do
    echo $i
done
```
---
### Ejercicio 15
```bash
#!/bin/bash

n=$1
suma=0

for ((i=1; i<=n; i++))
do
    suma=$((suma+i))
done

echo "La suma de los números del 1 al $n es: $suma"
```
---
### Ejercicio 16
```bash
#!/bin/bash

$temp=$1
$1=$2
$2=$temp

echo "El primer parámetro es $1 y el segundo es $2"
```
---
### Ejercicio 17
```bash
#!/bin/bash

while true; do
    read -p "Introduce una palabra: " palabra
    if [ "$palabra" == ":q" ]; then
        break
    fi
    echo "La palabra introducida es: $palabra"
done
```
---
### Ejercicio 18
```bash
#!/bin/bash

while true
do
    read palabra
    if [ "$palabra" == ":q" ]
    then
        break
    else
        echo "$palabra" >> palabras.txt
    fi
done
```
---
### Ejercicio 19
```bash
#!/bin/bash

archivo="palabras2.txt"

while true; do
    read palabra

    if [[ "$palabra" == ":q" ]]; then
        break
    fi

    echo "$palabra" >> "$archivo"

    sort -o "$archivo" "$archivo"
done

cat "$archivo"
```
---
### Ejercicio 20
```bash
#!/bin/bash

echo "Introduce un número: "
read num

if grep -wq "$num" numeros.txt
then
    echo "El número $num está en el archivo numeros.txt"
else
    echo "El número $num no está en el archivo numeros.txt"
fi
