SEMANTIC GROUP
---------------

A semantic group in CASL-SG has the following structure::

	GROUP aGroup: {
			description: "";
			group_rules: {
				layout_type: BOUND;
			};
			parameters: {};
			functions: {};
			behaviors: {};
			transmissions: {};
			internals: {};
	};


Parameters
^^^^^^^^^^^
This stores the ``GROUP`` parameters. Some examples::

	var bool:Alive = false;
	agt Cell:aNeighbour;

:doc:`More about Parameters <Blocks/Parameters>`

Functions
^^^^^^^^^
This stores the ``GROUP`` functions. Each ``GROUP`` requires an ``initialize`` function to be declared and the CASL Editor will warn you if it is missing.  Some examples::

	//Double a number and return
	def doubleNumber(var int:num)(var int:newNum): {
		newNum = num * 2;
	};

	//Set the position of this GROUP
	def setPosition(var Vector2:pos)(): {
		self.position = pos;
	};

	//Get the position of this GROUP
	def getPosition()(var Vector2:pos): {
		pos = self.position.
	};

:doc:`More about Functions <Blocks/Functions>`

Behaviors
^^^^^^^^^^
This stores the ``GROUP`` behaviors. An example::

	changeStateToDead[SELF][DELAYED](): {
		FUNCTION.setState(false);
	};


:doc:`More about Behaviors <Blocks/Behaviors>`

Interactions
^^^^^^^^^^^^^
This stores the ``GROUP`` interactions. An example::

	checkNeighboursVelocity[GROUP][INSTANT](): {
		BEHAVIOR.adjustVelocity(neighbour.AGT_INTERACTION.getVelocity());
	};


:doc:`More about Interactions <Blocks/Interactions>`

Transmissions
^^^^^^^^^^^^^^

Internals
^^^^^^^^^^