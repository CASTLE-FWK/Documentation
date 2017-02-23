ENVIRONMENT
------------

An ``ENVIRONMENT`` in CASL has the following structure::

	ENVIRONMENT anEnvironment: {
		description: "";
		environment_rules: {
			type: implicit
			attributes: virtual
			layout_type: BOUND;
		};
		parameters: {};
		functions: {};
		behaviors: {};
		interactions: {};
		adaptation: {};	
		subsystems: {};		
	};

In CASL-SG, an ``ENVIRONMENT`` has an extra component called Group_Interactions::
	
	group_interactions: {};


Description
^^^^^^^^^^^^^^^
**(Optional)**

This allows the designer to add a helpful description to the model. Newlines are allowed.

Environment_Rules
^^^^^^^^^^^^^^^^^^
There are 3 rules that have to be set for each ``ENVIRONMENT``, these are ``type``, ``attributes``, ``layout_type``.

Type
####


Attributes
###########

Layout_Type
############



Parameters
^^^^^^^^^^^
This stores the ``ENVIRONMENT`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
^^^^^^^^^
This stores the ``ENVIRONMENT`` functions. Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this ENVIRONMENT
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this ENVIRONMENT
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
^^^^^^^^^^
This stores the ``ENVIRONMENT`` behaviors. An example::

	changeStateToDead[SELF][DELAYED](): {
		FUNCTION.setState(false);
	};


:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
^^^^^^^^^^^^^
This stores the ``ENVIRONMENT`` interactions. An example::

	checkNeighboursVelocity[ENVIRONMENT][INSTANT](): {
		BEHAVIOR.adjustVelocity(neighbour.AGT_INTERACTION.getVelocity());
	};


:doc:`More about Interactions <Blocks/Interactions>`

Adaptation
^^^^^^^^^^
This stores the ``ENVIRONMENT`` adptations or adaptive processes. An example::

	adaptState[IMPLICIT][NONE](var int:numNeighbors): {
		if (numNeighbors > 3) then
			BEHAVIOR.die();
		endif;
	}

:doc:`More about Adaptations <Blocks/Adaptations>`

Subsystems
^^^^^^^^^^^
This stores the ``ENVIRONMENT`` subsystems. In here you can declare multiple ``ENVIRONMENT`` types. The parent type and other subsystems can interact.

:doc:`More about Subsystems <Blocks/Subsystems>`
