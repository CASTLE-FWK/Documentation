AGENT
------
An Agent in CASL and CASL-SG has the following structure:: 

	AGENT theAgentsName: {
		description: "";
		parameters: {};
		functions: {
			def initialize()(): {};
		};
		behaviors: {};
		interactions: {};
		adaptation: {};
		subsystems: {};
	};

An ``AGENT`` block starts of with ``AGENT`` and the agents name

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
This stores the ``AGENT`` functions. Each ``AGENT`` requires an ``initialize`` function to be declared and the CASL Editor will warn you if it is missing. Some examples::

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
This stores the ``AGENT`` behaviors. An example::

	changeStateToDead[SELF][DELAYED](): {
		FUNCTION.setState(false);
	};


:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
^^^^^^^^^^^^^
This stores the ``AGENT`` interactions. An example::

	checkNeighboursVelocity[AGENT][INSTANT](): {
		BEHAVIOR.adjustVelocity(neighbour.AGT_INTERACTION.getVelocity());
	};


:doc:`More about Interactions <Blocks/Interactions>`

Adaptation
^^^^^^^^^^
This stores the ``AGENT`` adptations or adaptive processes. An example::

	adaptState[IMPLICIT][NONE](var int:numNeighbors): {
		if (numNeighbors > 3) then
			BEHAVIOR.die();
		endif;
	}

:doc:`More about Adaptations <Blocks/Adaptations>`

Subsystems
^^^^^^^^^^^
This stores the ``AGENT`` subsystems. In here you can declare multiple ``AGENT`` types. The parent type and other subsystems can interact.

:doc:`More about Subsystems <Blocks/Subsystems>`
