
*********
Funciones
*********

Aquí se muestra paso a paso las funciones que debed de declarar para obtener el flujo máximo del problema.

Declarar red
=============

.. code-block:: bash

    G = create_flow_network()

Declarar un nodo:
================

Deberás declarar esta función tantos nodos tenga tu red

.. code-block:: bash

    # Si es el nodo origen: 
    G.create_vertex('nombre del nodo', True, False)
   
    # Si es nodo final
    G.create_vertex('nombre del nodo', False, True)

    # Otro nodo
    G.create_vertex('nombre del nodo', False False)


Declarar un arco:
=================

Deberás declarar esta fucnión tantos arcos tenga tu red

.. code-block:: bash

    G.create_edge('inicio arco', 'fin arco', capacidad)


Flujo máximo:
=============
Esta función es nuestra función final. Una vez declarados los nodos y arcos, así como sus respectivas capacidades ejecuta la siguiente función para obtener el flujo máximo.

.. code-block:: bash

    G.MaxFlow()

Otras funciones:
================

Si deseas corroborar el nombre de tus vértices ejecuta lo siguiente:

.. code-block:: bash

    [vertex.name for vertex in fn.vertices]

Si deseas corroborar los arcos ejecuta lo siguiente:

.. code-block:: bash

    ['%s -> %s' % (e.start, e.end) for e in fn.get_edges()]


 # NOTA: Esta función imprime los arcos tanto de ida como los de regreso
