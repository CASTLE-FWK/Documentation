SEMANTIC GROUP
---------------

Parameters
^^^^^^^^^^^
This stores the ``AGENT`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
^^^^^^^^^
This stores the ``AGENT`` functions. Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this AGENT
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this AGENT
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
^^^^^^^^^^



:doc:`More about Behaviors <Blocks/Behaviors>`

GROUP_TRANSFER
^^^^^^^^^^^^^^^