
*********
Funciones:
*********

Aquí se muestra paso a paso las funciones que debes de declarar para obtener el glujo máximo del problema.

Declarar red
=============

.. autosummary::
   :toctree: _autosummary
    G = create_flow_network()

Declarar un nodo:
================

Deberás declarar esta función tantos nodos tenga tu red

.. autosummary::
   :toctree: _autosummary
    # Si es el nodo origen: 
    G.create_vertex('nombre del nodo', True, False)
   
    # Si es nodo final
    G.create_vertex('nombre del nodo', False, True)

    # Otro nodo
    G.create_vertex('nombre del nodo', False False)


Declarar un arco:
=================

Deberás declarar esta fucnión tantos arcos tenga tu red

.. autosummary::
   :toctree: _autosummary
    G.create_edge('inicio arco', 'fin arco', capacidad)


Flujo máximo:
=============
Esta función es nuestra función final. Una vez declarados los nodos y arcos, así como sus respectivas capacidades ejecuta la siguiente función para obtener el flujo máximo.

.. autosummary::
   :toctree: _autosummary
    G.MaxFlow()

Otras funciones:
================

Si deseas corroborar el nombre de tus vértices ejecuta lo siguiente:

.. autosummary::
   :toctree: _autosummary
    [vertex.name for vertex in fn.vertices]

Si deseas corroborar los arcos ejecuta lo siguiente:

.. autosummary::
   :toctree: _autosummary
    # NOTA: Esta función imprime los arcos tanto de ida como los de regreso
    ['%s -> %s' % (e.start, e.end) for e in fn.get_edges()]


