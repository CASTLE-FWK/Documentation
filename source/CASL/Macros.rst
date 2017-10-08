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

	CASL.LOGGER(mute, toConsole, toFile, ["filePath"], infoToFile, infoToConsole, infoToDB);

An example of configuring the CASL Logger to only send to the console::
	
	CASL.LOGGER(false, true, false, false, false, false);

An example of configuring the CASL Logger to send to both the console and a file::

	CASL.logger(false, true, true "/users/aUser/simulations/output.txt", false, false, false);

An example of configuring the CASL logger and execution data writer for data farming (that is send all execution information to the data base while maintaining console printing of explcit logs)::

	CASL.logger(false, true, false, "", false, false, true);

To send data to the Logger, in any function or feature simply::
	
	CASL.LOG("information to log");
	CASL.LOG("the state: "+FUNCTION.getState());

METRIC
^^^^^^^
The ``METRIC`` macro turns on tracking of that particular feature. To use this, simply::

	CASL.METRIC[true]

You can also send further information to be tracked::

	CASL.METRIC[true](agentState, "aString");

GET_ID
^^^^^^^
Every Entity in CASL has an object called ``entityID()`` which is generated on creation and assigns each Entity a unique ID. While it's not always useful to have direct access to the ID, situations may occur when you need it. To access an Entity's ID, simply::

	var EntityID:id = CASL.GET_ID();

