edge counter
============

..  code-block:: cpp

    edge_counter(name, pin, rising=true, falling=true);

Create a new input port for an edge_counter,
measuring either a falling or rising edge on the
respective input port.
name will be appended to the mqtt topic and
a trigger count will be published there.

Parameters
----------

- ``name``: the name it can be addressed via MQTT in the network. Inside the code
  it can be addressed via IN(name).

- ``pin``: the gpio pin

- ``rising``: if ``true``, count rising edges

- ``falling``: if ``true``, count falling edges

- ``.with_pullup(false)`` can be used to disable internal pullup (default enabled)

Example
-------

**node name:** ``living room/shock1``

..  code-block:: cpp

    edge_counter(left, D3);

Now, the number of rising and falling edges is published as 
``living room/shock1/left``