# Algoritmos y pseudocódigos
## Ejemplos matemáticos presentados en diagramas de flujo y pseudocódigos

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


	
