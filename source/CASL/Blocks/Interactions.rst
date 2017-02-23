Interactions
============

An Interaction allows for entities to communicate with one another and therefore fulfilling the basic idea of agent based modelling.

Structure
----------
A CASL interaction consists of a name, an interaction type, a trigger type, and an optional input parameter. An example is::

	interact[QUERY][STATE](var int:num): {
		//The interaction
	};


Interaction Type
-----------------
There are 3 types of interactions, namely, ``QUERY``, ``COMMUNICATION``, and ``INDIRECT``.

* ``QUERY``

* ``COMMUNICATION``

* ``INDIRECT``


Trigger Type
------------
There are 4 types of trigger types: ``STEP``, ``STATE``, ``PARAMETER``, ``INPUT``.

* ``STEP``

* ``STATE``

* ``PARAMETER``

* ``INPUT``



Input Parameters
----------------



Examples
---------
Reference interactions differs depending on the context. The following examples show the three 3 main contexts.::

	//An entity triggering its own interaction
	//This is usually how a COMMUNICATION interaction is performed
	INTERACTION.interactWithFriend(agt Friend:f): {
		
	};

	//An entity triggering the interaction in another entity
	//This is usually how a QUERY interaction is performed
	agt Friend:aFriend; //A reference to an agent
	var int:num = aFriend.AGT_INTERACTION.getInformation();

