ENVIRONMENTS
------------

Description
^^^^^^^^^^^^^^^
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

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

Interactions
^^^^^^^^^^^^^



:doc:`More about Interactions <Blocks/Interactions>`

Adaptation
^^^^^^^^^^


:doc:`More about Adaptations <Blocks/Adaptations>`

Subsystems
^^^^^^^^^^^


:doc:`More about Subsystems <Blocks/Subsystems>`