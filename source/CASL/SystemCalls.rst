CASL System Calls
------------------

Occasionally, and predominantly at initialization time, other entities may need to access ``PARAMETERS`` or ``FUNCTIONS`` from the ``SYSTEM``. This can be acheieved by using a *system call*, which takes the form of::

	SYSTEM.parameterName;

For example, for a variable ``initialPopulationSize`` stored in an ``ENVIRONMENT``::
	
	var int:initialPopulationSize = SYSTEM.initialPopulationSize;
