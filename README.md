# Actvidades Git 2

## 1- Vemos nuestro repositorio y empezamos a etiquetar nuestros commits. 

El primer commit será v1 y el tercero el v2.    
  
El segundo no será etiquetado

<img width="674" alt="Captura de pantalla 2022-11-30 a las 17 27 14" src="https://user-images.githubusercontent.com/87373226/204853539-b23a032e-ff23-42c4-8b71-2620c336335d.png">

Para etiquetar utilizamos el comando:

~~~ 
git  tag  -a  nombre_etiqueta  -m  "Mensaje"   commit_a_etiquetar 
~~~

En mi caso:

~~~
git tag -a v1 -m "Version 1" 29eb
git tag -a v2 -m "Version 2" bbf9
~~~

<img width="746" alt="Captura de pantalla 2022-11-30 a las 17 45 00" src="https://user-images.githubusercontent.com/87373226/204857475-9744e2cc-556c-44ed-b662-ccf959eb4f9c.png">
<img width="689" alt="Captura de pantalla 2022-11-30 a las 17 45 16" src="https://user-images.githubusercontent.com/87373226/204857529-f62ae75e-37fb-4ca5-8d4b-ed66f7323b1a.png">

Si por cualquier caso nos llegamos a equivocar con la etiqueta podemos eliminarla y volver a colocarla corregida con: 

~~~
git tag -d v2
git tag -a v2 -m "Version 2" bbf9
~~~

<img width="608" alt="Captura de pantalla 2022-11-30 a las 17 48 38" src="https://user-images.githubusercontent.com/87373226/204858300-c4a33404-2260-48db-a73b-0e77d6424795.png">

## 2- Usamos las etiquetas para movernos

Antes para movernos entre commits usabamos:

~~~
git chekout 29eb
~~~

Ahora podemos movernos con las etiquetas y volvemos al commit actual:

~~~
git checkout v1
git checkout main
~~~

<img width="564" alt="Captura de pantalla 2022-11-30 a las 17 55 20" src="https://user-images.githubusercontent.com/87373226/204859783-3cb0ab2c-18ce-48e5-8692-ece98fbfcf99.png">

## 3- Examinamos cambios de los commits respecto al anterior

Para ver los cambios de los commits respecto al anterior se usa :

~~~
git show
~~~

<img width="699" alt="Captura de pantalla 2022-11-30 a las 17 59 02" src="https://user-images.githubusercontent.com/87373226/204860603-391aa1b4-d829-40b5-ae42-94b7b397940f.png">

Como se puede ver, se añadio el nombre del centro al readme.

Para ver los cambios del segundo respecto al primero :

~~~
git show 04b7
~~~
<img width="746" alt="Captura de pantalla 2022-11-30 a las 18 02 26" src="https://user-images.githubusercontent.com/87373226/204861278-68734782-8098-4ca5-9655-62b638f144b9.png">

Y para ver los cambios del primer commit respecto al repositorio vacio :

~~~
git show v1
~~~

<img width="628" alt="Captura de pantalla 2022-11-30 a las 18 02 46" src="https://user-images.githubusercontent.com/87373226/204861383-fbe6d703-6509-42b9-b1ee-dc8eee922f8c.png">

## 4- Examinando cambios de un commit respecto a varios anteriores

Para ver los cambios a lo largo de varios commits se usa:

~~~ 
git  diff  commit1..commit2
~~~

En mi caso para ver los cambios entre el primero y el ultimo commit :

~~~
git  diff  v1..v2
~~~

<img width="390" alt="Captura de pantalla 2022-11-30 a las 18 05 44" src="https://user-images.githubusercontent.com/87373226/204862021-186f1a71-369d-4394-963c-4a41a2f40c68.png">

## 5- Diferencias entre git show y git diff

Si hacemos :

~~~
git show v1..v2
~~~

<img width="690" alt="Captura de pantalla 2022-11-30 a las 18 07 51" src="https://user-images.githubusercontent.com/87373226/204862468-8575a0df-5f7a-4343-87d5-cf6bb3b4160c.png">

Como vemos nos muestra los cambios respecto a los anteriores del tercer y segundo commit. Es a decir no vemos las diferencias entre el v1 y el v2, vemos las respecto al anterior entre el v1 y el v2 sin incluir el v1.
