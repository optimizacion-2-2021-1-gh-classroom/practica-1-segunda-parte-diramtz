**Equipo 2**
# Práctica 1 
### Segunda Parte

| Integrante | User | Tarea |
|---------------|-------|---------|
| Ana | @AnaTorresR | Documentación y uso de paquetes |
| Dira | @diramtz | Documentación y uso de paquetes |
| Iván | @IvanSalgadoVel |  Documentación y uso de paquetes y Project manager |


### Algoritmo Ford Fulkerson. 
#### Flujo Máximo 

El algoritmo de Ford-Fulkerson propone buscar caminos en los que se pueda aumentar el flujo, hasta que se alcance el flujo máximo. Es aplicable a los Flujos maximales. La idea es encontrar una ruta con un flujo positivo neto que una los nodos origen y destino. Su nombre viene dado por sus creadores, L. R. Ford, Jr. y D. R. Fulkerson. 

Sea G(V,E) un grafo, con V vértices, E aristas y donde por cada arista (u,v), tenemos una capacidad c(u,v) y un flujo f(u,v). Se busca maximizar el valor del flujo desde una fuente s hasta un sumidero t.

El método inicia con f(u,v)=0 para toda (u,v) en V. En cada iteración, se incrementa el flujo en G mediante el resultado de una búsqueda de un **camino de aumento** en una **red residual**  $G_f$. Aunque cada iteración del método Ford-Fulkerson aumenta el valor del flujo. En cada iteración el flujo se aumentará hasta que la red $G_{f}$ no tenga más caminos de aumento.

El flujo a aumentar se debe considerar legal, es decir:

    El flujo de para toda arista (u,v) no debe ser mayor que la capacidad de dicha arista.
    El flujo que sale de la fuente s debe ser igual al que llega al sumidero t.
    
*Nota: En una red con fuente s y sumidero t único el valor máximo que puede tomar un flujo variable es igual a la capacidad mínima que puede tomar un corte.*

**Red residual**

Definimos una red residual $G_{f}(V,E)$ como la red donde la capacidad de cada una de las aristas se define como $c_{f}(u,v) = c(u,v) − f(u,v)$ , donde c(u,v) es la capacidad de la arista y el flujo f(u,v) es el flujo de la arista (u,v) en el camino de aumento seleccionado.

Intuitivamente, dado el grafo G y un camino de aumento $c_{F}$ , la red residual $G_{f}$ consiste en el grafo que representa el como cambia la capacidad de cada una de las aristas con respecto al flujo del camino de aumento $c_{F}$ en el grafo G.

**Caminos de aumento**

Un camino de aumento es un camino dirigido de la fuente s al sumidero t en $G_{f}$, donde la capacidad del camino de aumento es el mínimo de las capacidades de sus aristas. 


**Pseudocódigo**
                        
    Ford-Fulkerson(G,s,t) { 
    Gf = Crear_grafo_residual(G);
    for (cada arista (u,v) de E) { 
        f[u,v]= 0;
    } 
    while (exista un camino p desde s a t en la red residual Gf) { 
        cf(p) = min{cf(u,v): (u,v) está sobre p};
        for (cada arista (u,v) en p) { 
            f[u,v]= f[u,v] + cf(p); 
            f[v,u]= f[v,u] - cf(p); 
        }
        Actualizar_grafo_residual(Gf);
    } 
    
  }


Prueba nuestro paquete dando click en el botón de Binder [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/optimizacion-2-2021-1-gh-classroom/practica-1-segunda-parte-diramtz/main). Puedes jugar con el notebook `prueba_paquete.ipynb`


Si deseas consultar la documentación de nuestro paquete **ffmaxflow**
da click [aquí](https://optimizacion-2-2021-1-gh-classroom.github.io/practica-1-segunda-parte-diramtz/) 
 
**Docker** 

Para correr nuestra imagen de docker sigue las instrucciones que se encuentran en la carpeta [dockerfiles](https://github.com/optimizacion-2-2021-1-gh-classroom/practica-1-segunda-parte-diramtz/tree/main/dockerfiles)



**Referencias**

[Algoritmo Ford Fulkerson](https://es.wikipedia.org/wiki/Algoritmo_de_Ford-Fulkerson)

[Libro optimización nota 4.2](https://itam-ds.github.io/analisis-numerico-computo-cientifico/IV.optimizacion_en_redes_y_prog_lineal/4.1/Definiciones_generales_de_flujo_en_redes.html)

[Ford Fulkerson Python](https://www.geeksforgeeks.org/ford-fulkerson-algorithm-for-maximum-flow-problem/)

[Sphinx](https://www.youtube.com/feed/history)

[example-python-package-and-sphinx-doc](https://github.com/palmoreck/example-python-package-and-sphinx-doc)
