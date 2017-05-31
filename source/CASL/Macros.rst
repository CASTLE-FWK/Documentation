Macros
-------

CASL contains several useful macros for essential simulation function. The most important ones are ``POPULATE`` and

POPULATE
^^^^^^^^^
The ``POPULATE`` macro allows SYSTEMS, ENVIRONMENTS, and GROUPS to create populations of entities. It takes the form of::

	CASL.POPULATE[theLayoutVariable](layoutInitializationParameters)[aRange,theTypeOfEntityToBePopulated](entityInitializationParameters);

An example of populating ``Cells`` into a ``CellCity`` where the layout variable is called ``cellGrid`` ::
	
	CASL.POPULATE[cellGrid](SYSTEM.sizeOfGrid)[SYSTEM.numberOfCells, AGENT.Cell](self);
