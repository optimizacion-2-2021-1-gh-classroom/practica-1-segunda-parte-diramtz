*******
Módulos
*******


vertex
================

La clase contiene un nombre, que es el que se utiliza para la creación de arcos y si es nodo origen o fin.

edge
================

La clase aro cuenta con los nombres de los nodos de inicio y fin de cada arco, su capacidad, un flujo y la dirección contraria de los arcos para crear la gráfica residual.

	
create_flow_network
===============

Esta clase tiene dos atributos:

- Vértices: Lista de todos los nodos que conforman la gráfica. Esta lista contiene objetos enteros, vinculando el nombre de un vértice a sus atributos de origen y fin.


- Red: Diccionario de datos que asigna el nombre de cada vértice a todos los bordes que salen del vértice correspondiente. 
       Simplemente haciendo que el nombre del vértice actúe como la clave del diccionario

En este módulo se encuentran la funciones que el usuario debe de ejecutar para poder solucionar el problema de flujo máximo.

La función `get_vertex` toma el nombre del nodo y lo encuentra en el conjunto de vértices en la red declarada. 

La función `create_vertex` agrega un nodo al grafo después de verificar varios casos de error para asegurarse de que se pueda agregar este nodo.
Posteriormente se agrega el nodo completo a la lista de nodos y agrega el nombre a una lista vacía de arcos con ayuda de la función add_edge (). 
Esta función  primero verifica que el nodo inicial y final estén en el grafo y que estén no el mismo vértice. 
Luego, crea el nuevo arco y su inverso con capacidad 0. Luego, agrega el nuevo borde al mapa de la red y finalmente agrega el arco inverso al mismo mapa.

La función `get_path` es una función recursiva que recorre la red comenzando en un nodo dado y calcula la capacidad residual para cada arco.
Esta capacidad residual se usa para decidir cuánto flujo enviar a lo largo de una ruta determinada en la siguiente función.
La ruta irá creciendo  hasta llegar al final de la red.

Y finalmente, la función `MaxFlow` es lo que llama a get_path con los parámetros correctos y suma el flujo máximo, primero encuentra el nodo origen y fin de la red. 
Calcula una ruta de aumento inicial y se continúa calculando el flujo mientras todavía hay una ruta. 
Si es que hay una ruta entonces hay una capacidad de aumento en cada arco de la ruta, por lo que se puede calcular un flujo. 
Ese flujo se suma a los arcos posteriores y se resta de los arcos inversos. Se vuelve a calcular otra ruta y se reanuda el proceso. 
Finalmente, se calcula el flujo total que sale del nodo origen porque esta es la cantidad exacta de flujo a través de toda la red.







