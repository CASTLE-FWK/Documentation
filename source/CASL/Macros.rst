Macros
-------

CASL contains several useful macros for essential simulation function. The most important ones are ``POPULATE`` and

POPULATE
^^^^^^^^^
The ``POPULATE`` macro allows SYSTEMS, ENVIRONMENTS, and GROUPS to create populations of entities. It takes the form of::

	CASL.POPULATE[theLayoutVariable](layoutInitializationParameters)[aRange,theTypeOfEntityToBePopulated](entityInitializationParameters);

An example of populating ``Cells`` into a ``CellCity`` where the layout variable is called ``cellGrid`` ::
	
	CASL.POPULATE[cellGrid](SYSTEM.sizeOfGrid)[SYSTEM.numberOfCells, AGENT.Cell](self);

For each Entity type, you are required to execute one ``POPULATE`` per type.


LOGGER
^^^^^^^
In the ``initialize`` function for the ``SYSTEM``, you can define how logging will work across the model. The ``LOGGER`` macro takes the form of::

	CASL.LOGGER(mute, toConsole, toFile, ["filePath"]);

An example of configuring the CASL Logger to only send to the console::
	
	CASL.LOGGER(false, true, false);

An example of configuring the CASL Logger to send to both the console and a file::

	CASL.logger(false, true, true "/users/aUser/simulations/output.txt");

To send data to the Logger, in any function or feature simply::
	
	//Body of feature
	CASL.LOG("information to log");

METRIC
^^^^^^^
The ``METRIC`` macro turns on tracking of that particular feature. To use this, simply::

	CASL.METRIC[true]

You can also send further information to be tracked::

	CASL.METRIC[true](agentState, "aString");