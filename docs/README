### Algoritmo Ford Fulkerson.

**Flujo Máximo**

El algoritmo de Ford-Fulkerson propone buscar caminos en los que se pueda aumentar el flujo, hasta que se alcance el flujo máximo. Es aplicable a los Flujos maximales. La idea e$

Sea G(V,E) un grafo, con V vértices, E aristas y donde por cada arista (u,v), tenemos una capacidad c(u,v) y un flujo f(u,v). Se busca maximizar el valor del flujo desde una fue$

El método inicia con f(u,v)=0 para toda (u,v) en V. En cada iteración, se incrementa el flujo en G mediante el resultado de una búsqueda de un **camino de aumento** en una **red$

El flujo a aumentar se debe considerar legal, es decir:

    El flujo de para toda arista (u,v) no debe ser mayor que la capacidad de dicha arista.
    El flujo que sale de la fuente s debe ser igual al que llega al sumidero t.

*Nota: En una red con fuente s y sumidero t único el valor máximo que puede tomar un flujo variable es igual a la capacidad mínima que puede tomar un corte.*

**Red residual**

Definimos una red residual $G_{f}(V,E)$ como la red donde la capacidad de cada una de las aristas se define como $c_{f}(u,v) = c(u,v) − f(u,v)$ , donde c(u,v) es la capacidad de$

Intuitivamente, dado el grafo G y un camino de aumento $c_{F}$ , la red residual $G_{f}$ consiste en el grafo que representa el como cambia la capacidad de cada una de las arist$

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
