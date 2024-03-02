# Algoritmos y pseudocódigos
## Procedimientos matemáticos presentados en diagramas de flujo y pseudocódigos

### Determinación de números primos hasta n
#### Diagrama de flujo (secuencia del algoritmo)
```mermaid
flowchart TD;
    A(Números primos hasta n)-->B[Crear una lista de números naturales desde 2 hasta n];
    B --> C;
    C[Para cada n_i de la lista se crea una sublista de divisores desde 2 hasta la raíz de n_i +1];
    C-->D;
    D[Dividir n_i/i];
    D-->E;
    E{el residuo de n_i/i es cero?} -- Sí --> F[i es divisor];
    E -- No --> G[i no es divisor];
    H[i=i+1] --> I{i menor a n_i?};
    G --> H;
    F --> H;
    I -- Sí --> E;
    I -- No --> J{n_i tiene divisores diferentes a n_i?};
    J -- Sí --> K[n_i no es primo];
    J -- No --> L[n_i es primo];
    K-->M;
    L -->M;
    M{n_i es menor a n?};
    M -- No --> N(Fin);
    M -- Sí --> J;
```
#### Pseudocódigo

```pseudocode
[variables]
n : entero
i : entero
n_i : entero

inicio
i:=2
 mientras (i<n) hacer
  si modulo (n.i) == 0
   escribir ('i es divisor de n_i')
  si no
   escribir ('i no es divisor de n_i')
 Fin mientras
 
crear lista para  cada n_i []
para cada i que cumple la condición de ser divisor ()
agregar a la lista (i)

 mientras (n_i< n) hacer
  si lista n_i contiene más de un elemento
   escribir ('n_i no es un número primo')
  si no
   escribir ('n_i es un número primo')
 Fin mientras
Fin 
```
### Hallar raíz cuadrada de un número
```mermaid
flowchart TD;
    A(Raíz cuadrada de un número)-->B[Dividir el número en pares de dígitos];
    B --> C;
    C[Para el par de dígitos que se encuentre más hacia la izquierda, buscar un x tal que su multiplicación por sí mismo sea menor o igual que el primer par de dígitos];
    C-->D
    D{x^2 es menor o igual al par de dígitos?} -- Sí --> E[Restar el x^2 al par de dígitos];
    D -- No --> F[Buscar un x más pequeño];
    E-->G;
    F -->E 
    G[Bajar los siguientes pares de dígitos y tomar en cuenta los dos primero dígitos del residuo de la resta]
    G -->H 
    H[Dividirlos entre el doble de x];
    H--> I[Tomar en cuenta la parte entera del cociente de la división];
    I-->J[Tomar esta como último dígito del doble de x, x con la introducción de un dígito entero n = r];
    J-->K[Hacer el producto entre r y la parte entera de la anterior división];
    K -->L{ el resultado es menor o igual al residuo total de la resta previa?} -- Sí --> M[Tomar en cuenta la parte entera de la divisón];
    L--No -->N[Buscar un dígito n que satisfaga la desigualdad];
    M -->O[Poner el dígito n junto a x];
    N --> M 
    O -->P[Restar el producto de r y la parte entera al residuo de la resta previa];
    P --> Q
    Q{el resultado de la resta es 0?} -- Sí --> R[La raíz cuadrada es x con el dígito n puesto en la derecha]
    Q -- No --> S[Agregar dos dígitos 0 al resultado de la última resta, .00 al número que queremos hallarle la raíz cuadrada y . a x con el dígito n];
    S --> T[Buscar el doble de x con el dígito n];
    T--> I 
    R --> U(Fin)
```
#### Pseudocódigo

```pseudocode
[variables]
x : entero
n : entero
r : entero
y : real
t : entero

inicio
crear lista de pares de dígitos.i []
crear lista de 0 a 9.x []
para cada i:
 mientras (i<= x^2) hacer
  i-x^2
 si no
   probar con un x menor de la lista
 Fin mientras
Tomar los dos primeros dígitos de la resta = s	
y = s/2*x
Tomar los dígitos enteros de y y ponerlos en la parte derecha de x = r
r*parte entera de y = t
 mientras (t<=(i-x^2)) hacer
  Tomar la parte entera de y 
 sino
    Buscar un n tal que cumpla la desigualdad
 Fin mientras
Poner el dígito n junto a x = a
(i-x^2)-t
 mientras (i-x^2)-t = 0 hacer
   raizcuadrada del numero = a
 sino
   resultado de (i-x^2)-t agregarle dos cifras decimales (00), .00 al número que queremos hallarle la raíz cuadrada y . a a
 Fin mientras
Fin 


